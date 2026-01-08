# 04 - Hoja de Ruta de Implementación

## Principios NO Negociables

### 1. Gobernanza tripartita desde día 1
Mesa tripartita (Estado + Empleadores + Trabajadores) decide QUÉ se construye, CÓMO, y CUÁNDO.

### 2. Fiscalización es HABILITADORA, no punitiva
Estado monitorea desde pedido #1 pero con enfoque PREVENTIVO.

### 3. Desarrollo iterativo cada 3 meses
Liberamos funcionalidad mínima, validamos con usuarios reales, ajustamos.

### 4. Inclusión progresiva, no expulsión
Talleres en proceso de formalización pueden entrar con plan de regularización.

### 5. Código abierto y auditable
Todo el código en GitHub, blockchain para verificación.

---

## MVP (Meses 0-6)

### Pregunta Clave
> "¿Pueden 20 talleres y 10 marcas hacer pedidos verificables con trabajo decente, pagos garantizados, y supervisión tripartita, en 6 meses?"

### Métricas de Éxito

| Métrica | Objetivo MVP |
|---------|--------------|
| Talleres registrados | 20 |
| Marcas activas | 10 |
| Pedidos completados | 212 |
| Valor transado | $2.1M USD |
| Tasa de disputa | <5% |
| Satisfacción | >80% |

### Funciones en MVP (6 de 10)

| Función | Estado | Barrera que resuelve |
|---------|--------|---------------------|
| ENCONTRAR | ✅ Directorio + búsqueda simple | Falta de clientes |
| ACORDAR | ✅ Contrato digital básico | Desconfianza |
| PAGAR | ✅ Escrow con Mercado Pago | Desconfianza |
| COMPLIANCE | ✅ Verificación CUIT | Formalización |
| FISCALIZAR | ✅ Dashboard básico | Estado ausente |
| APRENDER | ✅ Catálogo + certificados | Comunidad de aprendizaje |
| EJECUTAR | ❌ Fase 1 | - |
| VERIFICAR | ❌ Fase 1 | - |
| LOGÍSTICA | ❌ Fase 1 | - |
| GOBERNAR | ❌ Fase 1 | - |

### Cronograma MVP (Sprints - Equipo 1-2 devs)

```
SPRINT 0: SETUP (1 semana)
├── Crear proyecto Next.js
├── Configurar Supabase/PostgreSQL
├── Configurar NextAuth
└── Deploy inicial en Vercel

SPRINT 1: AUTH + PERFILES (2 semanas)
├── Registro marca/taller
├── Login
├── Verificación CUIT básica
└── Perfil editable

SPRINT 2: PEDIDOS (2 semanas)
├── CRUD pedidos (ENCONTRAR)
├── Dashboard marca
├── Dashboard taller
└── Lista de pedidos disponibles

SPRINT 3: MATCHING + CONTRATOS (2 semanas)
├── Búsqueda de talleres (ENCONTRAR)
├── Cotización (ACORDAR)
├── Contrato digital
└── Notificaciones email

SPRINT 4: PAGOS (2 semanas)
├── Integración Mercado Pago (PAGAR)
├── Escrow al crear pedido
├── Liberación al confirmar entrega
└── Historial de pagos

SPRINT 5: APRENDIZAJE (2 semanas)
├── Catálogo de cursos (APRENDER)
├── Inscripción a cursos
├── Tracking de progreso
├── Certificados PDF
└── Certificados en perfil

SPRINT 6: ESTADO + POLISH (2 semanas)
├── Dashboard inspector (FISCALIZAR)
├── Alertas básicas
├── Testing con usuarios reales
└── Fixes y mejoras

TOTAL: ~13 semanas (3.5 meses)
```

### Pantallas MVP (10 pantallas)

| # | Pantalla | Rol | Función |
|---|----------|-----|---------|
| 1 | Landing/Login | Todos | Auth |
| 2 | Perfil | Todos | Compliance |
| 3 | Dashboard Marca | Marca | - |
| 4 | Crear Pedido | Marca | Encontrar |
| 5 | Ver Talleres | Marca | Encontrar |
| 6 | Dashboard Taller | Taller | - |
| 7 | Aceptar Pedido | Taller | Acordar |
| 8 | Catálogo Cursos | Taller | Aprender |
| 9 | Mis Certificados | Taller | Aprender |
| 10 | Dashboard Inspector | Estado | Fiscalizar |

---

## Fase 1 (Meses 7-12)

### Objetivos
- Escalar de 20 a 100 talleres
- Escalar de 10 a 50 marcas
- Agregar funciones faltantes (EJECUTAR, VERIFICAR, LOGÍSTICA, GOBERNAR)
- Integrar blockchain real (Polygon)
- IA para matching avanzado
- Certificados avanzados con blockchain

### Métricas Fase 1

| Métrica | Objetivo |
|---------|----------|
| Talleres | 100 |
| Marcas | 50 |
| Pedidos | 1,060 |
| Valor transado | $10.6M USD |

---

## Fase 2 (Meses 13-24)

### Objetivos
- Escalar nacionalmente
- Integración completa con AFIP/ANSES
- Sostenibilidad financiera
- Replicación en otros países (OIT)

---

## Presupuesto Estimado

### MVP (6 meses)

| Rubro | Monto USD |
|-------|-----------|
| Equipo técnico (4 personas × 6 meses) | $360,000 |
| Infraestructura cloud | $36,000 |
| Diseño UX/UI | $48,000 |
| Legal y compliance | $24,000 |
| Capacitación y soporte | $36,000 |
| Contingencia (20%) | $100,800 |
| **TOTAL MVP** | **$604,800** |

### Fase 1 (6 meses adicionales)

| Rubro | Monto USD |
|-------|-----------|
| Equipo técnico (6 personas) | $540,000 |
| Infraestructura | $54,000 |
| Integraciones (AFIP, blockchain) | $72,000 |
| Marketing y adopción | $48,000 |
| **TOTAL Fase 1** | **$714,000** |

### Total Año 1: ~$1.3M USD

### Auto-sostenibilidad
- Comisión por transacción: 2-5%
- Break-even estimado: Mes 9-12

---

## Equipo Mínimo MVP

| Rol | Cantidad | Responsabilidad |
|-----|----------|-----------------|
| Tech Lead | 1 | Arquitectura, código |
| Full-stack Dev | 2 | Frontend + Backend |
| UX Designer | 1 | Interfases, prototipo |
| Product Owner | 1 | Priorización, mesa tripartita |
| DevOps | 0.5 | Infra, CI/CD |

---

## Riesgos y Mitigaciones

| Riesgo | Probabilidad | Mitigación |
|--------|--------------|------------|
| Baja adopción de talleres | Media | Incentivos iniciales, acompañamiento presencial |
| Resistencia del Estado | Baja | Involucrar desde día 1 |
| Fallas técnicas | Media | Testing exhaustivo, rollback rápido |
| Cambio de gobierno | Media | Código abierto, documentación completa |

---

## Documento Completo

Ver: `../Plataforma/00_INFORME_FINAL/PARTE_6_HOJA_RUTA_IMPLEMENTACION.md`
