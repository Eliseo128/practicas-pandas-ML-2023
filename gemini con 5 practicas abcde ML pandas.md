¡Hola! Qué gusto saludarte. Como tu docente de Machine Learning, te guiaré paso a paso para que domines **Pandas** dentro de **VS Code**. Este taller práctico está diseñado especialmente para que aprendas de forma clara, directa y estructurada.

---

**Configuración Inicial del Entorno**

Antes de programar, configuraremos nuestro espacio de trabajo. Sigue minuciosamente este orden de ejecución:

1. **Crear e ingresar a la carpeta de trabajo:** Paso 1.
Abre tu terminal (Command Prompt, PowerShell o Terminal en VS Code) y ejecuta:

```bash
mkdir practica5-ml-pandas
cd practica5-ml-pandas

```


2. **Crear el entorno virtual:** Paso 2.
Genera un entorno aislado llamado `.venv5` para instalar las librerías necesarias sin afectar a tu sistema:

```bash
python -m venv .venv5

```


3. **Activar el entorno virtual:** Paso 3.
Activa el entorno según tu sistema operativo:

* **Windows (PowerShell):** `.\.venv5\Scripts\Activate.ps1`
* **Windows (Cmd):** `.\.venv5\Scripts\activate.bat`
* **macOS / Linux:** `source .venv5/bin/activate`


4. **Instalar la librería Pandas:** Paso 4.
Con el entorno activo (verás `(.venv5)` al inicio de la línea de comandos), instala Pandas:

```bash
pip install pandas

```


5. **Seleccionar el intérprete en VS Code:** Paso 5.
1. Abre la carpeta `practica5-ml-pandas` en VS Code (`File > Open Folder`).
2. Presiona `Ctrl + Shift + P` (o `Cmd + Shift + P` en Mac) para abrir la paleta de comandos.
3. Escribe y selecciona **`Python: Select Interpreter`**.
4. Elige la opción que apunta a tu entorno **`./.venv5/Scripts/python.exe`** (o `bin/python` en Mac/Linux).


---

**Estructura del Proyecto**

La organización de carpetas y archivos en tu proyecto debe verse así en el explorador de VS Code:

```text
practica5-ml-pandas/
├── .venv5/
├── practica5a-0777.py
├── practica5b-0777.py
├── practica5c-0777.py
├── practica5d-0777.py
└── practica5e-0777.py

```

---

**Ejemplos Prácticos de la Vida Real**

**1. Archivo `practica5a-0777.py`: Registro de Calificaciones Escolares**

* **Concepto:** Crear un `DataFrame` desde cero usando un diccionario y calcular el promedio de calificaciones de los alumnos.

```python
import pandas as pd

# Datos del grupo escolar
datos_alumnos = {
    "Nombre": ["Ana", "Carlos", "Sofía", "Diego", "María"],
    "Matemáticas": [85, 90, 78, 92, 88],
    "Programación": [90, 85, 95, 80, 92]
}

# Crear DataFrame
df = pd.DataFrame(datos_alumnos)

# Agregar columna con el promedio individual
df["Promedio"] = (df["Matemáticas"] + df["Programación"]) / 2

print("=== REPORTE DE CALIFICACIONES ===")
print(df)

```

---

**2. Archivo `practica5b-0777.py`: Control de Inventario de una Tiendita**

* **Concepto:** Filtrar productos que necesitan reabastecimiento por tener bajo inventario.

```python
import pandas as pd

productos = {
    "Producto": ["Sabritas", "Refresco", "Galletas", "Agua", "Chocolates"],
    "Stock": [15, 4, 25, 2, 8],
    "Precio": [18.0, 20.0, 15.0, 12.0, 25.0]
}

df_inventario = pd.DataFrame(productos)

# Filtrar productos con stock menor a 5 unidades
reabastecer = df_inventario[df_inventario["Stock"] < 5]

print("=== PRODUCTOS QUE REQUIEREN REABASTECIMIENTO ===")
print(reabastecer)

```

---

**3. Archivo `practica5c-0777.py`: Seguimiento de Gastos Semanales**

* **Concepto:** Agrupar datos para sumar los gastos por categoría (comida, transporte, entretenimiento).

```python
import pandas as pd

gastos = {
    "Día": ["Lunes", "Lunes", "Martes", "Miércoles", "Miércoles"],
    "Categoría": ["Transporte", "Comida", "Comida", "Transporte", "Entretenimiento"],
    "Monto": [25.0, 60.0, 55.0, 25.0, 120.0]
}

df_gastos = pd.DataFrame(gastos)

# Agrupar por Categoría y calcular el total gastado
total_por_categoria = df_gastos.groupby("Categoría")["Monto"].sum().reset_index()

print("=== RESUMEN DE GASTOS POR CATEGORÍA ===")
print(total_por_categoria)

```

---

**4. Archivo `practica5d-0777.py`: Registro de Redes Sociales (Limpieza de Datos)**

* **Concepto:** Identificar y manejar datos faltantes (`NaN`) en la interacción de usuarios.

```python
import pandas as pd

datos_redes = {
    "Usuario": ["@user1", "@user2", "@user3", "@user4"],
    "Likes": [120, None, 450, 210],
    "Comentarios": [15, 8, None, 30]
}

df_redes = pd.DataFrame(datos_redes)

# Rellenar los valores nulos (NaN) con 0
df_limpio = df_redes.fillna(0)

print("=== DATOS DE REDES SOCIALES LIMPIOS ===")
print(df_limpio)

```

---

**5. Archivo `practica5e-0777.py`: Monitoreo de Pasos Diarios (Estadística Básica)**

* **Concepto:** Obtener métricas descriptivas básicas (máximo, mínimo, promedio) sobre hábitos de salud.

```python
import pandas as pd

pasos_semana = {
    "Día": ["Lun", "Mar", "Mié", "Jue", "Vie", "Sáb", "Dom"],
    "Pasos": [4500, 8200, 6100, 7500, 9000, 11200, 3100]
}

df_pasos = pd.DataFrame(pasos_semana)

# Obtener estadísticas rápidas
print("=== RESUMEN ESTADÍSTICO DE PASOS DE LA SEMANA ===")
print(f"Total de pasos: {df_pasos['Pasos'].sum()}")
print(f"Promedio diario: {df_pasos['Pasos'].mean():.2f}")
print(f"Día con más pasos: {df_pasos.loc[df_pasos['Pasos'].idxmax(), 'Día']} ({df_pasos['Pasos'].max()} pasos)")

```
