# Prestadores de Salud y Egresos Hospitalarios (ISAPRE y FONASA)

## 📁 Contenido Carpeta
En esta carpeta se encuentra el notebook `notebook.ipynb`, que corresponde al análisis de los **prestadores de salud** (sistema público y privado) y la **cantidad de egresos hospitalarios** durante el periodo de pandemia.  
Los datos utilizados provienen de las fuentes oficiales indicadas en la propuesta del proyecto:

- **Superintendencia de Salud:** Egresos ISAPRE por diagnóstico y prestador.  
- **Departamento de Estadísticas e Información de Salud (DEIS):** Egresos hospitalarios FONASA.  

El objetivo de este módulo es comparar ambos sistemas para observar **diferencias en la cantidad de egresos, su distribución y evolución durante la pandemia**.

---

## 🧾 Base de Datos

Los archivos utilizados corresponden a registros oficiales del sistema público y privado de salud en Chile. Estos contienen datos estructurados en formato `.csv` y `.xlsx` con variables como:

- `prestador` – Nombre del hospital o clínica  
- `tipo_prestador` – Clasificación (público / privado)  
- `egresos` – Cantidad total de egresos hospitalarios  
- `anio` – Año de registro  
- `region` – Región correspondiente (Región Metropolitana en este caso)  
- `diagnostico` – Categoría de diagnóstico o tipo de atención  

**Fuentes de datos:**
- [Superintendencia de Salud – Egresos Hospitalarios ISAPRE](https://www.superdesalud.gob.cl/tax-biblioteca-digital/estadisticas-3724/estadisticas-por-tema-3741/egresos-hospitalarios-3744/)  
- [DEIS – Egresos Hospitalarios FONASA](https://deis.minsal.cl/#datosabiertos)

---

## ⚙️ Instalación y Limpieza

Para ejecutar el notebook correctamente:

1. Descargue los archivos originales desde las fuentes oficiales.  
2. Colóquelos en la misma carpeta que el notebook `notebook.ipynb` y descomprímalos.  
3. Ejecute el notebook para realizar la **lectura, limpieza y unificación** de los datos.  

Durante la limpieza se realizaron los siguientes pasos:
- Lectura de archivos `.xlsx` y `.csv` mediante **pandas**  
- Eliminación de filas vacías y columnas irrelevantes  
- Estandarización de nombres de columnas  
- Filtrado de registros correspondientes a la **Región Metropolitana**  
- Agrupación por tipo de prestador y año  

---

## 📊 Análisis y Visualización

El análisis incluye:
- **Gráficos comparativos** de cantidad de egresos entre **ISAPRE y FONASA**  
- **Distribuciones por tipo de prestador**  
- **Proporciones y diferencias** relativas en los años 2020–2022  

Se utilizan las bibliotecas:
- `pandas` para manipulación y limpieza de datos  
- `matplotlib` para visualizaciones  

---

## 📂 Archivos

| Archivo | Descripción |
|----------|--------------|
| `notebook.ipynb` | Notebook principal con el proceso de limpieza, análisis y visualización |
| `egresos_isapre.xlsx` | Datos originales del sistema privado (Superintendencia de Salud) |
| `egresos_fonasa.csv` | Datos originales del sistema público (DEIS) |
| `egresos_unificados.csv` | Dataframe resultante luego de la limpieza, con las variables combinadas |
