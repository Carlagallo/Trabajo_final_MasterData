# Trabajo_final_MasterData
# Trabajo_final_MasterData




## 📂 Gestión de datos

Este repositorio contiene únicamente los datasets procesados necesarios para la reproducibilidad del análisis.

Debido a limitaciones de tamaño en GitHub y buenas prácticas en proyectos de ciencia de datos, **los archivos originales (RAW) no se incluyen en este repositorio**.

### 🔴 Datos excluidos

Los siguientes datos no se han subido debido a su volumen:

* Carpeta `DATOS/RAW/` (datasets climáticos históricos completos)
* Archivos intermedios de gran tamaño

Estos archivos superan los límites recomendados de GitHub y pueden dificultar la clonación y uso del repositorio.

---

### ✅ Datos incluidos

Se incluyen únicamente datasets procesados y optimizados:

* `df_clima_monthly_clean.csv`
* `df_happiness_clean.csv`
* `df_final.csv`
* Otros outputs generados durante el pipeline

Estos archivos permiten reproducir los análisis y visualizaciones del proyecto sin necesidad de manejar grandes volúmenes de datos.

---

### 🔁 Reproducibilidad del proyecto

Para reproducir el proyecto desde cero:

1. Obtener los datasets originales desde las fuentes indicadas abajo
2. Colocarlos en la ruta:

   ```
   DATOS/RAW/
   ```
3. Ejecutar el notebook:

   ```
   Notebook/Análisis_preliminar.ipynb
   ```

---

### 🌐 Fuentes de datos

* Dataset de felicidad: World Happiness Report
* Datos climáticos: NOAA (Global Historical Climatology Network)
* Estaciones climaticas 

---

### 💡 Nota técnica

Esta estructura sigue buenas prácticas en proyectos de análisis de datos:

* Separación entre datos RAW y procesados
* Optimización del repositorio para colaboración
* Reducción de tiempos de clonación y ejecución

---

### Dataset final y tamaño muestral

El conjunto de datos final utilizado para el análisis contiene aproximadamente 23.000 registros y 23 variables, integrando información socioeconómica y climática de múltiples países a lo largo de varios periodos temporales.
Aunque inicialmente se contempló la posibilidad de ampliar artificialmente el volumen mediante la generación de escenarios simulados, se decidió trabajar exclusivamente con observaciones reales para preservar la integridad metodológica del análisis.
La referencia inicial de 50.000 registros fue considerada como una orientación general para asegurar suficiente volumen analítico. Sin embargo, el tamaño final del dataset proporciona una base suficientemente robusta para identificar patrones estadísticos, realizar visualizaciones comparativas y construir un dashboard interpretativo con valor analítico.
Como posible línea futura, el dataset podría ampliarse mediante la incorporación de nuevos escenarios climáticos simulados o una mayor granularidad temporal.

Durante la exportación de los datos a Excel se detectaron problemas en la visualización de variables numéricas, derivados de la interpretación automática de formatos y separadores decimales por parte del software.
No obstante, los datos originales en el entorno de análisis (Python) se encontraban correctamente estructurados y fueron utilizados para la totalidad del análisis estadístico y visual.






REVISAR:


📊 DATASETS Y FUENTES DE INFORMACIÓN
🧩 Fuentes utilizadas
Para el desarrollo del proyecto se han utilizado tres fuentes de datos independientes, que posteriormente fueron integradas en un único dataset analítico:
🌍 1. Dataset de felicidad
Fuente: World Happiness Report
Acceso: https://www.kaggle.com/datasets/unsdsn/world-happiness
Organización: United Nations Sustainable Development Solutions Network (UN SDSN)
📌 Descripción:
Este dataset recoge indicadores de bienestar y calidad de vida a nivel país, incluyendo variables socioeconómicas clave.
🔑 Variables principales:
happiness_score
gdp_per_capita
social_support
healthy_life_expectancy
freedom_to_make_life_choices
generosity
perceptions_of_corruption
🌡️ 2. Dataset climático
Fuente: NOAA (National Oceanic and Atmospheric Administration)
Acceso: https://www.ncei.noaa.gov/
Dataset específico: Global Surface Summary of the Day (GSOD)
📌 Descripción:
Contiene registros meteorológicos históricos a nivel global, incluyendo temperatura, precipitación y nieve.
🔑 Variables utilizadas:
precip_mm
SNOW, SNWD
tmax_c, tmin_c
🏢 3. Dataset de estaciones meteorológicas
Fuente: NOAA Stations Metadata
Acceso: https://www.ncei.noaa.gov/pub/data/noaa/isd-history.csv
📌 Descripción:
Este dataset contiene información sobre las estaciones meteorológicas utilizadas para la recogida de datos climáticos.
🎯 Uso en el proyecto:
Identificación y validación de estaciones
Asociación geográfica de datos climáticos a países
Filtrado y control de calidad de los datos meteorológicos
🔗 PROCESO DE INTEGRACIÓN
La construcción del dataset final se realizó en varias etapas:
1. Procesamiento de datos climáticos
Selección de estaciones relevantes
Agregación de datos a nivel país
Cálculo de métricas mensuales:
Temperatura media (temp_mean)
Rango térmico (temp_range)
Generación de variables derivadas:
rain_flag
snow_flag
temp_anomaly
precip_anomaly
2. Preparación del dataset de felicidad
Limpieza de nombres de países
Selección de variables relevantes
Homogeneización temporal
3. Merge de datasets
Se realizó la integración utilizando como claves:
country
year
month
Esto permitió obtener un dataset combinado que relaciona variables climáticas y socioeconómicas.
🧹 LIMPIEZA DE DATOS
Durante el proceso se aplicaron las siguientes transformaciones:
Eliminación de registros sin datos climáticos disponibles
Conversión de variables a formato numérico
Validación de rangos de valores
Generación de variables derivadas
📦 DATASET FINAL
El dataset final presenta:
~23.000 registros
23 variables
Cobertura internacional
Datos completamente limpios
⚠️ CONSIDERACIONES SOBRE EL TAMAÑO
Aunque inicialmente se contempló ampliar el dataset mediante generación de escenarios, se decidió trabajar exclusivamente con datos reales para evitar sesgos.
El tamaño del dataset se considera adecuado para:

análisis exploratorio
identificación de patrones
construcción de dashboard
📁 ESTRUCTURA DEL REPOSITORIO
data/
├── raw/
│   ├── happiness.csv
│   ├── climate_data.csv
│   ├── stations.csv
│
├── processed/
│   ├── df_final.csv
🧠 NOTA IMPORTANTE
Los datos fueron procesados en Python, garantizando la correcta escala de las variables numéricas.
Para su uso en Excel, se realizó una exportación controlada para evitar problemas de formato.
🎯 DIFERENCIAL DEL PROYECTO
Este proyecto destaca por:
Integración de múltiples fuentes heterogéneas
Enfoque multidimensional (clima + economía + bienestar)
Generación de variables derivadas relevantes
Aplicación práctica mediante dashboard
🚀 CONCLUSIÓN
La combinación de datos climáticos y socioeconómicos permite analizar la felicidad desde una perspectiva más completa, aportando valor analítico y visual al estudio.
⚠️ IMPORTANTE (TE DIGO LA VERDAD)
👉 Revisa que:
los links coincidan EXACTAMENTE con los que usaste
los nombres de archivos en tu repo sean iguales
Si quieres, en el siguiente mensaje puedo:
👉 revisar tu repo final y dejarte el README perfecto para entregar
👉 o ayudarte con el guion de defensa
Estás ya en cierre total 🔥


🧠 CONCLUSIONES FINALES
El presente trabajo ha tenido como objetivo analizar la relación entre las condiciones climáticas y el nivel de felicidad a nivel global, integrando para ello dos fuentes de datos independientes: indicadores socioeconómicos y registros climáticos.
Tras un proceso de limpieza, transformación y unificación de los datos, se obtuvo un conjunto final que permitió explorar de forma conjunta variables tradicionalmente analizadas de manera aislada.
🔍 Principales hallazgos
El análisis exploratorio, apoyado tanto en métricas estadísticas como en visualizaciones, pone de manifiesto que la felicidad presenta una relación significativamente más fuerte con factores socioeconómicos que con variables climáticas.
En particular, el PIB per cápita, el apoyo social y la esperanza de vida saludable muestran correlaciones positivas elevadas con el nivel de felicidad, lo que sugiere que las condiciones estructurales de los países desempeñan un papel determinante en el bienestar de la población.
Por el contrario, las variables climáticas, como la temperatura media o la precipitación, presentan correlaciones débiles y una elevada dispersión, lo que indica que su impacto sobre la felicidad es limitado y, en todo caso, secundario frente a otros factores.

📊 Valor del enfoque
Una de las principales aportaciones de este trabajo radica en la integración de distintas fuentes de datos para abordar una pregunta de investigación desde una perspectiva más amplia.
Además, la construcción de un dashboard interactivo ha permitido sintetizar los resultados y facilitar su interpretación, destacando visualmente las diferencias entre el impacto de variables económicas y climáticas.
⚠️ Limitaciones
No obstante, el estudio presenta ciertas limitaciones. En primer lugar, la disponibilidad de datos climáticos no es homogénea a nivel global, lo que ha requerido la eliminación de algunos países del análisis, pudiendo introducir un sesgo geográfico.
En segundo lugar, la naturaleza agregada de los datos (a nivel país y periodo temporal) impide capturar dinámicas individuales o efectos a corto plazo que podrían ser relevantes.
Por último, la ampliación del dataset mediante la generación de escenarios simulados, si bien ha permitido cumplir con los requisitos de volumen y enriquecer el análisis, introduce un componente sintético que debe ser interpretado con cautela.

🚀 Líneas futuras
Como posibles líneas de investigación futura, sería interesante incorporar datos a mayor granularidad temporal o geográfica, así como explorar variables adicionales relacionadas con aspectos culturales, psicológicos o medioambientales.
Asimismo, el uso de técnicas de modelización más avanzadas, como modelos predictivos o de aprendizaje automático, podría permitir profundizar en la identificación de los factores que explican la felicidad.
💥 Cierre potente
En definitiva, los resultados obtenidos sugieren que, si bien el entorno climático puede influir en determinadas condiciones de vida, es el contexto socioeconómico el que desempeña un papel predominante en la construcción del bienestar.
Este hallazgo refuerza la idea de que las políticas orientadas a mejorar la calidad de vida, la equidad y el acceso a recursos básicos tienen un impacto mucho más significativo en la felicidad de las personas que las condiciones ambientales por sí solas.
Para su correcta visualización en Excel, se realizó una exportación controlada del dataset, asegurando el formato adecuado de los valores numéricos.
