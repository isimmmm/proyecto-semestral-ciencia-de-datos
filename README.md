# Rol del nivel socioeconómico en el impacto del COVID-19 en la Región Metropolitana, Chile.

Este proyecto investiga cómo el nivel socioeconómico de las comunas se relacionó con el impacto del Covid-19. El análisis busca identificar patrones y brechas sociales que surgieron durante la pandemia, examinando variables clave que incluyen tipos de previsión de salud como indicador de desigualdad estructural. El objetivo es comprender cómo las condiciones socioeconómicas influyeron en los resultados sanitarios durante la crisis.

## Estructura

```bash
proyecto/
├── data/                   # Archivos de datos (procesados)
├── notebooks/              # Notebooks con análisis exploratorio y modelamiento
├── figures/                # Imágenes y visualizaciones generadas
├── web/                    # Archivos para GitHub Pages
└── README.md               # Descripción general del proyecto
```

## Bases de datos (fuentes)

- [COVID-19 de OBSERVA, Gobierno de Chile](https://observa.minciencia.gob.cl/datos-abiertos/datos-del-repositorio-covid-19).
- [Encuesta Nacional de Caracterización Socioeconómica CASEN 2017](https://observatorio.ministeriodesarrollosocial.gob.cl/encuesta-casen-2017).
- [CENSO 2017, del Instituto Nacional de Estadísticas Chile (INE)](https://censo2024.ine.gob.cl/estadisticas-2017/).
- [CENSO 2024, del Instituto Nacional de Estadísticas Chile (INE)](https://censo2024.ine.gob.cl/estadisticas/).
- [Encuesta Nacional de Caracterización Socioeconómica CASEN 2020](https://observatorio.ministeriodesarrollosocial.gob.cl/encuesta-casen-en-pandemia-2020).
- [Encuesta Nacional de Caracterización Socioeconómica CASEN 2022](https://observatorio.ministeriodesarrollosocial.gob.cl/encuesta-casen-2022).
- [Superintendencia de Salud: Egresos hospitalarios del sistema ISAPRE, por diagnóstico y tipo de prestador](https://www.superdesalud.gob.cl/biblioteca-digital/estadistica-anual-de-egresos-hospitalarios-del-sistema-isapre-ano-2023/).
- [Departamento de Estadísticas e Información de Salud (DEIS): Egresos hospitalarios del sistema público (FONASA)](https://deis.minsal.cl/#datosabiertos).

## Herramientas utilizadas y necesarias

- Lenguaje de programación: Python.
- JupyterNotebooks para la exploración y limpieza de datos.
- Matplotlib / Seaborn para la visualización de datos.
- Statsmodels (sm) para el modelo estadístico.
- Numpy, pandas, geopandas para la lectura de datos y apoyo para tranformar datos al graficarlos.

## Recreación del proyecto

Cada carpeta contiene los pasos a seguir para recrear este proyecto por cuenta propia.

## Declaración de uso de IA

Se utilizaron herramientas de Inteligencia Artificial Generativa (Deepseek/ChatGPT) para generar el código .html a partir de un documento .md, y como pequeño apoyo para el código de regresión lineal en notebooks/Notebook_principal.

## Equipo de trabajo y roles

**Daniela Cerda:**
- Responsable de la lectura y limpieza de las bases de datos _Egresos hospitalarios del sistema ISAPRE, por diagnóstico y tipo de prestador y Departamento de Estadísticas e Información de Salud (DEIS)_, trabajo visible en [Data/prestadores de salud].
- EDA y análisis de las bases de datos mencionadas con anterioridad en el notebook: [notebooks/Análisis (notebooks)/Analisis-prestadores-de-salud.ipynb].
- Participación activa en la discusión metodológica y en el análisis del equipo respecto a la pregunta a responder.
- Colaboración en el notebook grupal de exploración de datos en conjunto [notebooks/Análisis (notebooks)/Notebook_exploratorio_conjunto.ipynb], aportando gráficos y análisis.
- Desarrollo conceptual y orden lógico del proyecto.
- Aporte directo al Notebook_principal.ipynb. donde se encuentra el análisis y la respuesta principal del proyecto [notebooks/Notebook_principal.ipynb].

**Liz González:**
- Responsable de la lectura y limpieza de las bases de datos _Encuesta Nacional de Caracterización Socioeconómica Casen 2017, 2020 y 2022_, trabajo visible en [Data/Nivel socioeconomico y geografico].
- Realizadora del modelo estadístico en notebook_principal.ipynb.
- EDA y análisis de las bases de datos mencionadas con anterioridad en el notebook: [notebooks/Análisis (notebooks)/Analisis_de_datos_Socioeconomicos y Geograficos.ipynb].
- Participación activa en la discusión metodológica y en el análisis del equipo respecto a la pregunta a responder.
- Colaboración en el notebook grupal de exploración de datos en conjunto [notebooks/Análisis (notebooks)/Notebook_exploratorio_conjunto.ipynb], aportando gráficos y análisis.
- Aporte directo al Notebook_principal.ipynb. donde se encuentra el análisis y la respuesta principal del proyecto [notebooks/Notebook_principal.ipynb].

**Isidora Mora:**
- Responsable de la lectura y limpieza de las bases de datos _Datos del Repositorio COVID-19_, trabajo visible en [Data/Covid-19].
- Responsable de la lectura de las bases de datos _Censo 2017 y 2024_, creando una estimación de la población en los años intermedios, trabajo visible en [Data/censo].
- EDA y análisis de las bases de datos mencionadas con anterioridad en el notebook: [notebooks/Análisis (notebooks)/Analisis-de-datos-Covid-19.ipynb].
- Participación activa en la discusión metodológica y en el análisis del equipo respecto a la pregunta a responder.
- Colaboración en el notebook grupal de exploración de datos en conjunto [notebooks/Análisis (notebooks)/Notebook_exploratorio_conjunto.ipynb], aportando gráficos y análisis.
- Aporte directo al Notebook_principal.ipynb. donde se encuentra el análisis y la respuesta principal del proyecto [notebooks/Notebook_principal.ipynb]

**Benjamín Ubilla:**
- No realiza aportes al proyecto grupal.
