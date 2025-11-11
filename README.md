# Análisis de Cultivos Agrícolas

**Laboratorio I — Especialización en Análisis de Datos**

Este repositorio contiene el trabajo final del laboratorio I: un proceso completo de **ETL (Extracción, Transformación y Carga)** y un **EDA (Análisis Exploratorio de Datos)** sobre un dataset agrícola (1.000.000 de registros). El objetivo es analizar qué factores influyen en el rendimiento de cultivos y responder preguntas de negocio relevantes para la planificación agrícola.

## Abrir y ejecutar en Google Colab

Ejecutá el notebook directamente en Colab (recomendado — entorno ya preparado):

[![Abrir en Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/gonzalo2sotomayor/Analisis-Cultivos-Agricolas/blob/main/analisis_cultivos_agricolas.ipynb)

## Estructura del repositorio

- `analisis_cultivos_agricolas.ipynb` — Notebook principal (ETL, EDA, visualizaciones y preguntas de negocio).  
- `README.md` — Este archivo (documentación del proyecto).

## Resumen del proyecto

**Fuente de datos (ejemplo):** dataset público (uso educativo).  
**Tamaño:** 1.000.000 registros.  
**Lenguaje / Entorno:** Python (Google Colab).  
**Librerías principales:** `pandas`, `SQLAlchemy` y `seaborn`/`matplotlib` para visualizaciones).

## Qué incluye el notebook

### ETL (Extracción, Transformación y Carga)
- Montaje de Google Drive y lectura del CSV (detcción automática de encoding).
- Renombrado y traducción de columnas y categorías al español.
- Conversión de tipos (fechas), redondeo de variables numéricas y creación de variables derivadas (p. ej. `Estacion`).
- Verificación de duplicados/nulos y exportación del dataset limpio a `cultivos_agricolas_ok.csv` en Drive.

### EDA (Análisis Exploratorio de Datos)
- Revisión de estructura (`info()`, `describe()`, `head()`).
- Tablas de frecuencia y porcentajes de variables categóricas (`Region`, `Tipo_Suelo`, `Cultivo`, `Condiciones_Meteorologicas`, `Estacion`).
- Análisis agregado con `groupby()` y `pivot_table()`:
  - Rendimiento promedio por cultivo, por estación y por tipo de suelo.
  - Rendimiento según uso de riego y fertilizante (desglose por cultivo).
  - Días hasta la cosecha: análisis por cultivo, suelo y estación.

## Preguntas de negocio respondidas
El notebook formula y responde tres preguntas de negocio con tablas y gráficos. Entre ellas:

1. **¿Qué combinación de riego y fertilizante genera mayor rendimiento promedio?**  
   - Análisis `groupby()` y pivot table que compara combinaciones `Sí/No`.

2. **¿Cómo varía el rendimiento según tipo de suelo y condiciones meteorológicas?**  
   - Pivot table por tipo de suelo y condición climática.

3. **¿Cómo varía el rendimiento promedio por cultivo a lo largo del tiempo?**  
   - Tabla mensual + gráfico de líneas por cultivo (insights estacionales).

(El notebook contiene interpretaciones breves para cada resultado y recomendaciones prácticas.)
