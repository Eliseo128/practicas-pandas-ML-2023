¡Perfecto! Vamos a llevar tu clase al siguiente nivel. **Jupyter Notebooks (`.ipynb`)** es la herramienta estándar en la industria de Data Science y Machine Learning porque nos permite ejecutar código por celdas, ver resultados inmediatamente y combinar texto explicativo con código.

Continuaremos trabajando sobre la misma carpeta `practica5-ml-pandas` y el entorno virtual `.venv5` que creamos anteriormente.

---

### **Configuración del Entorno para Jupyter Notebooks**

Sigue este procedimiento paso a paso desde la terminal de VS Code:

1. **Asegurar que el entorno virtual esté activo:** Paso 1.
Verifica que en tu terminal aparezca `(.venv5)` al inicio de la línea de comandos. Si no está activo, ejecútalo según tu sistema operativo:

* **Windows (PowerShell):** `.\.venv5\Scripts\Activate.ps1`
* **Windows (CMD):** `.\.venv5\Scripts\activate.bat`
* **macOS / Linux:** `source .venv5/bin/activate`


2. **Instalar Jupyter e ipykernel:** Paso 2.
`ipykernel` es el conector que permite a VS Code ejecutar celdas de código en el entorno virtual. Instala ambas herramientas ejecutando:

```bash
pip install pandas jupyter ipykernel

```


3. **Registrar el entorno en Jupyter:** Paso 3.
Para que VS Code reconozca tu entorno `.venv5` dentro de los cuadernos de Jupyter, registra el kernel ejecutando:

```bash
python -m ipykernel install --user --name=.venv5 --display-name "Python (.venv5)"

```


4. **Seleccionar el Kernel en el archivo .ipynb dentro de VS Code:** Paso 4.
1. Crea o abre cualquier archivo `.ipynb` en VS Code.
2. En la esquina superior derecha del cuaderno, haz clic en **`Select Kernel`** (o *Seleccionar Kernel*).
3. Elige **`Python Environments...`** y selecciona el kernel con el nombre **`Python (.venv5)`**.


---

### **Estructura de Carpetas y Archivos**

La estructura en el explorador de archivos de VS Code quedará de la siguiente manera:

```text
practica5-ml-pandas/
├── .venv5/
├── practica5a-0777.ipynb
├── practica5b-0777.ipynb
├── practica5c-0777.ipynb
├── practica5d-0777.ipynb
└── practica5e-0777.ipynb

```

---

### **Instrucciones para Trabajar con Notebooks en VS Code**

* En un archivo `.ipynb`, el código se divide en **Celdas de Código**.
* Para ejecutar una celda, presiona **`Shift + Enter`** o haz clic en el botón de reproducción (**`▶`**) a la izquierda de la celda.
* En Jupyter Notebook, al colocar una variable al final de una celda sin la función `print()`, Pandas mostrará la tabla con un formato visual interactivo y ordenado.

---

### **Contenido de los Notebooks (`.ipynb`)**

Crea cada archivo e introduce el código correspondiente en la primera celda de código:

#### **1. Archivo: `practica5a-0777.ipynb**`

* **Explicación:** Creación de un DataFrame con calificaciones y cálculo del promedio final por alumno.

```python
import pandas as pd

# Datos de los alumnos
datos_alumnos = {
    "Nombre": ["Ana", "Carlos", "Sofía", "Diego", "María"],
    "Matemáticas": [85, 90, 78, 92, 88],
    "Programación": [90, 85, 95, 80, 92]
}

# Crear el DataFrame
df = pd.DataFrame(datos_alumnos)

# Calcular la columna Promedio
df["Promedio"] = (df["Matemáticas"] + df["Programación"]) / 2

# Mostrar el DataFrame de forma interactiva
df

```

---

#### **2. Archivo: `practica5b-0777.ipynb**`

* **Explicación:** Filtrado condicional en un inventario para detectar qué productos necesitan reabastecimiento urgente.

```python
import pandas as pd

productos = {
    "Producto": ["Sabritas", "Refresco", "Galletas", "Agua", "Chocolates"],
    "Stock": [15, 4, 25, 2, 8],
    "Precio": [18.0, 20.0, 15.0, 12.0, 25.0]
}

df_inventario = pd.DataFrame(productos)

# Filtrar productos cuyo Stock sea menor a 5
reabastecer = df_inventario[df_inventario["Stock"] < 5]

reabastecer

```

---

#### **3. Archivo: `practica5c-0777.ipynb**`

* **Explicación:** Agrupación de datos (`groupby`) para analizar el gasto total realizado por categoría.

```python
import pandas as pd

gastos = {
    "Día": ["Lunes", "Lunes", "Martes", "Miércoles", "Miércoles"],
    "Categoría": ["Transporte", "Comida", "Comida", "Transporte", "Entretenimiento"],
    "Monto": [25.0, 60.0, 55.0, 25.0, 120.0]
}

df_gastos = pd.DataFrame(gastos)

# Agrupar por Categoría y sumar los montos
total_por_categoria = df_gastos.groupby("Categoría")["Monto"].sum().reset_index()

total_por_categoria

```

---

#### **4. Archivo: `practica5d-0777.ipynb**`

* **Explicación:** Tratamiento y limpieza de datos faltantes (`NaN`) en registros de redes sociales.

```python
import pandas as pd

datos_redes = {
    "Usuario": ["@user1", "@user2", "@user3", "@user4"],
    "Likes": [120, None, 450, 210],
    "Comentarios": [15, 8, None, 30]
}

df_redes = pd.DataFrame(datos_redes)

# Rellenar datos faltantes (NaN) con el valor 0
df_limpio = df_redes.fillna(0)

df_limpio

```

---

#### **5. Archivo: `practica5e-0777.ipynb**`

* **Explicación:** Cálculo de estadísticas descriptivas clave sobre el seguimiento de hábitos diarios.

```python
import pandas as pd

pasos_semana = {
    "Día": ["Lun", "Mar", "Mié", "Jue", "Vie", "Sáb", "Dom"],
    "Pasos": [4500, 8200, 6100, 7500, 9000, 11200, 3100]
}

df_pasos = pd.DataFrame(pasos_semana)

# Calcular métricas principales
total_pasos = df_pasos["Pasos"].sum()
promedio_pasos = df_pasos["Pasos"].mean()
dia_max = df_pasos.loc[df_pasos["Pasos"].idxmax(), "Día"]
max_pasos = df_pasos["Pasos"].max()

# Mostrar resultados
print(f"Total de pasos acumulados: {total_pasos}")
print(f"Promedio diario: {promedio_pasos:.2f}")
print(f"Día con mayor actividad: {dia_max} con {max_pasos} pasos")

# Mostrar la tabla de datos
df_pasos

```
