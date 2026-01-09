# PROPUESTA TÉCNICA: MVP Plataforma Textil OIT-UNTREF

**Proyecto:** Plataforma digital para formalización y trazabilidad de talleres textiles
**Período:** Febrero 2026 - Julio 2026 (6 meses)
**Presupuesto:** $20,000 USD
**Equipo:** 6 personas (2 desarrollo + 4 implementación)

---

## 1. RESUMEN EJECUTIVO

Se propone desarrollar un Producto Mínimo Viable (MVP) de una plataforma digital que conecte marcas con talleres textiles formalizados, bajo supervisión del Estado y con apoyo de formación continua.

**Objetivo principal:** Demostrar que 20 talleres y 10 marcas pueden realizar pedidos verificables con trabajo decente, pagos registrados, y supervisión tripartita, en 6 meses.

**Problema que resuelve:** La industria textil argentina enfrenta barreras estructurales que perpetúan la informalidad:
- Falta de trazabilidad en la cadena productiva
- Desconfianza entre marcas y talleres
- Complejidad en la formalización
- Estado ausente en el monitoreo
- Bajas capacidades técnicas

---

## 2. ALCANCE DEL MVP

### 2.1 Funciones Incluidas (7 de 11)

| Función | Qué hace | Barrera que resuelve |
|---------|----------|---------------------|
| **REGISTRACIÓN** | Onboarding en <5 minutos con verificación CUIT | Formalización compleja |
| **ENCONTRAR** | Directorio de talleres + búsqueda por capacidad | Falta de clientes |
| **ACORDAR** | Contratos digitales con términos claros | Desconfianza |
| **COMPLIANCE** | Verificación CUIT en AFIP, niveles Bronce/Plata/Oro | Formalización |
| **FISCALIZAR** | Dashboard para inspectores del Estado | Estado ausente |
| **APRENDER** | Catálogo de cursos + certificados PDF | Bajas capacidades |
| **PAGAR** | Registro de pagos (placeholder, sin integración bancaria) | Desconfianza |

### 2.2 Funciones NO Incluidas (Fase 1-2)

| Función | Por qué no entra | Cuándo |
|---------|------------------|--------|
| EJECUTAR | Requiere tracking en tiempo real | Fase 1 |
| VERIFICAR | Requiere blockchain, QR por prenda | Fase 1 |
| LOGÍSTICA | Requiere integración con transportistas | Fase 2 |
| GOBERNAR | Mesa tripartita funciona offline primero | Fase 1 |

---

## 3. PERFILES COMERCIALES: EL ESPACIO DE CADA ACTOR

Para que el matching funcione, cada actor necesita un **espacio propio** donde presentar su información comercial.

### 3.1 Perfil del Taller

El taller completa su perfil para que las marcas lo encuentren:

| Sección | Campos | Obligatorio |
|---------|--------|-------------|
| **Datos básicos** | Nombre, CUIT (verificado), Ubicación, WhatsApp, Foto | Sí |
| **Capacidades** | Procesos que realiza, Tipos de prenda, Capacidad mensual | Sí |
| **Equipamiento** | Maquinaria, Trabajadores registrados | Parcial |
| **Extras** | Descripción, Fotos de trabajos (portfolio) | No |

**Catálogo de Procesos (el taller marca los que hace):**
- Corte, Confección, Lavandería, Desgaste/Lijado, Acabado/Terminación
- Tintorería, Estampado, Bordado, Planchado, Sublimado, Control de calidad

**Catálogo de Prendas (el taller marca su especialización):**
- Remera/Camiseta, Buzo/Hoodie, Campera, Jean, Pantalón
- Camisa, Ropa de trabajo, Ropa deportiva, Ropa infantil, Lencería, Otros

### 3.2 Perfil de la Marca

La marca completa su perfil para que los talleres la conozcan:

| Sección | Campos | Obligatorio |
|---------|--------|-------------|
| **Datos básicos** | Razón social, CUIT, Ubicación, WhatsApp, Logo | Sí |
| **Actividad** | Descripción, Tipos de prenda, Sector/Nicho | Parcial |
| **Volumen** | Pedidos mensuales típicos, Cantidad promedio | No |

### 3.3 Cómo Funciona el Matching

```
MARCA crea pedido → SISTEMA filtra talleres → SISTEMA rankea → MARCA ve lista ordenada
```

**Criterios de filtro automático:**
- Taller tiene la capacidad de prenda requerida
- Taller tiene los procesos requeridos
- Taller tiene capacidad >= cantidad del pedido
- Taller tiene CUIT verificado

**Fórmula de ranking:**
- Formalización (nivel Bronce/Plata/Oro): 40%
- Proximidad geográfica: 30%
- Reputación (rating de estrellas): 20%
- Capacidad disponible: 10%

**Lo que NO hacemos en MVP (queda para Fase 1):**
- Rutas de procesos predefinidas por tipo de prenda
- División automática de pedido entre varios talleres
- Matching con inteligencia artificial
- Cálculo automático de precio por proceso

---

## 4. FUNCIONAMIENTO DE LA APLICACIÓN

### 4.1 Flujo General

```
                    ┌─────────────────────────────────────────┐
                    │          PLATAFORMA TEXTIL              │
                    │                                         │
     MARCA ────────►│  1. Crea pedido                        │
                    │  2. Busca talleres compatibles          │
                    │  3. Recibe cotizaciones                 │
                    │  4. Firma contrato                      │◄──────── TALLER
                    │  5. Confirma entrega                    │
                    │  6. Registra pago                       │
                    │                                         │
                    │  ─────── MONITOREO ───────              │
                    │                                         │◄──────── INSPECTOR
                    │  Dashboard + Alertas automáticas        │
                    │                                         │
                    │  ─────── FORMACIÓN ───────              │
                    │                                         │
                    │  Cursos + Certificados verificables     │◄──────── TODOS
                    └─────────────────────────────────────────┘
```

### 4.2 Flujo de Registro (REGISTRACIÓN)

1. Usuario ingresa email + contraseña
2. Elige rol: Marca o Taller
3. Ingresa CUIT → Sistema verifica en AFIP automáticamente
4. Sistema auto-completa datos desde AFIP (razón social, domicilio)
5. Usuario confirma teléfono WhatsApp para notificaciones
6. **Tiempo total: <5 minutos**

### 4.3 Flujo de Pedido (ENCONTRAR → ACORDAR → PAGAR)

**Paso 1 - Crear pedido (Marca)**
- Tipo de prenda (remera, pantalón, etc.)
- Cantidad
- Fecha límite
- Presupuesto máximo

**Paso 2 - Buscar talleres (Sistema)**
- Filtra por: ubicación, capacidad, nivel de formalización
- Notifica a talleres compatibles por WhatsApp + Email

**Paso 3 - Cotizar (Taller)**
- Precio propuesto
- Plazo de entrega
- Condiciones

**Paso 4 - Acordar (Ambos)**
- Sistema genera contrato con términos
- Ambas partes "firman" aceptando términos
- Contrato queda registrado con fecha/hora

**Paso 5 - Entregar y Pagar**
- Taller marca "listo para entregar"
- Taller sube foto de las prendas
- Marca confirma recepción
- Marca registra que pagó (fuera del sistema)
- Taller confirma recepción de pago
- Pedido completado

### 4.4 Flujo de Fiscalización (FISCALIZAR)

El Inspector accede a un dashboard donde puede:
- Ver lista de todos los pedidos activos
- Ver lista de talleres con nivel de formalización
- Recibir alertas automáticas si:
  - Precio muy bajo (<70% del referencia INTI)
  - Taller sin actividad prolongada
  - Reclamos de usuarios
- Marcar talleres para auditoría presencial

### 4.5 Flujo de Aprendizaje (APRENDER)

1. Usuario accede a sección Cursos
2. Ve catálogo de cursos disponibles (ejemplos):
   - "Cómo usar la plataforma"
   - "Formalización de talleres textiles"
   - "Buenas prácticas de producción"
   - "Cálculo de costos y precios"
3. Se inscribe a un curso
4. Completa el contenido
5. Recibe certificado PDF verificable
6. Certificado aparece en su perfil público

---

## 5. INDICADORES DE ÉXITO

### 5.1 Indicadores de Resultado (Obligatorios)

| Indicador | Meta | Cómo se mide |
|-----------|------|--------------|
| Talleres registrados | 20 | Usuarios con rol taller en sistema |
| Marcas registradas | 10 | Usuarios con rol marca en sistema |
| Pedidos completados | 212 | Pedidos en estado "completado" |
| Satisfacción usuarios | >80% | Encuesta NPS post-transacción |
| Tasa de disputa | <5% | Pedidos con reclamo / total |

### 5.2 Indicadores de Proceso (Por etapa)

| Mes | Indicador | Meta |
|-----|-----------|------|
| **Mes 3 (Piloto inicial)** | Talleres registrados | 5 |
| | Marcas registradas | 3 |
| | Primer pedido creado | 1 |
| **Mes 4 (Expansión)** | Talleres activos | 10 |
| | Marcas activas | 5 |
| | Pedidos en curso | 10 |
| **Mes 5 (Estabilización)** | Talleres registrados | 15 |
| | Pedidos completados | 50 |
| | Tasa de conversión | >30% |
| **Mes 6 (Cierre)** | Todos los indicadores finales | 100% |

### 5.3 Indicadores de Calidad

| Indicador | Meta | Alerta si... |
|-----------|------|--------------|
| Tiempo de registro | <5 minutos | >10 minutos |
| Tiempo hasta primer pedido | <24 horas | >7 días |
| Tasa de abandono registro | <30% | >50% |
| Bugs críticos abiertos | 0 | >3 |

---

## 6. ARQUITECTURA TÉCNICA

### 6.1 Stack Tecnológico

| Componente | Tecnología | Costo/mes |
|------------|------------|-----------|
| Frontend + Backend | Next.js 14 (App Router) | - |
| Base de Datos | PostgreSQL via Supabase Pro | $25 USD |
| Autenticación | NextAuth.js | - |
| Deploy | Vercel Pro | $20 USD |
| Notificaciones | WhatsApp (Twilio) + Email | Variable |
| Verificación CUIT | AFIP SDK | ~$10 USD |
| **Total infraestructura** | | **~$55 USD/mes** |

### 6.2 Integraciones

| Servicio | Estado | Prioridad |
|----------|--------|-----------|
| **AFIP (ARCA)** | Obligatorio | Alta |
| **WhatsApp** | Requerido por OIT | Alta |
| **Email** | Sí | Media |
| **Mercado Pago** | Placeholder (Fase 1) | Baja |

### 6.3 Modelo de Desarrollo

**Enfoque:** Desarrollo 100% asistido por IA (Claude)

Los desarrolladores (no programadores) trabajan con Claude Max para:
- Generación de código
- Testing automatizado
- Documentación técnica
- Debugging y optimización

---

## 7. CRONOGRAMA

### 7.1 Fases

| Fase | Período | Duración |
|------|---------|----------|
| **Desarrollo** | Febrero - Marzo 2026 | 2 meses (36 días) |
| **Piloto** | Abril - Julio 2026 | 4 meses |

### 7.2 Desarrollo (36 días)

| Etapa | Días | Entregable |
|-------|------|------------|
| Setup + Auth + Perfiles | 8 | Login, registro, verificación CUIT |
| Pedidos + Encontrar | 8 | Crear pedidos, buscar talleres |
| Acordar + Pagar | 10 | Contratos, registro de pagos |
| Aprender | 6 | Cursos, certificados PDF |
| Fiscalizar + Integración | 4 | Dashboard inspector, AFIP real |

---

## 8. PRESUPUESTO

**Total OIT:** $20,000 USD = $29,700,000 ARS
**Tipo de cambio:** $1,485 ARS/USD (oficial, enero 2026)

### 8.1 Distribución por Actividad

| Actividad | Días | Valor/día ARS | Total ARS |
|-----------|------|---------------|-----------|
| Elaboración plan de trabajo e informes | 13 | 409,136 | 5,318,768 |
| Coordinación reuniones técnicas | 5 | 409,136 | 2,045,680 |
| **Diseño y desarrollo del prototipo** | **36** | **409,136** | **14,728,896** |
| Seguimiento implementación piloto | 5 | 409,136 | 2,045,680 |
| Monitoreo y evaluación de resultados | 3 | 409,136 | 1,227,408 |
| Propuesta estrategia de escalamiento | 1 | 409,136 | 409,136 |
| **Subtotal** | **63** | - | **25,775,568** |
| Fee administración UNTREF (10%) | - | - | 2,577,557 |
| Infraestructura (6 meses) | - | - | 430,650 |
| **TOTAL** | - | - | **28,783,775** |

### 8.2 Infraestructura (6 meses)

| Servicio | Plan | $/mes USD | Total 6 meses ARS |
|----------|------|-----------|-------------------|
| Vercel | Pro | $20 | $178,200 |
| Supabase | Pro | $25 | $222,750 |
| Dominio .ar | - | ~$3 | $29,700 |
| **Total Infra** | - | $48 | **$430,650** |

**Nota:** Claude Max (herramienta de desarrollo IA) es pagado por los desarrolladores y no está incluido en el presupuesto OIT.

---

## 9. EQUIPO

| Rol | Personas | Dedicación | Responsabilidad |
|-----|----------|------------|-----------------|
| Desarrollo | 2 | Part-time | Código con Claude Max |
| Implementación | 4 | Part-time | Relación con actores, difusión |
| Coordinación OIT/UNTREF | 1 | - | Supervisión |

---

## 10. GOBERNANZA

| Decisión | Responsable |
|----------|-------------|
| Diseño de pantallas | OIT aprueba |
| Precios de referencia | INTI define |
| Reglas de alertas | Mesa tripartita |
| Resolución de disputas | Mesa tripartita |
| Priorización de features | Equipo según feedback |

---

## 11. RIESGOS Y MITIGACIONES

| Riesgo | Probabilidad | Impacto | Mitigación |
|--------|--------------|---------|------------|
| Baja adopción de talleres | Media | Alto | Acompañamiento presencial, incentivos |
| Un desarrollador se va | Baja | Crítico | Documentación exhaustiva, código simple |
| AFIP cambia API | Muy baja | Bajo | SDK se actualiza automáticamente |
| Resistencia del Estado | Baja | Medio | Involucrar desde día 1 |

---

## 12. POST-MVP

- **Propiedad intelectual:** OIT
- **Código:** Repositorio GitHub (licencia por definir)
- **Replicabilidad:** Diseño para adaptar a otros países
- **Fase 1:** Depende del éxito del MVP

---

## 13. ANEXOS

### A. Prototipo Actual
- URL: https://gbreard.github.io/textil/
- 21 pantallas HTML estáticas

### B. Documentación Técnica
- Repositorio: github.com/gbreard/textil-mvp
- Carpeta: MVP_DESARROLLO/docs/

### C. Contacto
- Coordinación: Matías Crespo (OIT/UNTREF)
- Desarrollo: Sergio Rodriguez, Gerardo Breard

---

*Documento generado para propuesta OIT - Enero 2026*
