# 📉 Analisis de CHURN de Clientes — Telecom Industry

[![Python](https://img.shields.io/badge/Python-3.10+-blue.svg)]()
[![Pandas](https://img.shields.io/badge/Pandas-2.3-green.svg)]()
[![Numpy](https://img.shields.io/badge/Numpy-2.2-green.svg)]()
[![Matplotlib](https://img.shields.io/badge/Matplotlib-3.10-green.svg)]()
[![Seaborn](https://img.shields.io/badge/Seaborn-0.13-green.svg)]()
[![Plotly](https://img.shields.io/badge/Plotly-6.6-green.svg)]()
[![Status](https://img.shields.io/badge/Status-Completo-brightgreen.svg)]()


## Descripción
Actualmente me desempeño como Analista GTR (Gestión de Tiempo Real) 
en una empresa de BPO/Call Center. Mi interés en este dataset surge de la 
similitud directa entre las métricas de retención de clientes y las 
problemáticas operativas que gestiono a diario.
Este proyecto realiza un Análisis Exploratorio de Datos (EDA) sobre 
una base de clientes de una empresa de telecomunicaciones, con el 
objetivo de comprender los patrones de comportamiento asociados al 
abandono del servicio (churn).

## Problema de Negocio
Adquirir un nuevo cliente cuesta entre 5 y 7 veces más que retener 
uno existente. Identificar a tiempo los clientes con alta probabilidad 
de abandonar permite implementar estrategias de retención focalizadas 
y reducir el impacto económico del churn.

## Estructura del Repositorio
📁 data/          → Dataset original y procesado  
📁 notebooks/     → 5 notebooks (exploración → conclusiones)  
📁 visuals/       → Gráficos exportados del análisis  
📁 reports/       → Informe ejecutivo con recomendaciones  
📄 README.md      → Documentación del proyecto  

## Hallazgos Principales
- **Tasa de churn:** 26.5% (~1.869 clientes, ~$120.000/mes en riesgo).
- **Tipo de contrato:** Clientes con contrato mensual abandonan 14x más (42%) que los de contrato bianual (3%).
- **Servicios contratados:** Fiber Optic duplica el churn (42% vs 19% en DSL). Ausencia de Online Security o Tech Support eleva el churn a ~42%.
- **Antigüedad:** Los primeros 6 meses son críticos (~47% de churn). Después del año, la tasa cae a ~10%.
- **Correlaciones:** Tenure (-0.35) y MonthlyCharges (+0.19) son las variables numéricas más asociadas al churn.

## Conclusiones y Recomendaciones

El análisis permite construir un perfil del cliente en riesgo:
contrato mensual + Fiber Optic + sin servicios de seguridad/soporte
+ antigüedad < 6 meses + pago con Electronic Check.

### Recomendaciones
1. **Migrar contratos** mensuales a anuales/bianuales con incentivos.
2. **Programa de onboarding** intensivo durante los primeros 6 meses.
3. **Incluir** Online Security y Tech Support en el plan básico.
4. **Revisar precios** de Fiber Optic frente a la competencia.
5. **Incentivar** débito automático o tarjeta sobre Electronic Check.

> Ver detalle completo en [`reports/informe_ejecutivo.md`](reports/informe_ejecutivo.md)

## Stack Tecnológico
`Python` `Pandas` `NumPy` `Matplotlib` `Seaborn` `Plotly`

## Dataset
- Fuente: IBM Telco Customer Churn (disponible en Kaggle)
- Registros: 7.043 clientes
- Variables: 21 (demográficas, de contrato, de servicio y target)
- Variable objetivo: `Churn` (Sí/No)

## Cómo ejecutar
1. Clonar el repositorio
2. `pip install -r requirements.txt`
3. Ejecutar notebooks en orden numérico

## Autor
Nahuel Caero | [[LinkedIn](https://www.linkedin.com/in/nahuel-agustin-caero/)] | [[GitHub](https://github.com/Caero-Nahuel/)]