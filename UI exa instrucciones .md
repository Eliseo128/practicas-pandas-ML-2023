¡Entendido! Aquí tienes la práctica completa actualizada cambiando el **punto 5** a **ordenar datos de forma descendente por un campo numérico (Stock)**.

---

---

## 🛠️ Paso 1: Configuración del Entorno Virtual en VS Code

Abre la terminal de VS Code en la carpeta base de tu proyecto y ejecuta los siguientes comandos según tu sistema operativo.

### En Windows (PowerShell):

```bash
# 1. Crear el entorno virtual
python -m venv .venv-ml-0777

# 2. Activar el entorno virtual
.\.venv-ml-0777\Scripts\activate

# 3. Instalar Pandas
pip install pandas

# 4. Generar el archivo de requerimientos
pip freeze > requirements.txt

```

### En macOS / Linux:

```bash
# 1. Crear el entorno virtual
python3 -m venv .venv-ml-0777

# 2. Activar el entorno virtual
source .venv-ml-0777/bin/activate

# 3. Instalar Pandas
pip install pandas

# 4. Generar el archivo de requerimientos
pip freeze > requirements.txt

```

---

## 📁 Paso 2: Estructura de Carpetas y Archivos

Tu proyecto en VS Code debe verse de la siguiente manera:

```text
exa-UI_ml_0777/
│
├── .venv-ml-0777/                  # Carpeta del entorno virtual
├── requirements.txt                # Lista de librerías instaladas
│
├── datos-de-entrada-ml-0777/
│   └── dicc-0777.py                # Contiene el diccionario original de productos
│
├── codigo-ml-0777/
│   └── exa-ml-0777.py              # Script principal que procesa y muestra resultados
│
└── resultados-0777/
    └── resultados-ml-0777.md       # Archivo final generado automáticamente

```

---

## 💻 Paso 3: Código Fuente de los Archivos

Crea cada archivo en la ubicación indicada dentro de VS Code:

### 1. `datos-de-entrada-ml-0777/dicc-0777.py`

```python
print("Eliseo Nava Machine Learning pandas, NC 0777")

# Diccionario con los datos de entrada
datos_productos = {
    "Producto": ["Sabritas", "Refresco", "Galletas", "Agua", "Chocolates"],
    "Stock": [15, 4, 25, 2, 8],
    "Precio": [18.0, 20.0, 15.0, 12.0, 25.0]
}

print("Eliseo Nava Machine Learning pandas, NC 0777")

```

---

### 2. `codigo-ml-0777/exa-ml-0777.py`

1. **Script completo de ejecución y exportación:**
```python
import sys
import os
import pandas as pd

# Permitir importar dicc-0777.py desde la subcarpeta hermana
sys.path.append(os.path.abspath(os.path.join(os.path.dirname(__file__), '..', 'datos-de-entrada-ml-0777')))
import dicc_0777

print("Eliseo Nava Machine Learning pandas, NC 0777")

# Variable para almacenar las salidas y guardarlas en el archivo .md
contenido_md = []
encabezado_pie = "Eliseo Nava Machine Learning pandas, NC 0777"
contenido_md.append(f"# Reporte de Análisis de Datos - Pandas\n\n`{encabezado_pie}`\n")

def registrar(titulo, contenido):
    """Muestra el resultado en terminal y lo formatea para el archivo Markdown."""
    print(f"\n--- {titulo} ---")
    print(contenido)
    contenido_md.append(f"## {titulo}\n```text\n{contenido}\n```\n")

# 1. Convertir diccionario a DataFrame
df = pd.DataFrame(dicc_0777.datos_productos)
registrar("1. DataFrame Convertido", df)

# 2. Información Estructural
registrar("2.1 Primeras Filas (head)", df.head(2))
registrar("2.2 Últimas Filas (tail)", df.tail(2))
registrar("2.3 Dimensiones (Filas, Columnas)", df.shape)
registrar("2.4 Tipos de Datos por Columna", df.dtypes)

# Capturar salida de df.info()
import io
buffer = io.StringIO()
df.info(buf=buffer)
registrar("2.5 Información General (info)", buffer.getvalue())

# 3. Estadísticas Generales de una Columna Numérica (Precio)
registrar("3. Estadísticas Generales de la Columna 'Precio'", df['Precio'].describe())

# 4. Ordenar Ascendente por Precio
df_asc_precio = df.sort_values(by="Precio", ascending=True)
registrar("4. Ordenar Ascendente por Precio", df_asc_precio)

# 5. Ordenar Descendente por Stock
df_desc_stock = df.sort_values(by="Stock", ascending=False)
registrar("5. Ordenar Descendente por Stock", df_desc_stock)

# 7. Guardar el archivo resultados-ml-0777.md dentro de resultados-0777
carpeta_resultados = os.path.abspath(os.path.join(os.path.dirname(__file__), '..', 'resultados-0777'))
os.makedirs(carpeta_resultados, exist_ok=True)
ruta_archivo_md = os.path.join(carpeta_resultados, "resultados-ml-0777.md")

contenido_md.append(f"`{encabezado_pie}`")

with open(ruta_archivo_md, "w", encoding="utf-8") as f:
    f.write("\n".join(contenido_md))

print(f"\n[ÉXITO] Archivo generado correctamente en: {ruta_archivo_md}")
print("Eliseo Nava Machine Learning pandas, NC 0777")

```


---

## 🚀 Paso 4: Ejecución y Resultados en Terminal

Ejecuta el archivo desde la raíz del proyecto en tu terminal con el entorno virtual activo:

```bash
python codigo-ml-0777/exa-ml-0777.py

```

### Salida esperada en la terminal de VS Code:

```text
Eliseo Nava Machine Learning pandas, NC 0777
Eliseo Nava Machine Learning pandas, NC 0777
Eliseo Nava Machine Learning pandas, NC 0777

--- 1. DataFrame Convertido ---
     Producto  Stock  Precio
0    Sabritas     15    18.0
1    Refresco      4    20.0
2    Galletas     25    15.0
3        Agua      2    12.0
4  Chocolates      8    25.0

--- 2.1 Primeras Filas (head) ---
   Producto  Stock  Precio
0  Sabritas     15    18.0
1  Refresco      4    20.0

--- 2.2 Últimas Filas (tail) ---
     Producto  Stock  Precio
3        Agua      2    12.0
4  Chocolates      8    25.0

--- 2.3 Dimensiones (Filas, Columnas) ---
(5, 3)

--- 2.4 Tipos de Datos por Columna ---
Producto     object
Stock         int64
Precio      float64
dtype: object

--- 2.5 Información General (info) ---
<class 'pandas.core.frame.DataFrame'>
RangeIndex: 5 entries, 0 to 4
Data columns (total 3 columns):
 #   Column    Non-Null Count  Dtype  
---  ------    --------------  -----  
 0   Producto  5 non-null      object 
 1   Stock     5 non-null      int64  
 2   Precio    5 non-null      float64
dtypes: float64(1), int64(1), object(1)
memory usage: 248.0+ bytes


--- 3. Estadísticas Generales de la Columna 'Precio' ---
count     5.000000
mean     18.000000
std       5.000000
min      12.000000
25%      15.000000
50%      18.000000
75%      20.000000
max      25.000000
Name: Precio, dtype: float64

--- 4. Ordenar Ascendente por Precio ---
     Producto  Stock  Precio
3        Agua      2    12.0
2    Galletas     25    15.0
0    Sabritas     15    18.0
1    Refresco      4    20.0
4  Chocolates      8    25.0

--- 5. Ordenar Descendente por Stock ---
     Producto  Stock  Precio
2    Galletas     25    15.0
0    Sabritas     15    18.0
4  Chocolates      8    25.0
1    Refresco      4    20.0
3        Agua      2    12.0

[ÉXITO] Archivo generado correctamente en: .../resultados-0777/resultados-ml-0777.md
Eliseo Nava Machine Learning pandas, NC 0777

```
