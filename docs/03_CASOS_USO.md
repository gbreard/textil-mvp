# 03 - Casos de Uso Prioritarios para MVP

## Resumen

De los **46 casos de uso** documentados, estos son los prioritarios para el MVP:

---

## Por Función

### ENCONTRAR (7 casos totales, 3 en MVP)

| ID | Caso | Actor | MVP |
|----|------|-------|-----|
| CU-E01 | Taller busca pedidos | Taller | ✅ |
| CU-E02 | Marca busca talleres | Marca | ✅ |
| CU-E03 | Talleres se asocian para pedido grande | Cooperativas | ✅ |
| CU-E04 | Federación coordina pedidos | Federación | ❌ |
| CU-E05 | Estado publica compra pública | Estado | ❌ |
| CU-E06 | Trabajador busca taller | Trabajador | ❌ |
| CU-E07 | Consumidor busca marcas éticas | Consumidor | ❌ |

### ACORDAR (5 casos totales, 2 en MVP)

| ID | Caso | Actor | MVP |
|----|------|-------|-----|
| CU-A01 | Marca y taller firman contrato | Marca + Taller | ✅ |
| CU-A02 | Precio justo con calculadora | Marca | ✅ |
| CU-A03 | Contrato multi-parte (cooperativas) | Cooperativas | ❌ |
| CU-A04 | Estado firma contrato compra pública | Estado | ❌ |
| CU-A05 | Renegociación de condiciones | Marca + Taller | ❌ |

### EJECUTAR (4 casos totales, 2 en MVP)

| ID | Caso | Actor | MVP |
|----|------|-------|-----|
| CU-X01 | Taller registra avance con evidencia | Taller | ✅ |
| CU-X02 | Marca monitorea en tiempo real | Marca | ✅ |
| CU-X03 | Sistema detecta retraso y alerta | Sistema | ❌ |
| CU-X04 | Producción distribuida entre talleres | Cooperativas | ❌ |

### PAGAR (4 casos totales, 1 en MVP)

| ID | Caso | Actor | MVP |
|----|------|-------|-----|
| CU-P01 | Pago por hitos completados | Marca + Taller | ✅ |
| CU-P02 | Escrow garantiza fondos | Sistema | ❌ |
| CU-P03 | Disputa de calidad | Marca + Taller | ❌ |
| CU-P04 | Historial para crédito bancario | Taller + Banco | ❌ |

### COMPLIANCE (8 casos totales, 2 en MVP)

| ID | Caso | Actor | MVP |
|----|------|-------|-----|
| CU-C01 | Taller ve checklist de formalización | Taller | ✅ |
| CU-C02 | Sistema verifica CUIT en AFIP | Sistema | ✅ |
| CU-C03 | Taller genera plan de regularización | Taller | ❌ |
| CU-C04 | Cooperativa valida CUIT de miembros | Cooperativa | ❌ |
| CU-C05 | Trabajador verifica su situación | Trabajador | ❌ |
| CU-C06 | Marca verifica proveedor antes de contratar | Marca | ❌ |
| CU-C07 | Sistema sugiere profesionales matriculados | Sistema | ❌ |
| CU-C08 | Niveles BRONCE/PLATA/ORO | Sistema | ❌ |

### FISCALIZAR (5 casos totales, 2 en MVP)

| ID | Caso | Actor | MVP |
|----|------|-------|-----|
| CU-F01 | Inspector ve dashboard con priorización | Inspector | ✅ |
| CU-F02 | Sistema detecta precio anómalo | Sistema | ✅ |
| CU-F03 | Trabajador denuncia anónimamente | Trabajador | ❌ |
| CU-F04 | Inspector agenda auditoría | Inspector | ❌ |
| CU-F05 | Sistema genera reporte para MTEySS | Sistema | ❌ |

### GOBERNAR (6 casos totales, 2 en MVP)

| ID | Caso | Actor | MVP |
|----|------|-------|-----|
| CU-G01 | Mesa tripartita define parámetros | Mesa | ✅ |
| CU-G02 | Dashboard muestra métricas del ecosistema | Mesa | ✅ |
| CU-G03 | Simulador de impacto de cambios | Mesa | ❌ |
| CU-G04 | OIT genera reporte de impacto | OIT | ❌ |
| CU-G05 | Investigador accede a datos anonimizados | Investigador | ❌ |
| CU-G06 | Sistema sugiere ajustes por tendencias | Sistema | ❌ |

---

## Flujo Principal del MVP

```
1. MARCA crea pedido (ENCONTRAR)
   → Define: prenda, cantidad, plazo, presupuesto

2. SISTEMA sugiere talleres compatibles (ENCONTRAR)
   → Filtra por: formalización, capacidad, ubicación

3. TALLER cotiza y acepta (ACORDAR)
   → Sistema muestra precio de referencia

4. CONTRATO se firma digitalmente (ACORDAR)
   → Condiciones, hitos, pagos

5. TALLER registra avance (EJECUTAR)
   → Fotos, porcentaje, CUIT trabajador

6. MARCA monitorea progreso (EJECUTAR)
   → Ve tablero en tiempo real

7. MARCA paga por hitos (PAGAR)
   → Al completar 50%, 100%

8. ESTADO monitorea (FISCALIZAR)
   → Dashboard con alertas

9. MESA revisa métricas (GOBERNAR)
   → Ajusta parámetros si necesario
```

---

## Criterios de Aceptación MVP

### Para ENCONTRAR
- [ ] Marca puede publicar pedido en <5 minutos
- [ ] Sistema devuelve ≥3 talleres compatibles en <10 segundos
- [ ] Taller recibe notificación de oportunidad

### Para ACORDAR
- [ ] Contrato incluye: alcance, precio, plazo, hitos
- [ ] Ambas partes firman digitalmente
- [ ] Precio de referencia se muestra automáticamente

### Para EJECUTAR
- [ ] Taller puede registrar avance con foto
- [ ] Marca ve progreso sin llamar/visitar
- [ ] Sistema registra fecha/hora de cada evento

### Para PAGAR
- [ ] Marca puede pagar vía plataforma
- [ ] Taller recibe notificación de pago
- [ ] Historial de pagos visible para ambos

### Para COMPLIANCE
- [ ] Taller ve checklist con % completado
- [ ] Sistema valida CUIT en AFIP automáticamente
- [ ] Muestra qué falta para subir de nivel

### Para FISCALIZAR
- [ ] Inspector ve lista de talleres priorizada
- [ ] Sistema alerta precios <70% del referencia
- [ ] Dashboard muestra métricas básicas

### Para GOBERNAR
- [ ] Mesa puede ver métricas del ecosistema
- [ ] Parámetros del algoritmo son configurables
- [ ] Cambios quedan registrados con fecha/usuario

---

## Documento Completo

Ver: `../Plataforma/02_CASOS_USO/CASOS_USO_POR_FUNCION.md`
