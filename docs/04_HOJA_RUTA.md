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

### Funciones en MVP (7 de 10)

| Función | Estado |
|---------|--------|
| ENCONTRAR | ✅ Simplificado |
| ACORDAR | ✅ Sin blockchain |
| EJECUTAR | ✅ Básico |
| PAGAR | ✅ Sin escrow automático |
| COMPLIANCE | ✅ Simplificado |
| FISCALIZAR | ✅ Dashboard básico |
| GOBERNAR | ✅ Mesa tripartita |
| VERIFICAR | ❌ Fase 1 |
| LOGÍSTICA | ❌ Fase 1 |
| APRENDER | ❌ Fase 1 |

### Cronograma MVP

```
MES -3 a -1: PREPARACIÓN
├── Constituir mesa tripartita
├── Seleccionar talleres y marcas piloto
├── Definir métricas de éxito
└── Preparar documentación legal

MES 0: KICK-OFF
├── Mesa tripartita aprueba alcance MVP
├── Equipo técnico inicia desarrollo
└── Onboarding de primeros talleres

MES 1-2: DESARROLLO CORE
├── Registro de usuarios (COMPLIANCE básico)
├── Crear pedido y matching (ENCONTRAR)
├── Contrato digital (ACORDAR)
└── Revisión quincenal con mesa tripartita

MES 3: PRIMER PILOTO
├── 5 talleres + 3 marcas hacen pedidos reales
├── Soporte intensivo del equipo
├── Recopilación de feedback
└── Ajustes urgentes

MES 4: SEGUNDO CICLO
├── Seguimiento de pedidos (EJECUTAR)
├── Pagos vía plataforma (PAGAR)
├── Dashboard Estado (FISCALIZAR)
└── Más talleres y marcas

MES 5: EXPANSIÓN PILOTO
├── 15 talleres + 8 marcas
├── Dashboard mesa tripartita (GOBERNAR)
├── Refinamiento basado en feedback

MES 6: EVALUACIÓN
├── Mesa tripartita evalúa métricas
├── Decisión: ¿Escalar a Fase 1 o refinar MVP?
├── Documentación de aprendizajes
```

---

## Fase 1 (Meses 7-12)

### Objetivos
- Escalar de 20 a 100 talleres
- Escalar de 10 a 50 marcas
- Agregar funciones faltantes (VERIFICAR, LOGÍSTICA, APRENDER)
- Integrar blockchain real (Polygon)
- Integrar escrow automático

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
