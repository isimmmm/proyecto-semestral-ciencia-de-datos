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

### Correlación entre mortalidad y variables económicas
![Mortalidad vs economía](../figures/corr_tasa_mortalidad_vs_variables_socio.png)

Ingreso y mortalidad están inversamente correlacionados (a menor ingreso, mayor mortalidad). Además, mortalidad e índice de pobreza tienen una correlación positiva, es decir, a mayor pobreza, mayor mortalidad.

---

## Principales Hallazgos

El análisis realizado manifiesta que la desigualdad socioeconómica en la Región Metropolitana de Chile tiene un impacto directo y profundo en la distribución del impacto sanitario del COVID-19, especialmente en términos de vacunación, mortalidad y testeo. Las comunas más vulnerables, caracterizadas por un bajo nivel socioeconómico (NSE) y menores ingresos, han experimentado un mayor impacto de la pandemia, reflejando las desigualdades estructurales del sistema de salud y el acceso limitado a servicios de atención médica. En contraste, las comunas más ricas, con un NSE alto, han mostrado menores tasas de mortalidad, mayor acceso a las vacunas, mejores recursos sanitarios y mayor testeo, lo que ha permitido detectar y tratar los casos de manera más eficiente.

Aunque la relación entre vacunación y mortalidad se muestra débil, los gráficos indican que la mortalidad no puede explicarse únicamente por la vacunación. Otros factores, como la edad de la población, el testeo y la calidad del sistema de salud, juegan un papel crucial en determinar los resultados sanitarios. En particular, notamos que a pesar de que la cobertura de casos sospechosos fue excepcional en todas las comunas, aún así el testeo se revela como un mediador clave, ya que las comunas con mayores tasas de testeo logran detectar más casos y, por lo tanto, mantienen una menor mortalidad proporcional. Esto subraya la importancia de diagnosticar a tiempo y prevenir el subdiagnóstico, lo que indirectamente ayuda a salvar vidas al permitir intervenciones más rápidas.

Por otro lado, los análisis sobre el impacto de los sistemas de salud privados (isapre) y públicos (fonasa) no han proporcionado conclusiones definitivas debido a la baja representatividad de las muestras en las comunas donde predomina isapre. Esto deja abierta la pregunta sobre la efectividad comparativa entre estos sistemas en la lucha contra la pandemia, aunque los resultados actuales no permiten inferir causalidad.

En resumen, el estudio confirma que las diferencias socioeconómicas entre comunas tienen un efecto directo en la mortalidad por COVID-19. Las comunas más vulnerables sufren peores resultados sanitarios debido a una combinación de factores como el bajo testeo, el acceso limitado a servicios médicos y la alta vulnerabilidad social. Si bien la vacunación es un factor importante en la reducción de la mortalidad, su impacto está condicionado por la presencia de otros determinantes sociales de la salud. Este análisis subraya la necesidad de una intervención más equitativa en la distribución de recursos sanitarios, con un enfoque especial en las comunas de mayor pobreza, para reducir las desigualdades en salud y mitigar el impacto de futuras crisis sanitarias.

---

## ¿Cuál es la relación entre el nivel socioeconómico comunal y el impacto del COVID-19 en la Región Metropolitana de Chile?**

La relación entre el nivel socioeconómico comunal y el impacto del COVID-19 en la Región Metropolitana de Chile es clara: las comunas con menor NSE y menores ingresos han sufrido un mayor impacto sanitario, con más muertes y menor acceso a recursos sanitarios. Esto se debe a múltiples factores, como el bajo testeo, el acceso limitado a atención médica y las condiciones sociales que agravan el riesgo de contagio. Por el contrario, las comunas con mayor NSE y mayores ingresos han tenido un menor impacto, gracias a un mayor acceso a vacunas, mejor calidad del sistema de salud y mayores recursos para prevenir y tratar la enfermedad. Por lo tanto, la desigualdad socioeconómica juega un rol crucial en el impacto del COVID-19, afectando la mortalidad y la capacidad de respuesta sanitaria en las comunas más vulnerables.

---
## ¿Qué podría salir mal?

Aunque el análisis realizado proporciona una visión valiosa sobre la relación entre el nivel socioeconómico y el impacto del COVID-19 en la Región Metropolitana de Chile, existen algunas limitaciones y sesgos que deberían ser considerados si se quiere interpretar los resultados y al implementar cualquier tipo de solución basada en este análisis.

- Subdiagnóstico y falta de datos completos:
Un problema clave es el subdiagnóstico de los casos de COVID-19. En las comunas con menos recursos, el acceso a pruebas y la capacidad de diagnóstico son limitados, lo que significa que el número real de casos podría ser mucho mayor de lo reportado. Este sesgo puede llevar a subestimar la mortalidad o la distribución de los casos en ciertas áreas, distorsionando la interpretación de la relación entre vacunación y mortalidad. Al basarse en datos incompletos o no representativos, las conclusiones pueden ser erróneas, afectando la toma de decisiones políticas o de salud pública.

- Falta de variables:
Aunque se identificaron factores importantes como la vacunación y el nivel socioeconómico, muchas otras variables confusoras podrían haber influido en los resultados. Factores como la edad de la población, las enfermedades preexistentes, el acceso a atención médica, no fueron evaluados. Estos factores podrían estar influyendo de manera significativa en la mortalidad por COVID-19 y no fueron controlados en el análisis. Como se menciona en el libro Weapons of Math Destruction, la falta de variables adecuadas y la simplificación de modelos pueden exacerbar las desigualdades, especialmente cuando se hacen recomendaciones basadas en modelos o datos incompletos.

- Riesgo de la automatización y los modelos predictivos:
Actualemente la inteligencia artificial y los modelos predictivos se usan cada vez más en la toma de decisiones, es importante recordar que el uso de algoritmos sin transparencia o sin una supervisión adecuada puede perpetuar sesgos y agravar las desigualdades. Si las recomendaciones para asignar recursos (como vacunas, pruebas o tratamiento) se basan en modelos matemáticos sin tener en cuenta los contextos locales o las desigualdades previas, estos modelos pueden reproducir las mismas injusticias que se buscan corregir, al centrarse en la eficiencia sin considerar las implicaciones sociales y éticas.

En resumen, aunque este análisis proporciona información valiosa sobre el impacto del COVID-19 y la relación con el nivel socioeconómico, las limitaciones de los datos y los sesgos inherentes en los modelos utilizados deben ser cuidadosamente considerados antes de implementar políticas basadas en estos resultados. Es fundamental que cualquier solución propuesta tenga en cuenta la distribución equitativa de recursos, la prevención de futuros sesgos y una visión inclusiva y justa que no profundice las desigualdades existentes. El uso de modelos predictivos y decisiones basadas en datos debe ir acompañado de una supervisión ética y de una evaluación crítica de las posibles consecuencias no deseadas que podrían surgir, y siempre comprendiendo que los problemas sociales son multi-factoriales, no pueden ser simplificados, y merecen un estudio cuidadoso y profundo de causales y planeación.

---

## Equipo

- Liz González
- Isidora Mora 
- Daniela Cerda 

---