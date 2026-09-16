# Práctica 5 — Machine Learning con Pandas en VS Code

**Nivel:** 3.er semestre de preparatoria
**Modalidad:** Práctica guiada
**Lenguaje:** Python
**Biblioteca:** Pandas
**Carpeta:** `practica5-ml-pandas`

El objetivo es que el alumno aprenda a **crear un entorno virtual, instalar Pandas, crear DataFrames y realizar operaciones sencillas con datos de situaciones reales**.

---

## 1. Crear la carpeta de trabajo

Abre **Visual Studio Code** y selecciona:

**Terminal → Nueva terminal**

Ejecuta:

```powershell
mkdir practica5-ml-pandas
```

Entra a la carpeta:

```powershell
cd practica5-ml-pandas
```

Abre el proyecto en VS Code:

```powershell
code .
```

**Explicación:** `practica5-ml-pandas` será la carpeta principal donde estarán los programas de la práctica.

---

## 2. Crear el entorno virtual `.venv5`

En la terminal escribe:

```powershell
python -m venv .venv5
```

Se creará:

```text
practica5-ml-pandas/
└── .venv5/
```

**Explicación:** el entorno virtual permite mantener las bibliotecas de esta práctica separadas de otros proyectos de Python.

---

## 3. Activar el entorno virtual

En **PowerShell**:

```powershell
.\.venv5\Scripts\Activate.ps1
```

La terminal deberá mostrar algo similar a:

```text
(.venv5) PS C:\...\practica5-ml-pandas>
```

La aparición de:

```text
(.venv5)
```

indica que el entorno está activo.

---

## 4. Seleccionar el intérprete de Python

En VS Code presiona:

```text
Ctrl + Shift + P
```

Escribe:

```text
Python: Select Interpreter
```

Selecciona:

```text
Python 3.x.x ('.venv5': venv)
```

o el intérprete:

```text
.venv5\Scripts\python.exe
```

**Explicación:** esto garantiza que VS Code ejecute los programas utilizando el Python del entorno `.venv5`.

---

## 5. Instalar Pandas

Con `.venv5` activo:

```powershell
python -m pip install --upgrade pip
```

Después:

```powershell
python -m pip install pandas
```

---

## 6. Verificar Pandas

Ejecuta:

```powershell
python -c "import pandas as pd; print(pd.__version__)"
```

Si aparece una versión, por ejemplo:

```text
2.x.x
```

Pandas está instalado correctamente.

También puedes comprobarlo mediante:

```powershell
python -m pip show pandas
```

---

# 7. Crear la estructura del proyecto

La estructura recomendada es:

```text
practica5-ml-pandas/
│
├── .venv5/
│
├── practica5a-0777.py
├── practica5b-0777.py
├── practica5c-0777.py
├── practica5d-0777.py
├── practica5e-0777.py
│
└── requirements.txt
```

Los cinco programas serán independientes y cada uno trabajará con una situación sencilla de la vida real.

---

# 8. Crear `practica5a-0777.py`

### Situación real: calificaciones de estudiantes

Crea el archivo:

```text
practica5a-0777.py
```

Código:

```python
import pandas as pd

datos = {
    "Nombre": ["Ana", "Luis", "María", "Carlos", "Sofía"],
    "Calificacion": [9, 8, 10, 7, 9]
}

df = pd.DataFrame(datos)

print("=== CALIFICACIONES ===")
print(df)

print("\nPromedio:", df["Calificacion"].mean())
print("Calificación mayor:", df["Calificacion"].max())
```

### ¿Qué aprende el alumno?

Aprende a:

* Importar Pandas.
* Crear un diccionario.
* Convertir datos en un `DataFrame`.
* Calcular un promedio.
* Obtener el valor máximo.

### Ejecutar

```powershell
python practica5a-0777.py
```

Resultado aproximado:

```text
=== CALIFICACIONES ===
   Nombre  Calificacion
0     Ana             9
1    Luis             8
2   María            10
3  Carlos             7
4   Sofía             9

Promedio: 8.6
Calificación mayor: 10
```

---

# 9. Crear `practica5b-0777.py`

### Situación real: gastos semanales

Código:

```python
import pandas as pd

datos = {
    "Dia": ["Lunes", "Martes", "Miércoles", "Jueves", "Viernes"],
    "Gasto": [50, 35, 80, 45, 60]
}

df = pd.DataFrame(datos)

print("=== GASTOS SEMANALES ===")
print(df)

print("\nGasto total:", df["Gasto"].sum())
print("Gasto promedio:", df["Gasto"].mean())

print("\nDías con gasto mayor a $50:")
print(df[df["Gasto"] > 50])
```

### ¿Qué aprende?

El alumno aprende a utilizar:

```python
sum()
```

para obtener el total y:

```python
mean()
```

para obtener el promedio.

También aprende a **filtrar datos**:

```python
df[df["Gasto"] > 50]
```

Esto significa:

> Mostrar únicamente los registros cuyo gasto sea mayor que 50.

Ejecutar:

```powershell
python practica5b-0777.py
```

---

# 10. Crear `practica5c-0777.py`

### Situación real: ventas de una papelería

Código:

```python
import pandas as pd

datos = {
    "Producto": ["Cuaderno", "Pluma", "Mochila", "Lápiz", "Regla"],
    "Precio": [35, 10, 250, 8, 15],
    "Cantidad": [5, 10, 2, 15, 6]
}

df = pd.DataFrame(datos)

df["Total"] = df["Precio"] * df["Cantidad"]

print("=== VENTAS DE PAPELERÍA ===")
print(df)

print("\nVenta total:", df["Total"].sum())
```

### ¿Qué aprende?

Aquí aparece una operación muy importante:

```python
df["Total"] = df["Precio"] * df["Cantidad"]
```

Pandas calcula automáticamente el total de cada producto.

Por ejemplo:

```text
Cuaderno → 35 × 5 = 175
```

Después:

```python
df["Total"].sum()
```

calcula todas las ventas.

Ejecutar:

```powershell
python practica5c-0777.py
```

---

# 11. Crear `practica5d-0777.py`

### Situación real: temperatura durante la semana

Código:

```python
import pandas as pd

datos = {
    "Dia": ["Lunes", "Martes", "Miércoles", "Jueves", "Viernes"],
    "Temperatura": [27, 29, 31, 28, 30]
}

df = pd.DataFrame(datos)

print("=== TEMPERATURAS ===")
print(df)

fila = df["Temperatura"].idxmax()

print("\nDía con mayor temperatura:", df.loc[fila, "Dia"])
print("Temperatura máxima:", df["Temperatura"].max(), "°C")
```

### ¿Qué aprende?

El alumno utiliza:

```python
idxmax()
```

para localizar la posición del valor máximo.

Después:

```python
df.loc[fila, "Dia"]
```

permite obtener el nombre del día correspondiente.

Resultado:

```text
Día con mayor temperatura: Miércoles
Temperatura máxima: 31 °C
```

Ejecutar:

```powershell
python practica5d-0777.py
```

---

# 12. Crear `practica5e-0777.py`

### Situación real: inventario de una tienda

Código:

```python
import pandas as pd

datos = {
    "Producto": ["Teclado", "Mouse", "Monitor", "USB"],
    "Existencias": [8, 20, 4, 15]
}

df = pd.DataFrame(datos)

print("=== INVENTARIO ===")
print(df)

print("\nProductos con menos de 10 unidades:")
print(df[df["Existencias"] < 10])

print("\nExistencias totales:", df["Existencias"].sum())
```

### ¿Qué aprende?

El alumno aprende a identificar productos con pocas existencias mediante:

```python
df[df["Existencias"] < 10]
```

Resultado:

```text
Productos con menos de 10 unidades:

  Producto  Existencias
0  Teclado            8
2  Monitor            4
```

Ejecutar:

```powershell
python practica5e-0777.py
```

---

# 13. Crear `requirements.txt`

Cuando todos los programas funcionen, ejecuta:

```powershell
python -m pip freeze > requirements.txt
```

Este archivo registra las bibliotecas instaladas en el proyecto.

Posteriormente, las dependencias pueden instalarse con:

```powershell
python -m pip install -r requirements.txt
```

---

# 14. Resumen de los cinco ejemplos

| Archivo              | Situación real | Conceptos de Pandas            |
| -------------------- | -------------- | ------------------------------ |
| `practica5a-0777.py` | Calificaciones | `DataFrame`, `mean()`, `max()` |
| `practica5b-0777.py` | Gastos         | `sum()`, `mean()`, filtros     |
| `practica5c-0777.py` | Ventas         | operaciones entre columnas     |
| `practica5d-0777.py` | Temperaturas   | `idxmax()`, `loc[]`, `max()`   |
| `practica5e-0777.py` | Inventario     | filtros y `sum()`              |

---

# 15. Estructura final

```text
practica5-ml-pandas/
│
├── .venv5/
│   ├── Include/
│   ├── Lib/
│   └── Scripts/
│
├── practica5a-0777.py
├── practica5b-0777.py
├── practica5c-0777.py
├── practica5d-0777.py
├── practica5e-0777.py
│
└── requirements.txt
```

**Flujo que debe seguir el alumno:**

```text
Crear carpeta
      ↓
Crear .venv5
      ↓
Activar .venv5
      ↓
Seleccionar intérprete
      ↓
Instalar Pandas
      ↓
Verificar Pandas
      ↓
Crear 5 archivos Python
      ↓
Ejecutar cada práctica
      ↓
Comprobar resultados
      ↓
Crear requirements.txt
```

### Material listo para usar

Preparé los **cinco programas, `requirements.txt` y un README** dentro de un archivo ZIP:

[Descargar proyecto `practica5-ml-pandas.zip`](sandbox:/mnt/data/practica5-ml-pandas.zip)

Los ejemplos están planteados para que un alumno de **tercer semestre** pueda ejecutarlos individualmente y relacionar cada operación de Pandas con una situación cotidiana.
