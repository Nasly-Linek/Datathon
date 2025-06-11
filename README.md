# 🧠 Análisis de Establecimientos Educativos en Colombia

Este proyecto realiza un análisis exploratorio y de segmentación de los establecimientos educativos en Colombia, usando datos abiertos para identificar patrones relacionados con características como jornada, calendario, zona y tipo de establecimiento.

---

## 📊 Objetivo

Analizar la distribución y características de las instituciones educativas en Colombia, con énfasis en:

- Calendario académico (A o B)
- Jornada única
- Zona (urbana o rural)
- Sector (oficial o privado)
- Desigualdades estructurales en el acceso a condiciones educativas favorables

---

## 📁 Dataset

**Fuente**: Portal de Datos Abiertos de Colombia  
**Archivo original**: `ESTABLECIMIENTOS_EDUCATIVOS-COLOMBIA_20250606.csv`  
**Número de registros después de limpieza**: ~20,000  
**Columnas relevantes**:

- `zona`
- `calendario`
- `tipo_Establecimiento`
- `propiedad_Planta_Fisica`
- `numero_de_Sedes`
- `modelo_Educativo`, entre otras.

---

## 🧹 Proceso de limpieza

- Eliminación de columnas con más de 20.000 valores nulos
- Conversión de columnas al tipo de dato correcto (categóricas, enteras)
- Normalización de valores y corrección de formatos
- Codificación de variables para modelado

---

## 🔍 Análisis exploratorio

Se exploraron características como:

- Distribución por zona (urbana/rural)
- Frecuencia de calendarios A y B
- Asociación entre tipo de institución y jornada única
- Infraestructura educativa

---

## 🧾 Conclusiones

- Existe una fuerte asociación entre **instituciones privadas urbanas** y la **jornada única** y el **calendario B**
- Las **instituciones oficiales y rurales** enfrentan limitaciones de infraestructura y jornada
- Esto refleja una **desigualdad estructural en el acceso a condiciones educativas de calidad**

---

## 🛠 Requisitos

- Python 3.10+
- pandas
- scikit-learn
- matplotlib
- seaborn
- jupyter notebook

Instalar dependencias:

```bash
pip install -r requirements.txt

