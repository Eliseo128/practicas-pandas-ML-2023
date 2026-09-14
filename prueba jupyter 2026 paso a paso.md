# Trabajar con Jupyter y NumPy desde Visual Studio Code

A continuación se muestra el procedimiento **paso a paso y en orden**, utilizando la terminal de VS Code y un entorno virtual.

---

## 1. Crear la carpeta de trabajo

Abre **Visual Studio Code**.

Abre la terminal:

```text
Terminal → Nueva terminal
```

Crea una carpeta para la práctica:

```powershell
mkdir practica_jupyter
```

Entra a la carpeta:

```powershell
cd practica_jupyter
```

La ubicación será similar a:

```text
C:\Users\TuUsuario\practica_jupyter
```

---

# 2. Crear el entorno virtual

Dentro de la carpeta `practica_jupyter`, ejecuta:

```powershell
python -m venv .venv
```

Se creará la carpeta:

```text
practica_jupyter/
│
└── .venv/
```

### Explicación

* `python` → ejecuta Python.
* `-m venv` → utiliza el módulo para crear un entorno virtual.
* `.venv` → nombre del entorno virtual.

---

# 3. Activar el entorno virtual

Si estás utilizando **PowerShell en Windows**, escribe:

```powershell
.\.venv\Scripts\Activate.ps1
```

Si la activación fue correcta, observarás algo parecido a:

```text
(.venv) PS C:\Users\TuUsuario\practica_jupyter>
```

El indicador:

```text
(.venv)
```

significa que el entorno virtual está activo.

### Si utilizas CMD

```cmd
.venv\Scripts\activate
```

---

# 4. Actualizar pip

Con el entorno virtual activado, ejecuta:

```powershell
python -m pip install --upgrade pip
```

---

# 5. Instalar NumPy

Ahora instalamos la biblioteca **NumPy**:

```powershell
python -m pip install numpy
```

NumPy es una biblioteca utilizada para trabajar con:

* Arreglos.
* Operaciones matemáticas.
* Cálculos numéricos.
* Matrices.
* Datos utilizados posteriormente en Machine Learning.

---

# 6. Instalar Jupyter

Para trabajar con archivos Notebook desde VS Code, instala Jupyter:

```powershell
python -m pip install jupyter
```

También es recomendable instalar `ipykernel` para que el entorno virtual pueda utilizarse como kernel:

```powershell
python -m pip install ipykernel
```

Puedes instalar todo en un solo comando:

```powershell
python -m pip install jupyter ipykernel numpy
```

---

# 7. Seleccionar el intérprete de Python en VS Code

Ahora debemos indicar a VS Code que utilizará el Python del entorno `.venv`.

### Paso 1

Presiona:

```text
Ctrl + Shift + P
```

### Paso 2

Escribe:

```text
Python: Select Interpreter
```

Selecciona:

```text
Python: Select Interpreter
```

### Paso 3

Selecciona el intérprete similar a:

```text
Python 3.x.x ('.venv': venv)
```

o:

```text
.\.venv\Scripts\python.exe
```

De esta forma, VS Code utilizará el Python instalado dentro de nuestro entorno virtual.

---

# 8. Crear un archivo Jupyter Notebook

En el explorador de archivos de VS Code:

1. Haz clic en **Nuevo archivo**.
2. Escribe:

```text
practica_jupyter.ipynb
```

La extensión:

```text
.ipynb
```

indica que es un archivo de **Jupyter Notebook**.

La estructura del proyecto será:

```text
practica_jupyter/
│
├── .venv/
│
└── practica_jupyter.ipynb
```

---

# 9. Seleccionar el Kernel de Jupyter

Abre el archivo:

```text
practica_jupyter.ipynb
```

En la parte superior del Notebook, selecciona:

```text
Select Kernel
```

Después selecciona el entorno:

```text
Python Environments
```

Y elige:

```text
.venv
```

Es importante seleccionar el mismo entorno virtual donde instalamos:

```text
NumPy
Jupyter
ipykernel
```

---

# 10. Verificar la instalación de NumPy

En la primera celda del Notebook escribe:

```python
import numpy as np

print("NumPy instalado correctamente")
print("Versión de NumPy:", np.__version__)
```

Ejecuta la celda utilizando el botón:

```text
▶ Ejecutar celda
```

El resultado será similar a:

```text
NumPy instalado correctamente
Versión de NumPy: 2.x.x
```

La versión puede ser diferente dependiendo de la instalación.

---

# 11. Ejemplo básico utilizando NumPy

Crea una nueva celda y escribe:

```python
import numpy as np

numeros = np.array([10, 20, 30, 40, 50])

print("Arreglo:")
print(numeros)

print("Suma:", np.sum(numeros))
print("Promedio:", np.mean(numeros))
print("Valor máximo:", np.max(numeros))
print("Valor mínimo:", np.min(numeros))
```

### Resultado esperado

```text
Arreglo:
[10 20 30 40 50]

Suma: 150
Promedio: 30.0
Valor máximo: 50
Valor mínimo: 10
```

---

# 12. Ejemplo de matriz con NumPy

En otra celda escribe:

```python
import numpy as np

matriz = np.array([
    [10, 20, 30],
    [40, 50, 60],
    [70, 80, 90]
])

print("Matriz:")
print(matriz)

print("Número de filas y columnas:")
print(matriz.shape)
```

### Resultado esperado

```text
Matriz:
[[10 20 30]
 [40 50 60]
 [70 80 90]]

Número de filas y columnas:
(3, 3)
```

---

# 13. Crear el archivo de requerimientos

Para guardar las bibliotecas instaladas en el proyecto, desde la terminal ejecuta:

```powershell
python -m pip freeze > requirements.txt
```

Se creará:

```text
requirements.txt
```

La estructura final será:

```text
practica_jupyter/
│
├── .venv/
│
├── practica_jupyter.ipynb
│
└── requirements.txt
```

Para consultar el contenido:

```powershell
type requirements.txt
```

---

# 14. Resumen de comandos en orden

Ejecuta los siguientes comandos desde la terminal de VS Code:

```powershell
mkdir practica_jupyter
cd practica_jupyter
python -m venv .venv
.\.venv\Scripts\Activate.ps1
python -m pip install --upgrade pip
python -m pip install jupyter ipykernel numpy
python -m pip freeze > requirements.txt
```

## Flujo de trabajo

```text
Crear carpeta
      ↓
Crear entorno virtual .venv
      ↓
Activar entorno virtual
      ↓
Seleccionar intérprete de Python
      ↓
Instalar Jupyter
      ↓
Instalar ipykernel
      ↓
Instalar NumPy
      ↓
Crear archivo .ipynb
      ↓
Seleccionar Kernel .venv
      ↓
Importar NumPy
      ↓
Ejecutar las celdas
```

Este procedimiento permite trabajar con **Jupyter dentro de VS Code**, utilizando un entorno virtual independiente y preparando al alumno para realizar posteriormente prácticas de **Machine Learning con NumPy, Pandas y otras bibliotecas**.
