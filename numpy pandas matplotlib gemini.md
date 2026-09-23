¡Hola! Qué gusto acompañarte. Como docente de Machine Learning, he estructurado esta guía paso a paso para que tus estudiantes de 3.º semestre de preparatoria puedan configurar su entorno de trabajo de forma ordenada, limpia y profesional.

---

## 1. Crear la carpeta del proyecto

Para mantener todo organizado, primero creamos un directorio específico desde la terminal del sistema operativo (CMD, PowerShell o Terminal de macOS/Linux).

```bash
mkdir p5-biblioteca-0777
cd p5-biblioteca-0777

```

---

## 2. Abrir la carpeta en VS Code

Una vez posicionados dentro de la carpeta desde la terminal, ejecutamos:

```bash
code .

```

*Nota: También pueden abrir VS Code manualmente, ir al menú **Archivo > Abrir carpeta...** y seleccionar `p5-biblioteca-0777`.*

---

## 3. Abrir la terminal integrada en VS Code

Dentro de Visual Studio Code:

1. Usen el atajo de teclado: `Ctrl + Shift + \`` (en Windows/Linux) o `Cmd + Shift + `` (en macOS).
2. O bien, diríjanse al menú superior: **Terminal > Nueva terminal**.

---

## 4. Crear el entorno virtual `.venv-p5-0777`

El entorno virtual aísla las librerías de este proyecto para no interferir con otras aplicaciones.

**En Windows / macOS / Linux:**

```bash
python -m venv .venv-p5-0777

```

*(Si en macOS/Linux usan Python 3 de forma explícita, ejecuten `python3 -m venv .venv-p5-0777`).*

---

## 5. Activar el entorno virtual

Según el sistema operativo, ejecuten el comando correspondiente en la terminal de VS Code:

* **En Windows (PowerShell):**
```powershell
Wait-Event ; .venv-p5-0777\Scripts\Activate.ps1

```


* **En Windows (CMD / Símbolo del sistema):**
```cmd
.venv-p5-0777\Scripts\activate.bat

```


* **En macOS / Linux:**
```bash
source .venv-p5-0777/bin/activate

```



> **Verificación:** Al activarse, verán el nombre `(.venv-p5-0777)` al inicio de la línea de comandos en la terminal.

---

## 6. Seleccionar el intérprete de Python recomendado

Para asegurarse de que VS Code use el entorno que acabamos de crear:

1. Presionen `Ctrl + Shift + P` (Windows/Linux) o `Cmd + Shift + P` (macOS) para abrir la **Paleta de comandos**.
2. Escriban **`Python: Select Interpreter`** y selecciónenlo.
3. Elijan la opción que incluye la ruta de su entorno recién creado:
`./.venv-p5-0777/Scripts/python.exe` (Windows) o `./.venv-p5-0777/bin/python` (macOS/Linux), la cual aparecerá etiquetada como **Recommended** o **Venv**.

---

## 7. Crear los archivos de Python

Ejecuten los siguientes comandos en la terminal de VS Code para generar los 4 archivos `.py`:

* **En Windows (PowerShell / CMD):**
```powershell
type nul > p5-numpy-0777.py
type nul > p5-pandas-0777.py
type nul > p5-Matplotlib-0777.py
type nul > p5-Scikit-learn-0777.py

```


* **En macOS / Linux:**
```bash
touch p5-numpy-0777.py p5-pandas-0777.py p5-Matplotlib-0777.py p5-Scikit-learn-0777.py

```



---

## 8. Instalar y verificar las bibliotecas

### Instalación desde la terminal

Asegúrense de tener activo el entorno virtual `(.venv-p5-0777)` e instalen las bibliotecas con `pip`:

```bash
pip install numpy pandas matplotlib scikit-learn

```

### Verificación de la instalación

Para comprobar que se instalaron correctamente y revisar las versiones cargadas:

```bash
pip list

```

O con una comprobación rápida mediante Python:

```bash
python -c "import numpy, pandas, matplotlib, sklearn; print('¡Todas las librerías se instalaron correctamente!')"

```

---

## 9. Crear el archivo de requerimientos (`requirements.txt`)

Para guardar el registro exacto de las dependencias e independizar la distribución del código:

```bash
pip freeze > requirements.txt

```

*(Si en el futuro se quiere replicar este entorno en otra máquina, solo bastará con ejecutar `pip install -r requirements.txt`).*

---

## 10. Ejemplos básicos y funcionales por archivo

A continuación, cada archivo con su código completo y explicaciones clave para los alumnos.

### Archivo 1: `p5-numpy-0777.py`

```python
# p5-numpy-0777.py
import numpy as np

# NumPy sirve para trabajar con arreglos numéricos y realizar operaciones matemáticas rápidas.

# 1. Crear una lista de calificaciones de un alumno
calificaciones = [80, 95, 70, 100, 85]

# 2. Convertir la lista a un arreglo de NumPy
arreglo_calificaciones = np.array(calificaciones)

# 3. Calcular estadísticas básicas
promedio = np.mean(arreglo_calificaciones)
calificacion_maxima = np.max(arreglo_calificaciones)

# 4. Mostrar resultados
print("--- EJEMPLO DE NUMPY ---")
print("Calificaciones:", arreglo_calificaciones)
print(f"Promedio del grupo: {promedio}")
print(f"Calificación más alta: {calificacion_maxima}")

```

> **Explicación para clase:** NumPy transforma las listas comunes de Python en "arreglos numéricos", lo que permite calcular promedios, valores máximos y operaciones matemáticas de forma súper rápida en grandes cantidades de datos.

---

### Archivo 2: `p5-pandas-0777.py`

```python
# p5-pandas-0777.py
import pandas as pd

# Pandas nos permite organizar y manipular datos en tablas (DataFrame), similar a una hoja de Excel.

# 1. Crear una tabla de datos (Diccionario de listas)
datos_estudiantes = {
    "Nombre": ["Ana", "Luis", "Carla", "Diego"],
    "Edad": [16, 17, 16, 17],
    "Promedio": [9.5, 8.0, 9.8, 7.5]
}

# 2. Convertir el diccionario en un DataFrame de Pandas
df = pd.DataFrame(datos_estudiantes)

# 3. Mostrar la tabla completa y realizar un filtro sencillo
print("--- EJEMPLO DE PANDAS ---")
print("Tabla completa de estudiantes:")
print(df)

print("\nEstudiantes con promedio mayor o igual a 9.0:")
excelentes = df[df["Promedio"] >= 9.0]
print(excelentes)

```

> **Explicación para clase:** Pandas crea objetos llamados `DataFrame`, que son exactamente como hojas de cálculo dentro de Python. Con ello podemos ordenar, filtrar y consultar información con muy pocas líneas de código.

---

### Archivo 3: `p5-Matplotlib-0777.py`

```python
# p5-Matplotlib-0777.py
import matplotlib.pyplot as plt

# Matplotlib nos ayuda a crear gráficas para visualizar información.

# 1. Datos para la gráfica (Horas de estudio vs Calificación obtenida)
horas_estudio = [1, 2, 3, 4, 5]
calificaciones = [60, 70, 80, 90, 100]

# 2. Crear la gráfica de líneas
plt.plot(horas_estudio, calificaciones, marker='o', color='b', linestyle='--')

# 3. Personalizar la gráfica con títulos y etiquetas
plt.title("Relación entre Horas de Estudio y Calificación")
plt.xlabel("Horas de Estudio")
plt.ylabel("Calificación Obtención")
plt.grid(True)

# 4. Mostrar la gráfica
print("--- EJEMPLO DE MATPLOTLIB ---")
print("Cerrar la ventana de la gráfica para finalizar la ejecución del script.")
plt.show()

```

> **Explicación para clase:** Con Matplotlib convertimos listas de números en gráficos (de líneas, barras o dispersión). En Machine Learning, graficar ayuda a entender la tendencia de los datos antes de crear cualquier modelo.

---

### Archivo 4: `p5-Scikit-learn-0777.py`

```python
# p5-Scikit-learn-0777.py
from sklearn.linear_model import LinearRegression
import numpy as np

# Scikit-learn es la biblioteca para crear modelos de Machine Learning (IA que aprende de los datos).

# 1. Datos de entrenamiento (X: Horas de estudio, Y: Calificación esperada)
# Nota: Scikit-learn requiere que X sea una matriz de 2 dimensiones (.reshape(-1, 1))
X = np.array([1, 2, 3, 4, 5]).reshape(-1, 1) 
y = np.array([60, 70, 80, 90, 100])

# 2. Crear el modelo de Regresión Lineal y entrenarlo con los datos
modelo = LinearRegression()
modelo.fit(X, y)

# 3. Predecir un nuevo valor que el modelo no ha visto previamente
# ¿Qué calificación obtendrá un alumno si estudia 6 horas?
horas_nuevas = np.array([[6]])
prediccion = modelo.predict(horas_nuevas)

# 4. Mostrar resultado de la predicción
print("--- EJEMPLO DE SCIKIT-LEARN ---")
print(f"Predicción para un alumno que estudia 6 horas: {prediccion[0]:.2f} puntos")

```

> **Explicación para clase:** Scikit-learn nos da los algoritmos de Machine Learning. En este ejemplo, el algoritmo analiza los patrones del pasado (horas vs. nota) para "predecir" el resultado de una situación futura.

---
