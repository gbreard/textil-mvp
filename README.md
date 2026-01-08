# Plataforma Textil OIT-UNTREF - MVP

**Repositorio de desarrollo del MVP**

## Visión

Plataforma sociotécnica para el sector textil argentino que busca:
- Formalizar talleres y cooperativas textiles
- Conectar marcas con proveedores verificados
- Garantizar trazabilidad y transparencia
- Facilitar la fiscalización del Estado
- Combatir el trabajo informal y el dumping social

## Estado Actual

- **Prototipo:** https://gbreard.github.io/textil/ (21 pantallas HTML)
- **Documentación:** Completa (ver `/docs`)
- **Desarrollo:** Por iniciar

## Estructura

```
MVP_DESARROLLO/
├── README.md              ← Estás aquí
├── docs/                  # Documentación consolidada
│   ├── 01_CONTEXTO.md     # Resumen del proyecto
│   ├── 02_FUNCIONES.md    # Las 10 funciones
│   ├── 03_CASOS_USO.md    # Casos prioritarios
│   ├── 04_HOJA_RUTA.md    # Cronograma y métricas
│   ├── 05_ARQUITECTURA.md # Stack técnico (por definir)
│   └── 06_INTEGRACIONES.md # AFIP, ANSES, etc.
├── prototipo/             # Copia del prototipo actual
└── [src/, database/, etc.] # Por crear
```

## Documentación

| Documento | Descripción |
|-----------|-------------|
| [01_CONTEXTO.md](docs/01_CONTEXTO.md) | Qué es el proyecto, actores, barreras |
| [02_FUNCIONES.md](docs/02_FUNCIONES.md) | Las 10 funciones de la plataforma |
| [03_CASOS_USO.md](docs/03_CASOS_USO.md) | Casos de uso prioritarios para MVP |
| [04_HOJA_RUTA.md](docs/04_HOJA_RUTA.md) | Cronograma, presupuesto, métricas |
| [05_ARQUITECTURA.md](docs/05_ARQUITECTURA.md) | Stack técnico (por definir) |
| [06_INTEGRACIONES.md](docs/06_INTEGRACIONES.md) | Integración con bases del Estado |

## Métricas del MVP (Mes 0-6)

| Métrica | Objetivo |
|---------|----------|
| Talleres registrados | 20 |
| Marcas activas | 10 |
| Pedidos procesados | 212 |
| Presupuesto total | $741.700 USD |
| Auto-sostenible | Mes 9 |

## Las 10 Funciones

### Core (6)
1. **ENCONTRAR** - Matching talleres ↔ marcas
2. **ACORDAR** - Contratos digitales
3. **EJECUTAR** - Trazabilidad en tiempo real
4. **VERIFICAR** - Auditoría y certificación
5. **LOGÍSTICA** - Coordinación de entregas
6. **PAGAR** - Pagos trazados

### Habilitación (2)
7. **APRENDER** - Capacitación contextual
8. **COMPLIANCE** - Checklist de formalización

### Gobernanza (2)
9. **FISCALIZAR** - Priorización de inspecciones
10. **GOBERNAR** - Mesa tripartita

## Los 8 Actores

1. Talleres y Cooperativas
2. Marcas de Indumentaria
3. Trabajadores Textiles
4. Federaciones (FACTA)
5. Sindicatos (SOIVA)
6. Estado (MTEySS, AFIP, ANSES)
7. Certificadores (Vestir Conciencia)
8. Consumidores Finales

## Las 7 Barreras que Resuelve

| # | Barrera | Solución |
|---|---------|----------|
| B1 | Falta de Trazabilidad | Registro verificable en tiempo real |
| B2 | Desconfianza entre Actores | Reputación transparente y pública |
| B3 | Formalización Compleja | Checklist automatizado con ayuda |
| B4 | Falta de Articulación | Dashboard compartido entre actores |
| B5 | Estado Ausente | Datos e IA amplifican fiscalización |
| B6 | Bajas Capacidades | Cursos contextuales gratuitos |
| B7 | Dumping Social | Transparencia nivela la cancha |

## Stack Tecnológico (Por Definir)

Opciones en evaluación:

**Frontend:**
- React + TypeScript
- Vue.js
- Next.js

**Backend:**
- Node.js + Express
- Python (FastAPI/Django)

**Base de Datos:**
- PostgreSQL

**Integraciones:**
- AFIP/ARCA (Web Services)
- ANSES
- Mercado Pago

## Referencias

- **Prototipo actual:** [gbreard.github.io/textil](https://gbreard.github.io/textil/)
- **Documentación completa:** `../Plataforma/`
- **Índice del proyecto:** `../INDICE_PROYECTO.md`

---

## Cómo Contribuir

1. Revisar documentación en `/docs`
2. Ver prototipo actual en `/prototipo` o [online](https://gbreard.github.io/textil/)
3. Proponer cambios via Pull Request

## Licencia

Por definir (probablemente Open Source)
