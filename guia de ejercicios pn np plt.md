Aquí tienes la guía de ejercicios prácticos diseñada específicamente para que los alumnos apliquen los conceptos aprendidos en los scripts anteriores. Está redactada con un lenguaje claro, contextualizada en su vida cotidiana y lista para entregarse en clase.

---

## Guía Práctica de Machine Learning: Ejercicios APLICADOS

**Materia:** Introducción a Machine Learning | **Nivel:** 3.º Semestre de Preparatoria

**Objetivo:** Modificar y analizar scripts en Python para resolver problemas con NumPy, Pandas, Matplotlib y Scikit-learn.

---

### Ejercicio 1: Análisis de Temperatura Semanal (NumPy y Pandas)

**Contexto:** Deseas analizar las temperaturas máximas registradas durante la última semana en tu ciudad para identificar los días más calurosos.

**Instrucciones:**

1. Crea un nuevo archivo llamado `ejercicio1-pandas-0777.py`.
2. Utiliza **NumPy** para definir un arreglo con las temperaturas registradas de lunes a domingo: `[28, 30, 31, 29, 35, 33, 32]`.
3. Utiliza **Pandas** para estructurar estos datos en un `DataFrame` con dos columnas: `Día` y `Temperatura (°C)`.
4. Muestra en pantalla:
* La tabla completa de temperaturas.
* El promedio semanal de temperatura (calculado con NumPy).
* Un filtro que muestre únicamente los días donde la temperatura fue superior a **31 °C** ("Días calurosos").



```python
import numpy as np
import pandas as pd

# 1. Días y temperaturas
dias = ["Lunes", "Martes", "Miércoles", "Jueves", "Viernes", "Sábado", "Domingo"]
temps = np.array([28, 30, 31, 29, 35, 33, 32])

# 2. Crear DataFrame
datos = {"Día": dias, "Temperatura (°C)": temps}
df = pd.DataFrame(datos)

# 3. Mostrar resultados y filtrado
print("--- TABLA DE TEMPERATURAS ---")
print(df)
print(f"\nTemperatura promedio: {np.mean(temps):.1f} °C")

dias_calurosos = df[df["Temperatura (°C)"] > 31]
print("\nDías calurosos (>31°C):")
print(dias_calurosos)

```

---

### Ejercicio 2: Visualización de Hábitos de Redes Sociales (Matplotlib)

**Contexto:** Hiciste una encuesta rápida entre tus compañeros sobre cuántas horas pasan al día en redes sociales según el día de la semana.

**Instrucciones:**

1. Crea un archivo llamado `ejercicio2-matplotlib-0777.py`.
2. Modifica el código de Matplotlib para graficar los siguientes datos:
* **Días de la semana (Eje X):** `["Lun", "Mar", "Mié", "Jue", "Vie", "Sáb", "Dom"]`
* **Horas en redes (Eje Y):** `[2, 1.5, 2, 2.5, 4, 5, 4.5]`


3. Personaliza la gráfica:
* Cambia el color de la línea a **verde** (`color='green'`).
* Asigna el título: `"Uso Diario de Redes Sociales"`.
* Agrega las etiquetas `"Día de la semana"` en el eje X y `"Horas"` en el eje Y.
* Muestra la cuadrícula con `plt.grid(True)`.



```python
import matplotlib.pyplot as plt

dias = ["Lun", "Mar", "Mié", "Jue", "Vie", "Sáb", "Dom"]
horas = [2, 1.5, 2, 2.5, 4, 5, 4.5]

plt.plot(dias, horas, marker='o', color='green', linestyle='-')
plt.title("Uso Diario de Redes Sociales")
plt.xlabel("Día de la semana")
plt.ylabel("Horas")
plt.grid(True)

plt.show()

```

---

### Ejercicio 3: Predicción del Costo de Boletos de Cine (Scikit-learn)

**Contexto:** Un cine ofrece descuentos según el número de boletos que compres en grupo. Deseas entrenar un modelo de Inteligencia Artificial que prediga cuánto costará una compra de boletos en cantidad mayor.

**Instrucciones:**

1. Crea un archivo llamado `ejercicio3-sklearn-0777.py`.
2. Entrena un modelo de **Regresión Lineal** con los siguientes datos conocidos:
* **Boletos comprados ($X$):** $1, 2, 3, 4, 5$
* **Costo total en pesos ($y$):** $\$80, \$150, \$210, \$260, \$300$


3. Utiliza el modelo para **predecir cuánto costaría comprar 8 boletos**.
4. Imprime el resultado con una frase clara explicando la predicción.

```python
import numpy as np
from sklearn.linear_model import LinearRegression

# Entradas (X) y salidas conocidas (y)
X = np.array([1, 2, 3, 4, 5]).reshape(-1, 1)
y = np.array([80, 150, 210, 260, 300])

# Entrenar modelo
modelo = LinearRegression()
modelo.fit(X, y)

# Realizar la predicción para 8 boletos
boletos_nuevos = np.array([[8]])
prediccion = modelo.predict(boletos_nuevos)

print(f"El costo estimado para 8 boletos es de: ${prediccion[0]:.2f} pesos")

```

---

### Criterios de Evaluación para los Estudiantes

* **Puntuación (10 pts cada ejercicio):**
* **3 pts:** Correcta ejecución sin errores de sintaxis en el entorno virtual activo `(.venv-p5-0777)`.
* **4 pts:** Uso adecuado de las funciones requeridas de cada biblioteca.
* **3 pts:** Salida clara en la consola o gráfica con títulos correctos.
