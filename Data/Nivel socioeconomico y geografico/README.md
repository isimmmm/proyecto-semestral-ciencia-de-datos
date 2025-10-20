# Contenido Carpeta
En la carpeta 'Nivel Socioeconómico y Geográfico' se encuentra distribuida en parte en 'Datos Socioeconómicos', donde se hizo el proceso de recolección y limpieza de los datos necesarios para crear el dataset final de esta sección. En la carpeta se distribuyen otras carpetas con los nombres: 'Datos de 2017-2023', 'Datos Pandemia 2020-2022', 'Datos post pandemia 2022-2023' y 'Datos Pre-Pandemia 2017-2018'. Por otro lado, también en la carpeta 'Nivel Socioeconómico y Geográfico' se encuentra el dataset final de datos socieconomicos que se utilizará en el proyecto, en conjunto con un notebook de Jupyter que indica las instrucciones de cómo generarlo, respectivamente.

# Base de Datos 
En esta carpeta se encuenstran los archivos de datos a utilizar, en este caso se usara la base de datos de la Encuesta Nacional de Caracterización Socioeconómica Casen. Los objetivos de la encuesta son: conocer la situación de la población respecto de pobreza e ingresos, identificar carencias en las áreas de educación, salud, vivienda, trabajo e ingresos; evaluar brechas de pobreza e ingresos según variables demográficas y territoriales; y estimar la cobertura/focalización del gasto fiscal en subsidios a los hogares. Dado lo anterio, se escogio la version 'CASEN 2017','CASEN En Pandemia 2020' y 'CASEN 2022'.

## Descripcion CASEN 2017
Estos datos dan una mirada pre-pandemia para poder entender mejor como se desolvia la poblacion antes de su llegada y como era socieconomicamente cada sector de estudio (RM).El trabajo de campo se realizo entre noviembre de 2017 y enero de 2018.
## Descripcion CASEN EN PANDEMIA 2020
Dada la afectación de la pandemia en el empleo y los ingresos, la encuesta se centra en este aspecto como su eje principal. El trabajo de campo se realizo entre septiembre de 2020 a enero del 2021
## Descripcion CASEN 2022
La encuesta en cuenta con una nueva medición de la pobreza multidimensional, la cual no ha sido calculada desde 2017, entregando datos clave para el proceso de recuperación económica y social luego de la pandemia. El trabajo de campo se realizó entre noviembre del 2022 a enero del 2023.

# Instalación y Limpieza
Los archivos originales de los datos estan en formato STATA por lo que se debio leer y transformar en formato csv mediante pandas para mayor comodidad, por lo que si se desea acceder a la base de datos puede hacerlo mediante los siguientes links: 
- CASEN 2017 : https://observatorio.ministeriodesarrollosocial.gob.cl/encuesta-casen-2017
- CASEN EN PANDEMIA 2020 : https://observatorio.ministeriodesarrollosocial.gob.cl/encuesta-casen-en-pandemia-2020
- CASEN 2022 : https://observatorio.ministeriodesarrollosocial.gob.cl/encuesta-casen-2022

Por otro lado la limpieza de los datos y la creacion de los dataframes se puede realizar en los notebooks disponibles en cada seccion de las carpetas. Si se tiene mas dudas sobre otros tipos de variables consultar con el libro de codigos respectivo a la base de datos, se puede encontrarn en los links previamente compartidos.

# Variables importantes de Dataset_Socio_RM.csv
 - Pobreza_multidimensional = Esta medida incluye dimensiones como la salud, la educación, el acceso a servicios básicos como agua potable y saneamiento, la calidad de la vivienda y la infraestructura, y otros factores como las redes y cohesión social.(1: Pobreza, 0: No Pobreza).
 - NSE = Nivel SocioEconomico.
 - Pobreza_sinte = Situación de pobreza por ingreso sin transferencia Covid (1: Pobres extremos sin transferencia Covid, 2: Pobres no extremos sin transferencia Covid, 3: No pobres sin transferencia Covid).
 - Sistema_previsional = sistema es mixto y se compone de un componente público administrado por el Fondo Nacional de Salud (FONASA) y un componente privado a través de las Instituciones de Salud Previsional (ISAPRES).
 - Pobreza Categoria = Situación de pobreza por ingreso.

