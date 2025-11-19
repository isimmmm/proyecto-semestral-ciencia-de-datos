# Archivos elegidos de la base de datos de Covid-19 para la investigación

En esta carpeta se encuentra la información seleccionada y ordenada en distintos archivos .csv que se han sacado, manipulado y limpiado desde la base de datos abierta que MinCiencia pone a disposición del público.

## Contenido

-[Instalación](#instalacion)
-[Archivos](#archivos)

## Instalación

Para recrear esta lectura de archivos, es necesario descargar la base de datos desde la página web [OBSERVA del Gobierno de Chile](https://observa.minciencia.gob.cl/datos-abiertos/datos-del-repositorio-covid-19), y posicionar el archivo .zip dado en la misma carpeta que el notebook limpieza.ipynb. Luego, se debe correr el código del notebook ya mencionado. 

La base de datos de OBSERVA es abierta al público así que se puede descargar sin ningún problema.

## Archivos

Los archivos .csv que se crean, a partir del notebook "limpieza.ipynb", son los siguientes:

- *cant_muertes_20-21-22* - Agrupa, en cada fila por separado, las muertes totales en las comunas pertenecientes a la Región Metropolitana de forma individual.

- *cant_vacunados_distintas_dosis* - Por comuna perteneciente a la Región Metropolitana, de forma individual, por año del 2020-2022, se cuentan la cantidad total de vacunados según: primera dosis, segunda dosis, cuarta dosis, dosis única y dosis de refuerzo.

- *casos_confirmados_comuna* - Por comuna perteneciente a la Región Metropolitana, de forma individual, por año del 2020-2023, los casos confirmados de Covid-19 dados por el test PCR.

- *cobertura_casos_sospechosos_con_test_prom* - Por comuna perteneciente a la Región Metropolitana, de forma individual, por año del 2020-2022, se suma el promedio anual de casos nuevos notificados (sospechosos) con al menos un resultado de examen de RT-PCR.

- *cuarentenas_segun_codigo_manzanas_censo17* - Por código de manzanas basado en el sistema censal de 2017, se muestran los sectores con cuarentena total o cuarentena parcial según la comuna de la Región Metropolitana a la que pertenecen estas manzanas.

- *muertes_por_anio_comunal* - Por comuna perteneciente a la Región Metropolitana, de forma individual, por año del 2020-2023, se muestran el total de fallecidos por causa de covid-19.

- *positividad_test_covid19* - Por comuna perteneciente a la Región Metropolitana, de forma individual, por año del 2020-2022, se muestran el total de casos positivos confirmados por test PCR con covid-19.

- *transacciones_bip_por_comuna* - Por comuna perteneciente a la Región Metropolitana, de forma individual, en el 2020, se muestran las transacciones hechas por la tarjeta BIP de movilidad de transporte público. 

- *covid-19_datos_por_comuna* - Dataframe que contiene todos los datos recolectados anteriormente, haciéndoles .merge() por año y comuna. Datos faltantes de los archivos .csv leídos con anterioridad, son rellenados con NaN.

- *datos_finales* - Dataframe que contiene los datos del archivo *covid-19_datos_por_comuna.csv*, pero agregando las columnas de las variables poblaciones en porcentaje por sobre el total de la población, además de la población aproximada por cada año de las comunas según las predicciones hechas en la carpeta [censo/].
