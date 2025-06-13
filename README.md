# 🧠 Análisis de Instituciones Educativas en Colombia

Este proyecto realiza un análisis exploratorio y predictivo de los establecimientos educativos en Colombia, usando datos abiertos para identificar patrones relacionados con la jornada escolar, el calendario académico, la zona geográfica y la naturaleza (privada o pública) de las instituciones.

---

## 📊 Objetivo

Analizar la distribución y características de las instituciones educativas en Colombia para validar la siguiente hipótesis:

> “La presencia de jornada única y calendario B se asocia principalmente con instituciones privadas ubicadas en zonas urbanas.”

---

## 📁 Dataset
Fuente: Portal de Datos Abiertos de Colombia
Archivo original: ESTABLECIMIENTOS_EDUCATIVOS-COLOMBIA_20250606.csv

Número de registros después de limpieza: 22,530

Columnas relevantes:
zona → origen de la variable zona_normalizada
jornadas → origen de la variable jornadas_normalizadas
calendario_academico
naturaleza_institucion
zona_normalizada → zonas agrupadas en URBANA, RURAL y MIXTA
jornadas_normalizadas → categorías unificadas de jornada escolar
niveles_normalizados → niveles educativos reorganizados

---

## 🧹 Proceso de limpieza de datos

- **Eliminación de columnas irrelevantes o incompletas**  
  Se eliminaron 21 columnas como `direccion`, `telefono`, `correo_Electronico`, `nombre_Rector`, `discapacidades`, entre otras, por tener alto porcentaje de datos nulos o no ser útiles para el análisis.

- **Estandarización de texto**  
  Se convirtió a mayúsculas el contenido de todas las columnas tipo `object` para unificar valores.

- **Reemplazo de valores nulos y vacíos**  
  Se reemplazaron los valores `NaN`, vacíos o `None` por la etiqueta `"NO DILIGENCIADO (<nombre_columna>)"`.

- **Normalización de espacios**  
  Se corrigieron valores con espacios múltiples dentro del texto, dejándolos con un solo espacio.

- **Agrupación de zonas geográficas**  
  Se creó una nueva columna `zona_normalizada` con tres categorías: `URBANA`, `RURAL` y `MIXTA`.

- **Estandarización de niveles educativos**  
  Se creó `niveles_normalizados`, reorganizando el orden y agrupando niveles similares.

- **Agrupación y normalización de jornadas**  
  Se creó `jornadas_normalizadas`, donde se agruparon las jornadas en categorías como `MAÑANA`, `TARDE`, `NOCTURNA`, `UNICA/COMPLETA`, `FIN DE SEMANA`, `MIXTA` u `OTRO`.

- **Conversión de variables a tipo categórico**  
  Columnas como `zona_normalizada`, `jornadas_normalizadas` y `calendario_academico` se convirtieron al tipo `category` para optimizar el uso de memoria y facilitar el análisis.

---

## 🧪 Preprocesamiento para modelado

- **Codificación de variables categóricas**  
  Se aplicó codificación numérica (`LabelEncoder`) a columnas como `zona_normalizada`, `jornadas_normalizadas` y `calendario_academico` para preparar los datos para el modelo predictivo.

---

## 🔍 Análisis exploratorio

Se analizaron las siguientes características:

- Distribución por zona (`urbana`, `rural`, `mixta`)
- Comparación entre instituciones con jornada única y calendario B
- Frecuencia de instituciones privadas dentro del subconjunto filtrado
- Asociación entre características institucionales y el tipo de jornada

**Resultado**: Las instituciones con jornada única y calendario B son en su mayoría privadas y ubicadas en zonas urbanas, reforzando visualmente la hipótesis.

---

## 🤖 Modelo de Machine Learning

Se implementó un modelo de **regresión logística** para predecir si una institución es **privada** o **pública**, usando como variables independientes:
- `zona`
- `calendario_academico`
- `jornada`

### Resultados:
- El modelo logró predecir correctamente la naturaleza institucional con buena precisión
- La probabilidad de que una institución sea privada aumenta considerablemente cuando tiene jornada única, calendario B y está ubicada en zona urbana

---

## 🧾 Conclusiones

- La hipótesis fue confirmada tanto por análisis exploratorio como por el modelo predictivo
- Existe una fuerte asociación entre instituciones **privadas urbanas** y la presencia de **jornada única** y **calendario B**
- Las instituciones **públicas y rurales** presentan menor probabilidad de ofrecer estas condiciones

---

## 🛠 Requisitos

- Python 3.10+
- pandas
- scikit-learn
- matplotlib
- seaborn
- jupyter notebook
- Tablero en Trello: https://trello.com/b/mXzNjqpj

Instalar dependencias:

```bash
pip install pandas scikit-learn matplotlib seaborn jupyter
