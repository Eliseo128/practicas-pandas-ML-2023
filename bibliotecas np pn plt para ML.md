Claro. A continuación presento el procedimiento **paso a paso, desde cero y totalmente funcional**, pensado para alumnos de **tercer semestre de preparatoria** que trabajarán con **VS Code + Python**.

# Práctica 5: Instalación de bibliotecas para Machine Learning

**Carpeta del proyecto:** `p5-biblioteca-0777`
**Entorno virtual:** `.venv-p5-0777`

Bibliotecas:

* **NumPy:** operaciones numéricas y arreglos.
* **Pandas:** manejo y análisis de datos.
* **Matplotlib:** creación de gráficas.
* **Scikit-learn:** herramientas básicas de Machine Learning.

---

## 1. Crear la carpeta `p5-biblioteca-0777`

Se recomienda crear una carpeta general para las prácticas.

Por ejemplo:

```text
C:\Users\TuUsuario\Documents\practicas
```

Dentro de ella se creará:

```text
p5-biblioteca-0777
```

### Desde el Explorador de Windows

1. Abrir **Explorador de archivos**.
2. Ir a la carpeta donde se guardarán las prácticas.
3. Crear una nueva carpeta.
4. Asignar el nombre:

```text
p5-biblioteca-0777
```

La estructura inicial será:

```text
practicas
└── p5-biblioteca-0777
```

---

# 2. Abrir la carpeta con VS Code

### Opción A: desde VS Code

1. Abrir **Visual Studio Code**.
2. Seleccionar:

**Archivo → Abrir carpeta**

3. Buscar:

```text
p5-biblioteca-0777
```

4. Seleccionar **Seleccionar carpeta**.

En el panel izquierdo deberá aparecer:

```text
P5-BIBLIOTECA-0777
```

---

### Opción B: desde una terminal

También se puede abrir directamente desde una terminal ubicada dentro de la carpeta:

```powershell
code .
```

El punto `.` significa:

> Abrir en VS Code la carpeta actual.

---

# 3. Abrir la terminal de VS Code

En VS Code seleccionar:

**Terminal → Nuevo terminal**

También se puede utilizar:

```text
Ctrl + Shift + `
```

La terminal aparecerá normalmente en la parte inferior.

Debe mostrar una ubicación similar a:

```powershell
PS C:\Users\TuUsuario\Documents\practicas\p5-biblioteca-0777>
```

### Verificar la versión de Python

Ejecutar:

```powershell
python --version
```

Por ejemplo:

```text
Python 3.13.7
```

También se puede probar:

```powershell
py --version
```

---

# 4. Crear el entorno virtual `.venv-p5-0777`

El entorno virtual permite instalar las bibliotecas **solamente para esta práctica**, evitando conflictos con otros proyectos.

En la terminal de VS Code ejecutar:

```powershell
python -m venv .venv-p5-0777
```

Esperar a que termine el proceso.

La estructura será:

```text
p5-biblioteca-0777
└── .venv-p5-0777
```

> **Importante:** no es necesario modificar manualmente los archivos que aparecen dentro de `.venv-p5-0777`.

---

# 5. Activar el entorno virtual

En Windows PowerShell ejecutar:

```powershell
.\.venv-p5-0777\Scripts\Activate.ps1
```

Si se activó correctamente, al inicio de la línea aparecerá algo parecido a:

```text
(.venv-p5-0777) PS C:\Users\TuUsuario\Documents\practicas\p5-biblioteca-0777>
```

La aparición de:

```text
(.venv-p5-0777)
```

indica que el entorno virtual está activo.

---

## Si PowerShell bloquea la activación

Si aparece un mensaje relacionado con la ejecución de scripts, se puede utilizar la terminal **Command Prompt (CMD)** de VS Code.

Seleccionar:

**Terminal → Nueva terminal**

y elegir **Command Prompt**.

Después ejecutar:

```cmd
.venv-p5-0777\Scripts\activate
```

Debe aparecer:

```text
(.venv-p5-0777)
```

---

# 6. Actualizar `pip`

Con el entorno virtual activado:

```powershell
python -m pip install --upgrade pip
```

`pip` es la herramienta que utilizaremos para instalar las bibliotecas de Python.

---

# 7. Instalar NumPy

Ejecutar:

```powershell
python -m pip install numpy
```

Esperar a que termine la instalación.

### Verificar NumPy

Ejecutar:

```powershell
python -c "import numpy; print(numpy.__version__)"
```

Si aparece un número de versión, por ejemplo:

```text
2.x.x
```

NumPy está instalado correctamente.

---

# 8. Instalar Pandas

Ejecutar:

```powershell
python -m pip install pandas
```

### Verificar Pandas

```powershell
python -c "import pandas; print(pandas.__version__)"
```

Debe mostrar la versión instalada.

---

# 9. Instalar Matplotlib

Ejecutar:

```powershell
python -m pip install matplotlib
```

### Verificar Matplotlib

```powershell
python -c "import matplotlib; print(matplotlib.__version__)"
```

Debe aparecer la versión instalada.

---

# 10. Instalar Scikit-learn

La biblioteca se instala mediante el paquete:

```text
scikit-learn
```

Ejecutar:

```powershell
python -m pip install scikit-learn
```

### Verificar Scikit-learn

Importante: aunque se instala como `scikit-learn`, en Python se importa como `sklearn`.

Ejecutar:

```powershell
python -c "import sklearn; print(sklearn.__version__)"
```

---

# 11. Instalar las cuatro bibliotecas en un solo comando

También se puede hacer todo de una vez:

```powershell
python -m pip install numpy pandas matplotlib scikit-learn
```

Después verificar:

```powershell
python -c "import numpy, pandas, matplotlib, sklearn; print('Bibliotecas instaladas correctamente')"
```

Si aparece:

```text
Bibliotecas instaladas correctamente
```

la instalación básica está lista.

---

# 12. Verificar las bibliotecas con `pip`

Con el entorno virtual activo:

```powershell
python -m pip list
```

Debe aparecer una lista donde se encuentren, entre otras:

```text
numpy
pandas
matplotlib
scikit-learn
```

También podemos utilizar:

```powershell
python -m pip show numpy
python -m pip show pandas
python -m pip show matplotlib
python -m pip show scikit-learn
```

---

# 13. Seleccionar el intérprete de Python en VS Code

Este paso es **muy importante**.

Debemos indicarle a VS Code que utilice el Python que pertenece a:

```text
.venv-p5-0777
```

### Procedimiento

1. Presionar:

```text
Ctrl + Shift + P
```

2. Escribir:

```text
Python: Select Interpreter
```

3. Seleccionar:

**Python: Select Interpreter**

4. Aparecerán diferentes intérpretes.

Seleccionar el que corresponda al entorno:

```text
.venv-p5-0777
```

En Windows normalmente tendrá una ruta similar a:

```text
.\.venv-p5-0777\Scripts\python.exe
```

o:

```text
Python 3.x.x ('.venv-p5-0777': venv)
```

### Comprobar desde la terminal

Ejecutar:

```powershell
python -c "import sys; print(sys.executable)"
```

Debe mostrar una ruta que contenga:

```text
p5-biblioteca-0777\.venv-p5-0777\Scripts\python.exe
```

Esto confirma que estamos utilizando el Python correcto.

---

# 14. Crear los archivos Python

Dentro de:

```text
p5-biblioteca-0777
```

crear los siguientes cuatro archivos:

```text
p5-biblioteca-0777
│
├── .venv-p5-0777
│
├── p5-numpy-0777.py
├── p5-pandas-0777.py
├── p5-Matplotlib-0777.py
└── p5-Scikit-learn-0777.py
```

> El nombre del archivo `p5-Matplotlib-0777.py` y `p5-Scikit-learn-0777.py` puede conservarse exactamente como se solicita.

---

# 15. Archivo `p5-numpy-0777.py`

## Objetivo

Utilizar NumPy para crear un arreglo y realizar una operación matemática.

Escribir:

```python
import numpy as np

# Crear un arreglo de calificaciones
calificaciones = np.array([80, 90, 75, 95, 85])

# Calcular el promedio
promedio = np.mean(calificaciones)

print("CALIFICACIONES")
print(calificaciones)

print("Promedio:", promedio)
```

### Ejecutar

En la terminal:

```powershell
python p5-numpy-0777.py
```

### Resultado esperado

```text
CALIFICACIONES
[80 90 75 95 85]
Promedio: 85.0
```

### Explicación

```python
import numpy as np
```

Importa NumPy y utiliza `np` como nombre corto.

```python
np.array(...)
```

Crea un arreglo numérico.

```python
np.mean(...)
```

Calcula el promedio de los valores.

---

# 16. Archivo `p5-pandas-0777.py`

## Objetivo

Crear una pequeña tabla de datos utilizando Pandas.

Escribir:

```python
import pandas as pd

# Crear información de alumnos
datos = {
    "Nombre": ["Ana", "Luis", "Carlos", "María"],
    "Calificacion": [85, 90, 78, 95]
}

# Crear un DataFrame
alumnos = pd.DataFrame(datos)

print("LISTA DE ALUMNOS")
print(alumnos)

# Calcular el promedio
promedio = alumnos["Calificacion"].mean()

print("\nPromedio del grupo:", promedio)
```

### Ejecutar

```powershell
python p5-pandas-0777.py
```

### Resultado aproximado

```text
LISTA DE ALUMNOS
   Nombre  Calificacion
0     Ana            85
1    Luis            90
2  Carlos            78
3   María            95

Promedio del grupo: 87.0
```

### Explicación

```python
import pandas as pd
```

Importa Pandas.

```python
pd.DataFrame(datos)
```

Convierte los datos en una tabla.

Un `DataFrame` puede imaginarse como una **tabla formada por filas y columnas**.

```python
alumnos["Calificacion"].mean()
```

Selecciona la columna de calificaciones y calcula su promedio.

---

# 17. Archivo `p5-Matplotlib-0777.py`

## Objetivo

Crear una gráfica sencilla con las calificaciones.

Escribir:

```python
import matplotlib.pyplot as plt

# Datos
nombres = ["Ana", "Luis", "Carlos", "María"]
calificaciones = [85, 90, 78, 95]

# Crear gráfica
plt.bar(nombres, calificaciones)

# Títulos y etiquetas
plt.title("Calificaciones de alumnos")
plt.xlabel("Alumnos")
plt.ylabel("Calificación")

# Mostrar gráfica
plt.show()
```

### Ejecutar

```powershell
python p5-Matplotlib-0777.py
```

Se abrirá una ventana con una **gráfica de barras**.

### Explicación

```python
import matplotlib.pyplot as plt
```

Importa el módulo de gráficas de Matplotlib.

```python
plt.bar(...)
```

Crea una gráfica de barras.

```python
plt.title(...)
```

Establece el título.

```python
plt.xlabel(...)
```

Coloca el nombre del eje X.

```python
plt.ylabel(...)
```

Coloca el nombre del eje Y.

```python
plt.show()
```

Muestra la gráfica.

---

# 18. Archivo `p5-Scikit-learn-0777.py`

## Objetivo

Realizar un ejemplo introductorio de **Machine Learning** utilizando regresión lineal.

En este ejemplo se utilizarán horas de estudio para intentar estimar una calificación.

Escribir:

```python
from sklearn.linear_model import LinearRegression

# Datos de entrenamiento
horas_estudio = [[1], [2], [3], [4], [5]]
calificaciones = [55, 60, 70, 75, 85]

# Crear el modelo
modelo = LinearRegression()

# Entrenar el modelo
modelo.fit(horas_estudio, calificaciones)

# Realizar una predicción
horas_nuevas = [[6]]
prediccion = modelo.predict(horas_nuevas)

print("Horas de estudio:", horas_nuevas[0][0])
print("Calificación estimada:", round(prediccion[0], 2))
```

### Ejecutar

```powershell
python p5-Scikit-learn-0777.py
```

El resultado será similar a:

```text
Horas de estudio: 6
Calificación estimada: 89.5
```

El valor exacto puede depender de los datos utilizados.

### Explicación sencilla

Los datos:

```python
horas_estudio = [[1], [2], [3], [4], [5]]
```

representan las horas estudiadas.

Los datos:

```python
calificaciones = [55, 60, 70, 75, 85]
```

representan las calificaciones obtenidas.

Se crea un modelo:

```python
modelo = LinearRegression()
```

Después se entrena:

```python
modelo.fit(horas_estudio, calificaciones)
```

Finalmente se solicita una predicción:

```python
modelo.predict([[6]])
```

En este caso se intenta estimar la calificación correspondiente a **6 horas de estudio**.

> Este es un ejemplo introductorio de Machine Learning. La predicción no significa que estudiar determinado número de horas garantice una calificación; simplemente muestra cómo funciona técnicamente un modelo de regresión con los datos de entrenamiento proporcionados.

---

# 19. Ejecutar todos los programas

Con:

```text
(.venv-p5-0777)
```

visible en la terminal, ejecutar uno por uno:

```powershell
python p5-numpy-0777.py
```

Después:

```powershell
python p5-pandas-0777.py
```

Después:

```powershell
python p5-Matplotlib-0777.py
```

Finalmente:

```powershell
python p5-Scikit-learn-0777.py
```

---

# 20. Crear `requirements.txt`

Una buena práctica para proyectos de Python es guardar las bibliotecas utilizadas.

Con el entorno virtual activado:

```powershell
python -m pip freeze > requirements.txt
```

La estructura quedará:

```text
p5-biblioteca-0777
│
├── .venv-p5-0777
│
├── p5-numpy-0777.py
├── p5-pandas-0777.py
├── p5-Matplotlib-0777.py
├── p5-Scikit-learn-0777.py
└── requirements.txt
```

El archivo `requirements.txt` contendrá las bibliotecas instaladas y sus versiones.

Para instalar posteriormente las dependencias del proyecto se utilizaría:

```powershell
python -m pip install -r requirements.txt
```

---

# 21. Comprobación final de la práctica

El alumno debe comprobar:

| Elemento              | Comprobación                 |
| --------------------- | ---------------------------- |
| Carpeta               | `p5-biblioteca-0777`         |
| Entorno virtual       | `.venv-p5-0777`              |
| Entorno activo        | Aparece `(.venv-p5-0777)`    |
| Intérprete            | Python de `.venv-p5-0777`    |
| NumPy                 | `import numpy` funciona      |
| Pandas                | `import pandas` funciona     |
| Matplotlib            | `import matplotlib` funciona |
| Scikit-learn          | `import sklearn` funciona    |
| Programa NumPy        | Se ejecuta correctamente     |
| Programa Pandas       | Se ejecuta correctamente     |
| Programa Matplotlib   | Muestra la gráfica           |
| Programa Scikit-learn | Realiza una predicción       |
| Dependencias          | Existe `requirements.txt`    |

## Resultado final esperado

```text
p5-biblioteca-0777
│
├── .venv-p5-0777/
│
├── p5-numpy-0777.py
├── p5-pandas-0777.py
├── p5-Matplotlib-0777.py
├── p5-Scikit-learn-0777.py
│
└── requirements.txt
```

### Conceptos que debe identificar el alumno

**NumPy →** trabajar con datos numéricos.
**Pandas →** organizar y analizar datos en tablas.
**Matplotlib →** visualizar datos mediante gráficas.
**Scikit-learn →** construir y utilizar modelos de Machine Learning.

Esta práctica deja preparado el entorno para continuar posteriormente con ejercicios de **análisis de datos, visualización y construcción de modelos de Machine Learning**.
