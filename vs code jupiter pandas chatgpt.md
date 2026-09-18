Sí. Siguiendo el mismo procedimiento de la práctica anterior, puedes trabajar **Pandas + Jupyter Notebook directamente desde VS Code** utilizando el entorno virtual `.venv5`.

## 1. Crear la carpeta de trabajo

Abre **VS Code** y selecciona:

**Terminal → New Terminal**

En PowerShell ejecuta:

```powershell
mkdir practica5-ml-pandas
cd practica5-ml-pandas
code .
```

**Explicación:**
Se crea la carpeta `practica5-ml-pandas` y se abre como proyecto de trabajo en VS Code.

---

## 2. Crear el entorno virtual `.venv5`

En la terminal de VS Code:

```powershell
python -m venv .venv5
```

**Explicación:**
El entorno virtual permite instalar Pandas, Jupyter e IPykernel exclusivamente para esta práctica, evitando conflictos con otras prácticas.

La estructura inicialmente será:

```text
practica5-ml-pandas/
└── .venv5/
```

---

## 3. Activar el entorno virtual

En PowerShell:

```powershell
.\.venv5\Scripts\Activate.ps1
```

Si se activó correctamente, aparecerá algo parecido a:

```text
(.venv5) PS C:\...\practica5-ml-pandas>
```

**Explicación:**
El texto `(.venv5)` indica que estamos trabajando dentro del entorno virtual.

---

## 4. Actualizar pip

Ejecuta:

```powershell
python -m pip install --upgrade pip
```

**Explicación:**
Actualiza el administrador de paquetes de Python antes de instalar las bibliotecas.

---

## 5. Instalar Pandas

Ejecuta:

```powershell
python -m pip install pandas
```

**Explicación:**
`pandas` permitirá crear y manipular tablas de datos mediante `DataFrame`.

---

## 6. Instalar Jupyter

Ejecuta:

```powershell
python -m pip install jupyter
```

**Explicación:**
Jupyter permite crear y ejecutar archivos `.ipynb`, conocidos como **Jupyter Notebooks**.

---

## 7. Instalar IPykernel

Ejecuta:

```powershell
python -m pip install ipykernel
```

**Explicación:**
`ipykernel` conecta nuestro entorno `.venv5` con Jupyter para que los notebooks utilicen el Python correcto.

---

## 8. Registrar `.venv5` como kernel de Jupyter

Ejecuta:

```powershell
python -m ipykernel install --user --name practica5-venv5 --display-name "Python (.venv5)"
```

**Explicación:**
Esto registra el entorno virtual como un **kernel de Jupyter**. Así podremos seleccionar `Python (.venv5)` dentro de cada notebook.

---

## 9. Verificar Pandas

Ejecuta:

```powershell
python -c "import pandas as pd; print('Pandas instalado correctamente'); print('Versión:', pd.__version__)"
```

Debe aparecer algo similar a:

```text
Pandas instalado correctamente
Versión: 2.x.x
```

---

## 10. Verificar Jupyter

Ejecuta:

```powershell
python -m jupyter --version
```

Debe mostrar las versiones de los componentes instalados.

---

# 11. Crear los archivos Jupyter Notebook

En el explorador de archivos de VS Code crea estos cinco archivos:

```text
practica5-ml-pandas/
│
├── .venv5/
│
├── practica5a-0777.ipynb
├── practica5b-0777.ipynb
├── practica5c-0777.ipynb
├── practica5d-0777.ipynb
└── practica5e-0777.ipynb
```

Cada archivo representa una situación sencilla de la vida real.

| Archivo                 | Situación real      | Operaciones Pandas         |
| ----------------------- | ------------------- | -------------------------- |
| `practica5a-0777.ipynb` | Calificaciones      | promedio y máximo          |
| `practica5b-0777.ipynb` | Gastos semanales    | suma, promedio y filtro    |
| `practica5c-0777.ipynb` | Ventas de papelería | operaciones entre columnas |
| `practica5d-0777.ipynb` | Temperaturas        | máximo y búsqueda          |
| `practica5e-0777.ipynb` | Inventario          | filtro y suma              |

---

# 12. Seleccionar el intérprete de Python

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
.venv5
```

Por ejemplo:

```text
Python 3.x.x ('.venv5': venv)
```

**Explicación:**
Esto indica a VS Code que los programas deben ejecutarse utilizando el Python instalado dentro de `.venv5`.

---

# 13. Seleccionar el kernel de Jupyter

Abre:

```text
practica5a-0777.ipynb
```

En la parte superior derecha del notebook selecciona:

```text
Select Kernel
```

Después selecciona:

```text
Python (.venv5)
```

Haz lo mismo con los otros cuatro notebooks.

**Importante:** el intérprete de Python y el kernel de Jupyter deben corresponder al entorno `.venv5`.

---

# 14. Práctica 5A — Calificaciones

Abre:

```text
practica5a-0777.ipynb
```

### Celda 1

```python
import pandas as pd
```

**Explicación:**
Importamos Pandas y utilizamos `pd` como nombre corto.

### Celda 2

```python
datos = {
    "Nombre": ["Ana", "Luis", "María", "Carlos", "Sofía"],
    "Calificacion": [9, 8, 10, 7, 9]
}

df = pd.DataFrame(datos)

print("=== CALIFICACIONES ===")
print(df)
```

**Explicación:**
Se crea un `DataFrame`, que podemos imaginar como una tabla.

Resultado aproximado:

```text
=== CALIFICACIONES ===
   Nombre  Calificacion
0     Ana             9
1    Luis             8
2   María            10
3  Carlos             7
4   Sofía             9
```

### Celda 3

```python
print("Promedio:", df["Calificacion"].mean())
print("Calificación mayor:", df["Calificacion"].max())
```

**Explicación:**

* `mean()` calcula el promedio.
* `max()` obtiene el valor máximo.

---

# 15. Práctica 5B — Gastos semanales

Abre:

```text
practica5b-0777.ipynb
```

### Celda 1

```python
import pandas as pd
```

### Celda 2

```python
datos = {
    "Dia": ["Lunes", "Martes", "Miércoles", "Jueves", "Viernes"],
    "Gasto": [50, 35, 80, 45, 60]
}

df = pd.DataFrame(datos)

print("=== GASTOS SEMANALES ===")
print(df)
```

### Celda 3

```python
print("Gasto total:", df["Gasto"].sum())
print("Gasto promedio:", df["Gasto"].mean())

print("\nDías con gasto mayor a $50:")
print(df[df["Gasto"] > 50])
```

**Explicación:**

* `sum()` suma los gastos.
* `mean()` calcula el promedio.
* `df[df["Gasto"] > 50]` filtra los días cuyo gasto es mayor a 50.

---

# 16. Práctica 5C — Ventas de papelería

Abre:

```text
practica5c-0777.ipynb
```

### Celda 1

```python
import pandas as pd
```

### Celda 2

```python
datos = {
    "Producto": ["Cuaderno", "Pluma", "Mochila", "Lápiz", "Regla"],
    "Precio": [35, 10, 250, 8, 15],
    "Cantidad": [5, 10, 2, 15, 6]
}

df = pd.DataFrame(datos)

df["Total"] = df["Precio"] * df["Cantidad"]

print("=== VENTAS DE PAPELERÍA ===")
print(df)
```

**Explicación:**
Se crea una nueva columna llamada `Total`.

La operación:

```python
df["Precio"] * df["Cantidad"]
```

calcula:

```text
Precio × Cantidad
```

### Celda 3

```python
print("Venta total:", df["Total"].sum())
```

**Explicación:**
Se suman todos los importes de la columna `Total`.

---

# 17. Práctica 5D — Temperaturas

Abre:

```text
practica5d-0777.ipynb
```

### Celda 1

```python
import pandas as pd
```

### Celda 2

```python
datos = {
    "Dia": ["Lunes", "Martes", "Miércoles", "Jueves", "Viernes"],
    "Temperatura": [27, 29, 31, 28, 30]
}

df = pd.DataFrame(datos)

print("=== TEMPERATURAS ===")
print(df)
```

### Celda 3

```python
fila = df["Temperatura"].idxmax()

print("Día con mayor temperatura:", df.loc[fila, "Dia"])
print("Temperatura máxima:", df["Temperatura"].max(), "°C")
```

**Explicación:**

`idxmax()` encuentra la posición donde está el valor máximo.

Después:

```python
df.loc[fila, "Dia"]
```

obtiene el nombre del día correspondiente.

---

# 18. Práctica 5E — Inventario

Abre:

```text
practica5e-0777.ipynb
```

### Celda 1

```python
import pandas as pd
```

### Celda 2

```python
datos = {
    "Producto": ["Teclado", "Mouse", "Monitor", "USB"],
    "Existencias": [8, 20, 4, 15]
}

df = pd.DataFrame(datos)

print("=== INVENTARIO ===")
print(df)
```

### Celda 3

```python
print("Productos con menos de 10 unidades:")
print(df[df["Existencias"] < 10])

print("\nExistencias totales:", df["Existencias"].sum())
```

**Explicación:**

Esta instrucción:

```python
df[df["Existencias"] < 10]
```

muestra únicamente los productos que tienen menos de 10 unidades.

---

# 19. Ejecutar un Notebook

En cada archivo `.ipynb`:

1. Seleccionar el kernel **Python (.venv5)**.
2. Colocar el cursor en la primera celda.
3. Presionar:

```text
Shift + Enter
```

4. Ejecutar las siguientes celdas de la misma manera.

También se puede utilizar el botón **▶ Run** de cada celda.

---

# 20. Guardar las dependencias

Cuando todas las prácticas funcionen, en la terminal con `.venv5` activo ejecuta:

```powershell
python -m pip freeze > requirements.txt
```

La estructura final será:

```text
practica5-ml-pandas/
│
├── .venv5/
│
├── practica5a-0777.ipynb
├── practica5b-0777.ipynb
├── practica5c-0777.ipynb
├── practica5d-0777.ipynb
├── practica5e-0777.ipynb
│
└── requirements.txt
```

El archivo `requirements.txt` permitirá conocer las bibliotecas utilizadas en el proyecto.

---

## 21. Procedimiento completo para los alumnos

El flujo de trabajo de la práctica será:

```text
Crear carpeta
     ↓
Crear .venv5
     ↓
Activar .venv5
     ↓
Instalar Pandas
     ↓
Instalar Jupyter
     ↓
Instalar IPykernel
     ↓
Registrar kernel
     ↓
Seleccionar intérprete .venv5
     ↓
Crear archivos .ipynb
     ↓
Seleccionar Python (.venv5)
     ↓
Ejecutar las celdas
     ↓
Observar los DataFrame y resultados
     ↓
Guardar requirements.txt
```

### Comando de instalación resumido

Si el alumno desea realizar las instalaciones de una sola vez después de activar `.venv5`:

```powershell
python -m pip install --upgrade pip
python -m pip install pandas jupyter ipykernel
python -m ipykernel install --user --name practica5-venv5 --display-name "Python (.venv5)"
```

Con esto, los **cinco notebooks son totalmente funcionales en VS Code**, utilizan el mismo entorno `.venv5` y permiten practicar las operaciones básicas de Pandas mediante situaciones sencillas de la vida real.
