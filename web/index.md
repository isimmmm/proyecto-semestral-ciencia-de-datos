# Proyecto de Ciencia de Datos  
## ¿Cuál es la relación entre el nivel socioeconómico comunal y el impacto del COVID-19 en la Región Metropolitana?

Bienvenido a la página web del proyecto. Este sitio resume los principales hallazgos del análisis realizado sobre la relación entre el nivel socioeconómico comunal y el impacto del COVID-19 en la Región Metropolitana de Chile.  
Aquí encontrará información relevante del estudio, incluyendo nuestra motivación, visualizaciones, factores clave, hallazgos y más.

---

## Introducción

Diversos informes del **Ministerio de Salud (DEIS, 2020)** y estudios como el de **Mena et al. (2021)**, publicado en *Science*, han sugerido posibles diferencias en el impacto del COVID-19 entre comunas con distintos niveles socioeconómicos. Sin embargo, estos análisis se han enfocado principalmente en aspectos generales de mortalidad o contagio, sin integrar variables como vacunación, movilidad o cobertura de testeo, ni examinar cómo interactúan estas dimensiones en el contexto comunal.

Por ello, este proyecto busca **integrar esa relación**, utilizando datos abiertos y actualizados para determinar con mayor precisión si el nivel socioeconómico de las comunas de la Región Metropolitana se asoció al impacto del COVID-19, considerando tanto los efectos sanitarios como las condiciones sociales que podrían explicarlos.

Analizar cómo varió el impacto del COVID-19 según el nivel socioeconómico comunal permite comprender mejor las **brechas sociales que la crisis sanitaria amplificó**. Este proyecto busca **identificar patrones y relaciones** entre variables como pobreza, mortalidad, vacunación, movilidad y cobertura de testeo en las comunas de la Región Metropolitana entre 2020 y 2022 para poder responder la pregunta principal: **¿Cuál es la relación entre el nivel socioeconómico comunal y el impacto del COVID-19 en la Región Metropolitana?**

---
## Metodología del proyecto

El proyecto tuvo un enfoque completo de análisis de datos, iniciando con la obtención y limpieza de los datos, hasta llegar a la generación de visualizaciones y conclusiones. Siempre con el objetivo de evaluar la relación entre el nivel socioeconómico comunal y el impacto del COVID-19 en la Región Metropolitana de Chile.

El estudio se desarrolló en las siguientes etapas:

### 1. Recolección de datos:
Se integraron múltiples fuentes públicas:
- [COVID-19 de OBSERVA, Gobierno de Chile](https://observa.minciencia.gob.cl/datos-abiertos/datos-del-repositorio-covid-19).
- [Encuesta Nacional de Caracterización Socioeconómica CASEN 2017](https://observatorio.ministeriodesarrollosocial.gob.cl/encuesta-casen-2017).
- [CENSO 2017, del Instituto Nacional de Estadísticas Chile (INE)](https://censo2024.ine.gob.cl/estadisticas-2017/).
- [CENSO 2024, del Instituto Nacional de Estadísticas Chile (INE)](https://censo2024.ine.gob.cl/estadisticas/).
- [Encuesta Nacional de Caracterización Socioeconómica CASEN 2020](https://observatorio.ministeriodesarrollosocial.gob.cl/encuesta-casen-en-pandemia-2020).
- [Encuesta Nacional de Caracterización Socioeconómica CASEN 2022](https://observatorio.ministeriodesarrollosocial.gob.cl/encuesta-casen-2022).
- [Superintendencia de Salud: Egresos hospitalarios del sistema ISAPRE, por diagnóstico y tipo de prestador](https://www.superdesalud.gob.cl/biblioteca-digital/estadistica-anual-de-egresos-hospitalarios-del-sistema-isapre-ano-2023/).
- [Departamento de Estadísticas e Información de Salud (DEIS): Egresos hospitalarios del sistema público (FONASA)](https://deis.minsal.cl/#datosabiertos).
- Mapa GeoJSON para construir gráfico territorial que se obtuvo de: https://github.com/fcortes/Chile-GeoJSON/blob/master/comunas.geojson



### 2. Proceso ETL:
- **Extracción:** Se importaron las distintas bases de datos y cada archivo fue cargado en un DataFrame independiente para su exploración inicial.

- **Transformación:** Se realizó homologación de nombres de comunas entre distintas fuentes, conversión de tipos de datos, cálculo de indicadores, agrupación y cálculo de promedios por comuna, eliminación de duplicados, manejo de valores faltantes y unión de tablas por la columna común "Comuna".

- **Carga:** Los datos una vez limpios se intergraron en un DataFrame según su información (df_covid, df_nse, df_prestadores, df_censo). Esto nos permitió relacionar variables y generar las visualizaciones necesarias para analizar y connstruir comparaciones.


### 3. Visualización y análisis:
Se crearon distintos gráficos y visualizaciones:
- mapas territoriales por comuna
- gráficos de barras y dispersión
- análisis correlacional
- gráficos comparativos por año
- relaciones entre variables.
El análisis combinó estadísticas descriptivas con interpretación contextual para entender desigualdades estructurales entre comunas adineradas y vulnerables.


### 4. Interpretación y conclusiones:
A partir de la exploración visual y analítica se identificaron patrones consistentes:
- mayor vacunación y testeo en comunas ricas
- mayor mortalidad proporcional en comunas vulnerables
- relación inversa entre ingresos y mortalidad,
- relación directa entre pobreza y mortalidad.
Estos hallazgos se integraron para responder la pregunta central del proyecto.

---

## Visualizaciones principales del análisis


### Fallecidos de Covid-19 por comuna
![Fallecidos por comuna](../figures/fallecidos_por_comuna_covid-19.png)

Las 5 comunas más afectadas a nivel de mortalidad por el covid-19 han sido San Ramón, Cerro Navia, Pedro Aguirre Cerda, Independencia y Lo Espejo. Las 5 menos afectadas han sido San Pedro, Lo Barnechea, Colina, Santiago y Lampa.

---

### Porcentaje de vacunación por comuna  
![Vacunación](../figures/vacunados_por_comuna_porcentaje.png)

Las comunas ricas presentan mayor vacunación y las más pobres, menor cobertura.

---

### Mapa de NSE Predominante en la RM  
![Mapa NSE](../figures/mapa_nse_rm.png)

El mapa evidencia la desigual distribución territorial del nivel socioeconómico.

---

### Correlación de positividad vs mortalidad  
![Positividad](../figures/corr_positividad_vs_mortalidad_covid_19.png)

Podemos notar que mientras más PCR positivos, menos mortalidad (–0.51). Además mientras más % casos confirmados, nuevamente menos mortalidad (–0.61).
Esto puede ocurrir porque comunas de mayor NSE testean mucho más, detectan más casos leves, y tienen menos mortalidad. Por lo mismo la positividad baja puede significar mucho testeo, no pocos contagios.
Este gráfico es clave para entender que la mortalidad se asocia un poco más a diagnóstico que a contagios.

---

### 📉 Ingreso Promedio vs Mortalidad  
![Ingreso](../figures/ingreso.png)

Ingreso y mortalidad están inversamente correlacionados:  
**a menor ingreso, mayor mortalidad**.

---

## 🧠 Principales Hallazgos

El análisis revela una relación clara entre **desigualdad socioeconómica** y **resultado sanitario** durante la pandemia:

- Las comunas pobres tuvieron **mayor mortalidad**, **menos testeo** y **menor vacunación**.  
- Las comunas ricas mostraron **mejor cobertura de vacunación**, **más testeo** y **menor mortalidad**.  
- La vacunación por sí sola **no explica la mortalidad**; el acceso a salud, la edad, el testeo y la vulnerabilidad social son factores críticos.  
- El **testeo es un mediador relevante**: más testeo significa más detección temprana y menor mortalidad proporcional.  
- Ingreso y NSE están altamente correlacionados con mortalidad, reforzando la presencia de brechas estructurales.

---

## ⚠️ ¿Qué podría salir mal?

Este análisis tiene limitaciones que deben considerarse:

- **Subdiagnóstico** en comunas con bajo testeo distorsiona la mortalidad real.  
- Falta de variables clave como edad, comorbilidades o densidad poblacional.  
- Correlaciones no implican causalidad; simplificarlas puede llevar a políticas equivocadas.  
- Modelos basados en datos incompletos pueden reproducir desigualdades, como se discute en *Weapons of Math Destruction*.  
- Las conclusiones pueden ser malinterpretadas si se usan para justificar recortes o priorizaciones injustas.  

Es esencial que cualquier decisión basada en estos resultados considere la ética, la equidad y el contexto territorial.

---

## 📁 Enlaces relevantes

🔗 **Notebook del análisis:**  
[Notebook_principal.ipynb](../Notebook_principal.ipynb)

🔗 **Repositorio en GitHub:**  
*(agrega aquí la URL de tu repo)*

---

## 👥 Equipo

- Integrante 1  
- Integrante 2  

---

Gracias por visitar este sitio.  
Este proyecto fue realizado como parte del curso de Ciencia de Datos (2025).
