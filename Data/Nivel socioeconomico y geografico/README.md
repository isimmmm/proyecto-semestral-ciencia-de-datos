# Contenido Carpeta
En la caparta 'Nivel Socioeconomico y Geografico' se encuentra distribuida en dos capartes con los archivos a utilizar para el proyecto, en la carpeta 'Datos Pandemia 2020-2022' y en la carpeta 'Datos post pandemia 2022-2023'.

# Base de Datos 
En esta carpeta se encuenstran los archivos de datos a utilizar, en este caso se usara la base de datos de la Encuesta Nacional de Caracterización Socioeconómica Casen. Los objetivos de la encuesta son: conocer la situación de la población respecto de pobreza e ingresos, identificar carencias en las áreas de educación, salud, vivienda, trabajo e ingresos; evaluar brechas de pobreza e ingresos según variables demográficas y territoriales; y estimar la cobertura/focalización del gasto fiscal en subsidios a los hogares. Dado lo anterio, se escogio la version 'CASEN En Pandemia 2020' y 'CASEN 2022'.

## Descripcion CASEN EN PANDEMIA 2020
Dada la afectación de la pandemia en el empleo y los ingresos, la encuesta se centra en este aspecto como su eje principal. El trabajo de campo se realizo entre septiembre de 2020 a enero del 2021
## Descripcion CASEN 2022
La encuesta en cuenta con una nueva medición de la pobreza multidimensional, la cual no ha sido calculada desde 2017, entregando datos clave para el proceso de recuperación económica y social luego de la pandemia. El trabajo de campo se realizó entre noviembre del 2022 a enero del 2023.

# Instalación y Limpieza
Los archivos originales de los datos estan en formato STATA por lo que se debio leer y transformar en formato csv mediante pandas para mayor comodidad, por lo que si se desea acceder a la base de datos puede hacerlo mediante los siguientes links: 
- CASEN EN PANDEMIA 2020 : https://observatorio.ministeriodesarrollosocial.gob.cl/encuesta-casen-en-pandemia-2020
- CASEN 2022 : https://observatorio.ministeriodesarrollosocial.gob.cl/encuesta-casen-2022
Por otro lado la limpieza de los datos y la creacion de los dataframes se puede realizar en los notebooks disponibles en cada seccion de las carpetas.

# Arachivos Datos Pandemia 2020 - 2021
* CASEN_PANDEMIA_2020.csv : Dataframe original en csv.
* CASE_PANDEMIA_POBREZA_GEOGRAFICA_2020.csv : Dataframe creado a partir del original con varibles de interes para el proyecto. Presenta las siguientes variables:
 - folio - Identificador único del hogar
 - id_persona - Identificador de persona dentro del hogar
 - provincia - Código de provincia
 - comuna - Código de comuna
 - pobreza - Situación de pobreza por ingresos (1 = Indigente, 2 = Pobre no indigente, 3 = No pobre)
 - pobreza_sinte - Pobreza con ajuste por pandemia
 - lp - Línea de pobreza 2020
 - li - Línea de indigencia 2020
 - nse_aproximado - Nivel socioeconómico estimado ('E' = Indigente/Pobre (NSE bajo), 'D' = Pobre no indigente (NSE medio bajo), 'C2-C1' = Clase media (NSE medio), 'AB' = Clase media alta/alta (NSE alto))
 - edad - Edad de la persona
 - sexo - Sexo de la persona (1 = Hombre, 2 = Mujer)
 - ytotcorh - Ingreso total del hogar corregido
 - yoprcorh - Ingreso del trabajo principal del hogar corregido
 - expr - Factor de expansión regional

# Archivos Datos Post-Pandemia 2022 - 2023
* CASEN_2022.csv : Dataframe original en csv.
* CASEN_GEOGRAFICO.csv : Dataframe en formato csv, que contiene los datos geograficos de CASEN_2022.csv, presenta las siguientes variables:
 - folio - Identificador único del hogar
 - id_persona - Identificador de persona dentro del hogar
 - provincia - Código de provincia
 - comuna - Código de comuna
 - expp - Factor de expansión a nivel persona
 - expc - Factor de expansión a nivel comunal
- * CASEN_POBREZA_2022.csv : Dataframe en formato csv, que contiene los datos socioeconomicos de CASEN_2022.csv, presenta las siguientes variables:
 - pobreza - Situación de pobreza por ingresos (1 = Indigente, 2 = Pobre no indigente, 3 = No pobre)
 - pobreza_multi_5d - Pobreza multidimensional (5 dimensiones:)
 - lp - Línea de pobreza
 - li - Línea de indigencia
 - nse - Nivel socioeconómico (1 = Bajo (E), 2 = Medio bajo (D), 3 = Medio (C3), 4 = Medio alto (C2-C1), 5 = Alto (AB))
 - region - Región
 - edad - Edad de la persona
 - sexo - Sexo de la persona (1 = Hombre, 2 = Mujer)
 - ytotcorh - Ingreso total del hogar corregido
 - yoprcorh - Ingreso del trabajo principal del hogar corregido
 - expr - Factor de expansión regional
- * CASE_POBREZA_GEOGRAFICA_2022.csv : Dataframe unido con CASEN_POBREZA_2022.csv y CASEN_GEOGRAFICO.csv, que presenta las mismas variables mencionadas anteriormente.
