# analysis-everpeak
# Movilidad urbana y productividad económica en Latinoamérica | Análisis 2024
# Descripción del proyecto
Este proyecto explora la relación entre la congestión vehicular y la productividad económica de ciudades latinoamericanas a partir de indicadores de movilidad de TomTom Traffic Index y datos económicos de OECD Cities.

El análisis se desarrolla en Python, desde la exploración y limpieza de datos hasta la integración de fuentes, la visualización de indicadores y la elaboración de recomendaciones para orientar futuras investigaciones sobre infraestructura de transporte.
Alcance: análisis exploratorio de 2024 sobre 15 ciudades de 7 países (Colombia, Perú, México, Argentina, Brasil, Uruguay y Chile). Los resultados no permiten establecer causalidad.

# Objetivo
Evaluar si las ciudades con mayores niveles de congestión presentan patrones diferenciados de PIB per cápita y detectar casos que merezcan análisis adicionales antes de priorizar inversiones en movilidad urbana.
# Tecnologías utilizadas
- Python: procesamiento y análisis.
- pandas: limpieza, agrupación e integración de datos.
- NumPy: soporte para operaciones numéricas.
- Matplotlib y Seaborn: visualización.
- Jupyter Notebook: desarrollo y documentación del análisis.
#Fuentes de datos
Fuente	                Archivo esperado	            Contenido
TomTom Traffic Index	  tomtom_traffic.csv	          Congestión, índices de tráfico y tiempos de viaje.
    OECD Cities	            oecd_city_economy.csv	    PIB per cápita, desempleo, población y calidad del aire.

Los archivos originales no están incluidos en el notebook adjunto. Su disponibilidad y condiciones de uso deben verificarse antes de publicarlos en el repositorio.
# Metodología
1. Exploración: carga de archivos CSV, inspección de columnas, tipos de datos y valores ausentes.
2. Limpieza: estandarización de nombres de columnas, conversión de fechas y normalización de formatos numéricos.
3. Selección temporal: extracción del año y filtrado de registros correspondientes a 2024.
4. Agregación: cálculo de promedios de movilidad por ciudad, país y año.
5. Integración: unión INNER JOIN por city y year, conservando los registros presentes en ambas fuentes.
6. Visualización: boxplot de congestión, histograma de PIB per cápita y gráfico de barras comparativo por ciudad.
7. Exportación: generación del conjunto integrado ladb_mobility_economy_2024_clean.csv.
Indicadores analizados
Indicador	Interpretación
jams_delay	Tiempo de congestión reportado en la fuente de tráfico.
traffic_index_live	Índice de tráfico.
jams_length_kms	Longitud de los congestionamientos en kilómetros.
jams_count	Número de congestionamientos registrados.
mins_delay	Minutos de retraso.
travel_time_live_per_10kms_mins	Tiempo de viaje observado por cada 10 km.
city_gdp_capita	PIB per cápita de la ciudad.
unemployment_pct	Indicador de desempleo.
population	Población estimada en habitantes.

# Principales hallazgos
- No se observó una relación visual directa y consistente entre PIB per cápita y congestión en las ciudades analizadas. Esta observación es descriptiva: el notebook no calcula coeficientes de correlación ni pruebas de significancia.
- Ciudad de México aparece con el mayor promedio de jams_delay en la agregación de tráfico de 2024, con aproximadamente 2.833 minutos según la revisión registrada en el notebook.
- El resumen ejecutivo identifica a São Paulo, Lima y Bogotá entre las ciudades que merecen una revisión más detallada de sus niveles de congestión.
- Bogotá y Lima se plantean como posibles candidatas para profundizar el diagnóstico de movilidad, sin que el análisis por sí solo justifique una decisión de inversión.
Recomendaciones
- Validar la calidad, las unidades y la comparabilidad de los indicadores antes de extraer conclusiones económicas.
- Investigar las causas de los niveles elevados de congestión en las ciudades destacadas.
- Incorporar información sobre transporte público, parque automotor, densidad urbana e infraestructura vial.
- Evaluar relaciones estadísticas y factores de confusión antes de formular hipótesis causales o priorizar inversiones.
Estructura sugerida del repositorio
movilidad-economia-latinoamerica/
├── README.md
├── everpeak_analysis.ipynb
├── data/
│   ├── tomtom_traffic.csv
│   └── oecd_city_economy.csv
└── outputs/
    └── ladb_mobility_economy_2024_clean.csv


La estructura anterior es una propuesta para GitHub; no representa archivos adicionales que ya se hayan generado o adjuntado. Los CSV originales solo deben publicarse si sus condiciones de uso lo permiten.

# Cómo ejecutar el proyecto
1. Clona o descarga el repositorio.
2. Instala Python y Jupyter Notebook, junto con las dependencias:
   pip install pandas numpy matplotlib seaborn notebook
3. Coloca los dos archivos CSV en una carpeta local data/, siempre que tengas autorización para utilizarlos.
4. Abre everpeak_analysis.ipynb y ajusta las rutas originales /datasets/tomtom_traffic.csv y /datasets/oecd_city_economy.csv a data/tomtom_traffic.csv y data/oecd_city_economy.csv, respectivamente.
5. Ejecuta las celdas en orden y revisa los gráficos y el CSV exportado.
Nota de reproducibilidad: el notebook fue desarrollado en un entorno con rutas /datasets/. Además, la revisión del proyecto detectó que la limpieza de city_gdp_capita podría alterar la escala de los valores al reejecutarse. Se recomienda corregir y validar esta transformación antes de utilizar el CSV final o publicar cifras económicas como resultados definitivos.
# Limitaciones
- Se estudia únicamente el año 2024.
- La integración por ciudad y año puede requerir validación adicional de nombres de ciudades y correspondencia entre fuentes.
- Las comparaciones visuales no demuestran correlación estadísticamente significativa ni causalidad.
- El gráfico de barras compara indicadores con unidades y escalas diferentes, por lo que debe interpretarse con cautela.
- Los resultados dependen de la consistencia de las fuentes y de las transformaciones aplicadas.
# Estado del proyecto
Proyecto académico aprobado
