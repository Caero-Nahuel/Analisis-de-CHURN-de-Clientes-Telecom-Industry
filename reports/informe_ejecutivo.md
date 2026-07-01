# Informe Ejecutivo — Análisis de Churn de Clientes (Telecom Industry)

**Autor:** Nahuel Caero
**Fecha:** Julio 2025
**Dataset:** IBM Telco Customer Churn (7,043 registros, 21 variables)

---

## Resumen del Problema

Adquirir un nuevo cliente cuesta entre 5 y 7 veces más que retener uno existente. Este análisis explora los patrones de abandono de clientes en una empresa de telecomunicaciones, identificando los factores de mayor riesgo y las oportunidades de retención con mayor impacto.

---

## Hallazgos Clave

### 1. Métricas Globales

| Métrica | Valor |
|---|---|
| Total de clientes | 7,043 |
| Clientes perdidos (churn) | 1,869 |
| Tasa de churn | **26.5%** |
| Ingreso mensual en riesgo | ~$120,000/mes |
| Ingreso anual en riesgo | ~$1,440,000/año |

### 2. Factores de Mayor Riesgo

#### Tipo de Contrato
| Contrato | Tasa de Churn |
|---|---|
| **Month-to-month** | **42%** |
| One year | 11% |
| Two year | 3% |

Los clientes con contrato mensual tienen una tasa de abandono **14 veces mayor** que los de contrato bianual.

#### Tipo de Internet
| Internet Service | Tasa de Churn |
|---|---|
| **Fiber Optic** | **42%** |
| DSL | 19% |
| No internet | 7% |

Fibra óptica duplica la tasa de churn respecto a DSL, posiblemente por precio elevado o calidad inconsistente.

#### Servicios de Valor Agregado
| Servicio | Sin el servicio | Con el servicio |
|---|---|---|
| Online Security | 42% | 15% |
| Tech Support | 42% | 15% |
| Online Backup | 40% | 20% |

La ausencia de estos servicios se asocia a un churn **2.8 veces mayor**.

#### Antigüedad del Cliente (Tenure)
- Primeros 6 meses: **~47% de churn** (ventana crítica).
- 6-12 meses: ~27%.
- 2+ años: ~10%.

La probabilidad de abandono disminuye drásticamente después del primer año.

#### Método de Pago
| Método | Tasa de Churn |
|---|---|
| **Electronic Check** | **45%** |
| Mailed check | 19% |
| Bank transfer | 17% |
| Credit card | 15% |

### 3. Correlaciones con Churn

| Variable | Correlación | Interpretación |
|---|---|---|
| Tenure | -0.35 | A mayor antigüedad, menor churn |
| MonthlyCharges | +0.19 | A mayor cargo mensual, mayor churn |
| TotalCharges | -0.20 | Clientes que se van acumulan menos |

---

## Perfil del Cliente en Riesgo

Cliente con **alta probabilidad de abandono**:

- Contrato **mensual** (Month-to-month)
- Servicio **Fiber Optic**
- **Sin** Online Security ni Tech Support
- Antigüedad **menor a 6 meses**
- Paga con **Electronic Check**
- Cargo mensual **superior al promedio** (>$65)

---

## Recomendaciones Estratégicas

### Prioridad Alta (Impacto Rápido)

1. **Migración de contratos**
   - Ofrecer 1 mes gratis o descuento del 10% al migrar de contrato mensual a anual.
   - Potencial de reducción de churn del 42% al 11% en el segmento migrado.

2. **Programa de onboarding (primeros 6 meses)**
   - Check-ins mensuales durante el primer semestre.
   - Guía de uso del servicio y beneficios.
   - Objetivo: reducir el churn del 47% al 20% en este segmento.

3. **Paquete de seguridad incluido**
   - Incluir Online Security y Tech Support en el plan básico de Fiber Optic.
   - Costo bajo para la empresa, reducción de churn significativa (~27 puntos porcentuales).

### Prioridad Media

4. **Revisión de precios de Fiber Optic**
   - Evaluar si el precio es competitivo.
   - Considerar un plan de entrada con menos velocidad a menor precio.

5. **Incentivos en método de pago**
   - Descuento del 2-3% por usar débito automático o tarjeta de crédito.
   - Reducir la dependencia de Electronic Check.

### Prioridad Informativa

6. **Sistema de alertas tempranas**
   - Implementar scoring basado en las variables identificadas.
   - Activar retención proactiva cuando un cliente cruce umbrales de riesgo.

---

## Impacto Proyectado

| Escenario | Tasa de Churn | Clientes Retenidos | Ingreso Adicional/mes |
|---|---|---|---|
| Actual | 26.5% | — | — |
| Reducción al 22% | -4.5 pp | ~317 clientes | +$20,500 |
| Reducción al 18% | -8.5 pp | ~599 clientes | +$38,800 |
| Reducción al 15% | -11.5 pp | ~810 clientes | +$52,500 |

---

## Stack Tecnológico Utilizado

- **Python 3.10+**
- pandas, NumPy (manipulación y análisis)
- Matplotlib, Seaborn, Plotly (visualización)
- Jupyter Notebooks (documentación del análisis)

---

## Estructura del Análisis

| Notebook | Contenido |
|---|---|
| 01_exploracion_inicial | Carga, info general, estadísticas descriptivas, distribución de churn |
| 02_limpieza_datos | Duplicados, missing values, conversión de tipos, encoding |
| 03_analisis_univariado | Histogramas, boxplots, estadísticas por variable, skewness |
| 04_analisis_bivariado | Churn rate por variable categórica, correlaciones, interacciones |
| 05_conclusiones_viz | Tests de hipótesis, dashboard final, recomendaciones estratégicas |

---

*Para más detalles, revisar los notebooks en `/notebooks/` y las visualizaciones en `/visuals/`.*
