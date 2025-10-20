# Prestadores de Salud y Egresos Hospitalarios (FONASA e ISAPRE)

## Contenido de la carpeta
En esta carpeta se encuentra el notebook `notebook.ipynb`, que corresponde al análisis de los **prestadores de salud** en Chile durante el periodo de pandemia, diferenciando entre el sistema **público (FONASA)** y el **privado (ISAPRE)**.  
El objetivo es comparar ambos sistemas para observar **diferencias en la cantidad de egresos hospitalarios por COVID-19, su distribución y evolución entre 2020 y 2022**.

**Fuentes de datos:**
- **Superintendencia de Salud:** Egresos hospitalarios del sistema ISAPRE, por diagnóstico y tipo de prestador.  
- **Departamento de Estadísticas e Información de Salud (DEIS):** Egresos hospitalarios del sistema público (FONASA).  

---

## Base de datos utilizada

Los archivos utilizados corresponden a registros oficiales del sistema público y privado de salud en Chile. Estos datos están estructurados en formato `.csv` y `.xlsx` con las siguientes variables principales:

| Variable | Descripción | Tipo |
|-----------|-------------|------|
| `Año` | Año del registro (2020–2022) | Categórica (temporal) |
| `Sistema` | Sistema de salud: FONASA o ISAPRE | Categórica |
| `Egresos` | Número total de egresos hospitalarios | Cuantitativa discreta |
| `%_COVID_num` | Porcentaje de egresos por diagnóstico COVID-19 | Cuantitativa continua |
| `Prestador` | Nombre del hospital o clínica (según disponibilidad) | Categórica |
| `Región` | Región del país (en este caso, Región Metropolitana) | Categórica |

**Formato:** `.csv` / `.xlsx`  
**Origen:**  
- [Superintendencia de Salud – Estadística anual de egresos hospitalarios del sistema ISAPRE (2023)](https://www.superdesalud.gob.cl/biblioteca-digital/estadistica-anual-de-egresos-hospitalarios-del-sistema-isapre-ano-2023/)  
- [Departamento de Estadísticas e Información de Salud (DEIS) – Datos Abiertos](https://deis.minsal.cl/#datosabiertos)  

**Forma de recolección:**  
Los datos se descargaron manualmente desde las fuentes oficiales, se procesaron con **pandas**, y se unificaron en un solo DataFrame (`comp`) con los campos `Año`, `Sistema` y `%_COVID_num`.  
Se creó además un DataFrame auxiliar (`resumen_2022`) para representar los resultados del año 2022 de forma puntual.

---

## Limpieza y procesamiento
Durante la preparación de los datos, se realizaron los siguientes pasos:

1. **Lectura** de archivos `.csv` y `.xlsx` con `pandas`.  
2. **Eliminación** de filas vacías y columnas no necesarias.  
3. **Estandarización** de nombres de columnas y tipos de datos.  
4. **Filtrado** de registros correspondientes al periodo 2020–2022 y Región Metropolitana.  
5. **Cálculo del porcentaje de egresos por COVID (%_COVID_num)** a partir de egresos totales.  
6. **Agrupación** por `Sistema` y `Año` para facilitar la comparación temporal.

El DataFrame final permite comparar directamente los sistemas público y privado en términos del porcentaje de egresos por COVID-19.

---

## Análisis y visualizaciones

Se implementaron **dos visualizaciones principales** acordes al código del notebook:

### Gráfico de barras agrupadas (2020–2022)
**Código correspondiente:** usa `years`, `vals_fonasa`, `vals_isapre` y `plt.bar(...)` con colores `#8E44AD` (FONASA) y `#2E86C1` (ISAPRE).

**Propósito:**  
Mostrar la evolución temporal del **porcentaje de egresos hospitalarios por COVID-19** para ambos sistemas de salud entre 2020 y 2022.

**Justificación:**  
- Las barras agrupadas permiten **comparar dos categorías (sistemas)** dentro de cada año.  
- Facilitan observar **cambios o brechas** entre FONASA e ISAPRE en distintos periodos de la pandemia.  
- La inclusión de etiquetas de porcentaje sobre cada barra mejora la **lectura directa de valores**.

**Interpretación esperada:**  
Una mayor proporción en FONASA puede reflejar su rol predominante en la atención durante la pandemia, mientras que una disminución en ISAPRE podría estar asociada a postergación de cirugías o diferencias en población cubierta.

---

### Gráfico de barras simples (años 2020, 2021, 2022)
**Código correspondiente:** `plt.bar(resumen_202x["Sistema"], resumen_202x["%_COVID_num"], ...)`

**Propósito:**  
Visualizar la distribución del **porcentaje de egresos por COVID-19** entre los sistemas de salud durante cada año.

**Justificación:**  
- El gráfico de barras es ideal para **comparar magnitudes entre pocas categorías** (en este caso, solo dos sistemas).  
- Permite mostrar de forma limpia la **fotografía puntual** de un año de referencia, sin sobrecargar con información temporal.  
- Las etiquetas sobre las barras añaden claridad al resultado numérico.

---

## Interpretación general
El análisis gráfico permite observar cómo el **sistema público (FONASA)** concentró la mayor parte de los egresos hospitalarios por COVID-19 durante los años críticos de la pandemia, evidenciando su rol principal en la atención sanitaria nacional.  
El **sistema privado (ISAPRE)** presentó una proporción menor y más estable, posiblemente vinculada a diferencias en cobertura poblacional y tipo de prestaciones.

---

## Herramientas utilizadas
- **Python 3.11**  
- **pandas** – manipulación y limpieza de datos  
- **matplotlib** – visualizaciones comparativas  
- **numpy** – operaciones numéricas auxiliares  

---

## Archivos incluidos

| Archivo | Descripción |
|----------|--------------|
| `notebook.ipynb` | Notebook principal con el proceso de limpieza, análisis y visualización |
| `egresos_isapre.xlsx` | Datos originales del sistema privado (Superintendencia de Salud) |
| `egresos_fonasa.csv` | Datos originales del sistema público (DEIS) |
| `egresos_unificados.csv` | DataFrame resultante tras limpieza y unificación |
| `README.md` | Documento explicativo con descripción de datos y metodología |

---

