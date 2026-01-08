# 05 - Arquitectura Técnica

## Estado: POR DEFINIR

Este documento se completará cuando se defina el stack tecnológico.

---

## Opciones en Evaluación

### Frontend

| Opción | Pros | Contras |
|--------|------|---------|
| **React + TypeScript** | Ecosistema maduro, fácil contratar | Bundle grande |
| **Vue.js 3** | Más ligero, curva suave | Menos developers |
| **Next.js** | SSR, SEO, fullstack | Más complejo |

### Backend

| Opción | Pros | Contras |
|--------|------|---------|
| **Node.js + Express** | JavaScript everywhere, rápido | CPU-intensive lento |
| **Python + FastAPI** | Aprovechar RAG existente, ML | Dos lenguajes |
| **Python + Django** | Baterías incluidas, admin | Más pesado |

### Base de Datos

| Opción | Pros | Contras |
|--------|------|---------|
| **PostgreSQL** | ACID, JSON support, maduro | Escala vertical |
| **MongoDB** | Flexible, escala horizontal | Sin ACID nativo |

### Blockchain

| Opción | Pros | Contras |
|--------|------|---------|
| **Polygon** | Bajo costo, EVM compatible | Menos descentralizado |
| **Ethereum L2** | Más seguro | Más caro |
| **Sin blockchain (MVP)** | Más simple | Menos verificable |

### Infraestructura

| Opción | Pros | Contras |
|--------|------|---------|
| **AWS** | Más servicios, ubicuidad | Costoso, lock-in |
| **GCP** | ML/AI, Kubernetes | Menos servicios |
| **DigitalOcean** | Simple, económico | Menos escala |
| **On-premise** | Control total | Más trabajo |

---

## Arquitectura Propuesta (Borrador)

```
┌─────────────────────────────────────────────────────────┐
│                      FRONTEND                            │
│  React + TypeScript / Next.js                           │
│  - SPA para usuarios                                    │
│  - PWA para móviles                                     │
└─────────────────────┬───────────────────────────────────┘
                      │ REST API / GraphQL
┌─────────────────────┴───────────────────────────────────┐
│                      BACKEND                             │
│  Node.js + Express / FastAPI                            │
│  - API REST                                             │
│  - Autenticación (JWT)                                  │
│  - Lógica de negocio                                    │
└─────────────────────┬───────────────────────────────────┘
                      │
┌─────────────────────┴───────────────────────────────────┐
│                   SERVICIOS                              │
│  ┌─────────┐ ┌─────────┐ ┌─────────┐ ┌─────────┐       │
│  │   DB    │ │  AFIP   │ │ Mercado │ │Blockchain│       │
│  │PostgreSQL│ │  API    │ │  Pago   │ │ Polygon │       │
│  └─────────┘ └─────────┘ └─────────┘ └─────────┘       │
└─────────────────────────────────────────────────────────┘
```

---

## Modelo de Datos (Borrador)

### Entidades Principales

```
Usuario
├── id
├── tipo (TALLER | MARCA | INSPECTOR | TRABAJADOR)
├── email
├── cuit
├── estado_verificacion
└── fecha_registro

Taller
├── id
├── usuario_id
├── razon_social
├── nivel_formalizacion (BRONCE | PLATA | ORO)
├── capacidades[]
├── ubicacion
└── reputacion_score

Marca
├── id
├── usuario_id
├── razon_social
├── sector
└── historial_pagos_score

Pedido
├── id
├── marca_id
├── taller_id
├── estado (BORRADOR | PUBLICADO | EN_NEGOCIACION | ACORDADO | EN_EJECUCION | COMPLETADO)
├── tipo_prenda
├── cantidad
├── precio_unitario
├── precio_referencia
├── fecha_limite
└── hitos[]

Contrato
├── id
├── pedido_id
├── terminos
├── firma_marca
├── firma_taller
├── fecha_firma
└── hash_blockchain

Avance
├── id
├── pedido_id
├── porcentaje
├── evidencia_url
├── trabajador_cuit
├── fecha
└── validado

Pago
├── id
├── pedido_id
├── monto
├── estado
├── fecha
└── metodo
```

---

## Integraciones

Ver: [06_INTEGRACIONES.md](06_INTEGRACIONES.md)

---

## Decisiones Pendientes

- [ ] Definir stack frontend
- [ ] Definir stack backend
- [ ] Definir proveedor cloud
- [ ] Definir si MVP usa blockchain o no
- [ ] Definir estrategia de autenticación
- [ ] Definir estrategia de testing

---

## Referencias

- Prototipo actual: `../prototipo/` o https://gbreard.github.io/textil/
- Stack propuesto en documentación: `../Plataforma/04_ESPECIFICACIONES_TECNICAS/`
