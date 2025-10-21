# Archivos elegidos de la base de datos de Covid-19 para la investigación

En esta carpeta se encuentra la estimación de población comunal a partir de los datos censales de 2017 y 2024 en la Región Metropolitana.

## Contenido

-[Instalación](#instalacion)
-[Archivos](#archivos)

## Instalación

Para recrear esta lectura de archivos, es necesario descargar la base de datos desde la página web [Instituto Nacional de Estadísticas Chile](https://censo2024.ine.gob.cl/estadisticas/)(https://censo2024.ine.gob.cl/estadisticas-2017/). Se descarga el único archivo de la base de 2017, y en 2024 se debe seleccionar el archivo llamado "D1_Poblacion-censada-por-sexo-y-edad-en-grupos-quinquenales". Ambos archivos se deben posicionar en la carpeta censo/, y de esta forma se puede correr el Notebook adjunto sin problemas.

Las bases de datos de INE son abiertas al público, así que se pueden descargar sin ningún problema.

## Archivos

El archivo .csv que se crea a partir del notebook "NotebookEstimacion.ipynb" es:

- *estimacion_poblacion_por_comunas.csv* - Contiene tres columnas: Comuna, Año y Población. Comuna son las comunas pertenecientes a la Región Metropolitana, Año va desde el 2017 hasta el 2024, haciendo una estimación entremedio respecto a los datos de ambos años, reflejada en la columna Población.