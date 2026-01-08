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

### Cronograma MVP (Equipo: 2 devs + Claude)

```
═══════════════════════════════════════════════════════════════
FASE DESARROLLO: 2 MESES (8 semanas)
═══════════════════════════════════════════════════════════════

SEMANA 1: SETUP + AUTH
├── Dev 1: Proyecto Next.js + Supabase + Deploy Vercel
├── Dev 2: NextAuth + modelo usuarios
└── Claude: Scaffolding, tipos TypeScript, componentes base

SEMANA 2: AUTH + PERFILES
├── Dev 1: Registro marca/taller + login
├── Dev 2: Perfiles editables + verificación CUIT (mock)
└── Claude: Validaciones, formularios, tests unitarios

SEMANA 3-4: PEDIDOS + ENCONTRAR
├── Dev 1: CRUD pedidos + dashboard marca
├── Dev 2: Dashboard taller + lista pedidos
└── Claude: Componentes UI, filtros, búsqueda

SEMANA 5-6: ACORDAR + PAGAR
├── Dev 1: Cotizaciones + contratos digitales
├── Dev 2: Integración Mercado Pago + escrow
└── Claude: Lógica de estados, webhooks, notificaciones

SEMANA 7: APRENDER
├── Dev 1: Catálogo cursos + inscripciones
├── Dev 2: Certificados PDF + perfil público
└── Claude: Generación PDF, tracking progreso

SEMANA 8: FISCALIZAR + INTEGRACIÓN
├── Dev 1: Dashboard inspector + alertas
├── Dev 2: Integración AFIP real (reemplazar mock)
└── Claude: Tests E2E, documentación API

═══════════════════════════════════════════════════════════════
FASE IMPLEMENTACIÓN Y PRUEBAS: 4 MESES
═══════════════════════════════════════════════════════════════

MES 3: PILOTO INICIAL
├── Onboarding 5 talleres + 3 marcas
├── Soporte intensivo
├── Recopilación feedback
└── Fixes críticos

MES 4: EXPANSIÓN PILOTO
├── Escalar a 15 talleres + 8 marcas
├── Primeras transacciones reales
├── Ajustes UX basados en uso
└── Capacitación usuarios

MES 5: ESTABILIZACIÓN
├── 20 talleres + 10 marcas objetivo
├── Monitoreo de métricas
├── Optimización performance
└── Documentación para soporte

MES 6: EVALUACIÓN Y CIERRE MVP
├── Evaluación métricas vs objetivos
├── Documentación de aprendizajes
├── Plan para Fase 1
└── Decisión: escalar o iterar

TOTAL: 6 MESES
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

## Presupuesto MVP

**Presupuesto total OIT:** $20,000 USD (6 meses)
**Equipo:** 6 personas

### Distribución por Área

| Área | Personas | Período | Monto USD |
|------|----------|---------|-----------|
| **Desarrollo** (con Claude Code) | 2 | Meses 1-2 + soporte | $6,000 |
| **Implementación** (actores, capacitación, difusión) | 4 | Meses 1-6 | $12,000 |
| **Infraestructura** | - | 6 meses | $500 |
| **Contingencia** | - | - | $1,500 |
| **TOTAL** | **6** | **6 meses** | **$20,000** |

### Detalle Desarrollo

| Rubro | Horas | $/hora | Total USD |
|-------|-------|--------|-----------|
| Dev 1 - desarrollo intensivo | 150 | $20 | $3,000 |
| Dev 2 - desarrollo intensivo | 150 | $15 | $2,250 |
| Soporte meses 3-6 (bugs, mejoras) | 50 | $15 | $750 |
| **Subtotal Desarrollo** | **350** | - | **$6,000** |

*Claude Code acelera el desarrollo, reduciendo horas necesarias*

### Detalle Implementación

| Rol | Responsabilidad | Monto USD |
|-----|-----------------|-----------|
| Coordinador/a | Gestión proyecto, mesa tripartita | $4,000 |
| Facilitador/a 1 | Captación talleres, onboarding | $3,000 |
| Facilitador/a 2 | Captación marcas, onboarding | $3,000 |
| Comunicación | Difusión, capacitación, materiales | $2,000 |
| **Subtotal Implementación** | - | **$12,000** |

### Detalle Infraestructura

| Servicio | Plan | Total USD |
|----------|------|-----------|
| Vercel | Free (MVP) | $0 |
| Supabase | Free (MVP) | $0 |
| Claude API | ~$80/mes × 6 | $480 |
| Dominio | .ar | $20 |
| **Subtotal Infra** | - | **$500** |

*Usar tiers gratuitos en MVP, escalar en Fase 1 si necesario*

---

## Equipo MVP

| Rol | Cantidad | Responsabilidad |
|-----|----------|-----------------|
| Full-stack Dev | 2 | Frontend, Backend, integraciones |
| Claude (IA) | 1 | Scaffolding, componentes, tests, documentación |

### Distribución de Trabajo

```
Dev 1 (Lead)           Dev 2                  Claude
─────────────────────────────────────────────────────────
Arquitectura           Features paralelas     Código boilerplate
Integraciones críticas UI/UX implementation   Componentes React
Code review            Testing manual         Tests automatizados
Deploy/DevOps          Documentación usuario  Documentación técnica
```

### Rol de Claude en el Desarrollo
- **Generación de código**: Componentes, tipos, validaciones
- **Aceleración**: Tareas repetitivas, scaffolding
- **Calidad**: Tests unitarios, E2E, documentación
- **Soporte**: Debugging, optimización, refactoring

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
