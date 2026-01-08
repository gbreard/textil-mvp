# 05 - Arquitectura Técnica

## Stack Recomendado para MVP (Equipo Pequeño)

Para un equipo de 1-2 desarrolladores, se recomienda un stack unificado que minimice complejidad:

```
Frontend + Backend: Next.js 14+ (App Router)
Base de Datos:      PostgreSQL via Supabase
Autenticación:      NextAuth.js
Pagos:              Mercado Pago SDK
Email:              Resend o SendGrid
Deploy:             Vercel (gratis para empezar)
```

### Ventajas de este Stack
- **Un solo proyecto**: Frontend y API en el mismo repositorio
- **Un solo lenguaje**: TypeScript everywhere
- **Deploy simple**: Push a GitHub = deploy automático
- **Costo bajo**: Tier gratuito de Vercel + Supabase para MVP
- **Sin blockchain en MVP**: Se agrega en Fase 1

---

## Arquitectura MVP

```
┌─────────────────────────────────────────────────────────┐
│                      USUARIOS                            │
│  Marca  │  Taller  │  Inspector                         │
└───────────────┬─────────────────────────────────────────┘
                │
┌───────────────┴─────────────────────────────────────────┐
│              FRONTEND (Next.js)                          │
│  - Landing + Auth                                        │
│  - Dashboard por rol                                     │
│  - Crear/ver pedidos                                     │
│  - Catálogo de cursos                                    │
│  - Perfil taller/marca                                   │
└───────────────┬─────────────────────────────────────────┘
                │ API Routes
┌───────────────┴─────────────────────────────────────────┐
│              BACKEND (Next.js API)                       │
│  - Auth (NextAuth)                                       │
│  - CRUD pedidos/contratos                                │
│  - CRUD cursos/certificados                              │
│  - Verificación AFIP                                     │
│  - Webhooks Mercado Pago                                 │
└───────────────┬─────────────────────────────────────────┘
                │
┌───────────────┴─────────────────────────────────────────┐
│              BASE DE DATOS (Supabase)                    │
│  PostgreSQL + Auth + Storage                             │
└───────────────┬─────────────────────────────────────────┘
                │
┌───────────────┴─────────────────────────────────────────┐
│              SERVICIOS EXTERNOS                          │
│  ┌─────────┐ ┌─────────┐ ┌─────────┐                    │
│  │  AFIP   │ │ Mercado │ │  Email  │                    │
│  │  API    │ │  Pago   │ │ Resend  │                    │
│  └─────────┘ └─────────┘ └─────────┘                    │
└─────────────────────────────────────────────────────────┘
```

---

## Opciones Alternativas (Referencia)

### Si se prefiere Python Backend

| Componente | Opción |
|------------|--------|
| Frontend | React + Vite |
| Backend | FastAPI (Python) |
| DB | PostgreSQL (Railway) |
| Deploy | Railway o Render |

*Útil si se quiere integrar scripts Python existentes (RAG).*

---

## Modelo de Datos MVP

### Esquema SQL

```sql
-- USUARIOS Y PERFILES
users (
  id UUID PRIMARY KEY,
  email VARCHAR UNIQUE,
  role ENUM('marca', 'taller', 'inspector'),
  cuit VARCHAR(11),
  cuit_verified BOOLEAN DEFAULT FALSE,
  created_at TIMESTAMP
)

marca_profiles (
  user_id UUID REFERENCES users,
  razon_social VARCHAR,
  rubro VARCHAR,
  ubicacion VARCHAR,
  historial_pagos_score DECIMAL
)

taller_profiles (
  user_id UUID REFERENCES users,
  razon_social VARCHAR,
  capacidades TEXT[],
  ubicacion VARCHAR,
  nivel ENUM('bronce', 'plata', 'oro'),
  reputacion_score DECIMAL
)

-- TRANSACCIONES
pedidos (
  id UUID PRIMARY KEY,
  marca_id UUID REFERENCES users,
  estado ENUM('publicado', 'en_negociacion', 'acordado', 'completado'),
  tipo_prenda VARCHAR,
  cantidad INT,
  precio_max DECIMAL,
  plazo DATE,
  created_at TIMESTAMP
)

cotizaciones (
  id UUID PRIMARY KEY,
  pedido_id UUID REFERENCES pedidos,
  taller_id UUID REFERENCES users,
  precio DECIMAL,
  plazo DATE,
  mensaje TEXT,
  created_at TIMESTAMP
)

contratos (
  id UUID PRIMARY KEY,
  pedido_id UUID REFERENCES pedidos,
  taller_id UUID REFERENCES users,
  terminos TEXT,
  firma_marca TIMESTAMP,
  firma_taller TIMESTAMP,
  fecha_firma TIMESTAMP
)

pagos (
  id UUID PRIMARY KEY,
  contrato_id UUID REFERENCES contratos,
  monto DECIMAL,
  estado ENUM('pendiente', 'en_escrow', 'liberado', 'disputado'),
  mp_payment_id VARCHAR,
  created_at TIMESTAMP
)

-- APRENDIZAJE (Comunidad)
cursos (
  id UUID PRIMARY KEY,
  titulo VARCHAR,
  descripcion TEXT,
  duracion_horas INT,
  categoria VARCHAR,
  contenido_url VARCHAR,
  activo BOOLEAN DEFAULT TRUE,
  created_at TIMESTAMP
)

inscripciones (
  id UUID PRIMARY KEY,
  user_id UUID REFERENCES users,
  curso_id UUID REFERENCES cursos,
  progreso INT DEFAULT 0,
  completado BOOLEAN DEFAULT FALSE,
  fecha_inicio TIMESTAMP,
  fecha_fin TIMESTAMP
)

certificados (
  id UUID PRIMARY KEY,
  user_id UUID REFERENCES users,
  curso_id UUID REFERENCES cursos,
  codigo_verificacion VARCHAR UNIQUE,
  fecha_emision TIMESTAMP,
  pdf_url VARCHAR
)
```

### Diagrama Entidad-Relación

```
┌─────────┐       ┌─────────┐       ┌─────────┐
│  users  │───────│ pedidos │───────│contratos│
└────┬────┘       └────┬────┘       └────┬────┘
     │                 │                 │
     │            ┌────┴────┐       ┌────┴────┐
     │            │cotizac. │       │  pagos  │
     │            └─────────┘       └─────────┘
     │
     ├────────────┐
     │            │
┌────┴────┐  ┌────┴────┐
│ marca   │  │ taller  │
│ profile │  │ profile │
└─────────┘  └─────────┘

┌─────────┐       ┌─────────┐       ┌─────────┐
│  cursos │───────│inscripc.│───────│ certif. │
└─────────┘       └────┬────┘       └─────────┘
                       │
                  ┌────┴────┐
                  │  users  │
                  └─────────┘
```

---

## Integraciones

Ver: [06_INTEGRACIONES.md](06_INTEGRACIONES.md)

---

## Decisiones Técnicas

### Decidido
- [x] Stack: Next.js + Supabase (recomendado)
- [x] MVP sin blockchain (se agrega en Fase 1)
- [x] Autenticación: NextAuth.js
- [x] Pagos: Mercado Pago con escrow
- [x] Deploy: Vercel

### Pendiente de Confirmar
- [ ] Confirmar stack con equipo de desarrollo
- [ ] Definir estrategia de testing (Jest + Cypress)
- [ ] Configurar CI/CD en GitHub Actions

---

## Referencias

- Prototipo actual: `../prototipo/` o https://gbreard.github.io/textil/
- Stack propuesto en documentación: `../Plataforma/04_ESPECIFICACIONES_TECNICAS/`
