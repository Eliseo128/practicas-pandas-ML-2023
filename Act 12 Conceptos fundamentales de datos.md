¡Hola! Vamos a abordar esta sesión orientada a estudiantes de tercer semestre. Como docente, estructuraremos la clase bajo un enfoque **Basado en Problemas (ABP)**, conectando la teoría con código práctico en Python.

---

## 1. Explicación Didáctica de Conceptos

Imagina que una empresa de bienes raíces nos pide construir un sistema para **predecir el precio de una casa**. Para resolver esto con Machine Learning, primero debemos entender los elementos básicos de nuestros datos:

* **Dato (Data Point / Muestra):** Es la unidad mínima de información. En nuestro ejemplo, **una fila** de la tabla representa los datos completos de *una sola casa*.
* **Característica (Feature) / Datos de Entrada ($X$):** Son las variables independientes, los atributos o las propiedades que describen al objeto. En el modelo, actúan como las pistas o la "entrada" ($X$).
* *Ejemplos:* Tamaño en $m^2$, número de habitaciones, antigüedad, ubicación.


* **Variable Objetivo (Target) / Datos de Salida ($y$):** Es la variable dependiente, la respuesta o el valor que queremos predecir. En el entrenamiento supervised, es nuestra "salida" o etiqueta ($y$).
* *Ejemplo:* El precio final de venta de la casa.



---

## 2. Caso Práctico en Código (Python + Pandas)

Supongamos que tenemos un archivo CSV con información sobre un servicio de entregas a domicilio y queremos predecir el **tiempo de entrega en minutos**.

### Código de Inspección e Identificación

```python
import pandas as pd

# 1. Crear un dataset de ejemplo simular a un CSV
datos = {
    'distancia_km': [2.5, 4.0, 1.2, 5.8, 3.1],
    'trafico_nivel': [1, 3, 1, 3, 2],        # 1: Bajo, 2: Medio, 3: Alto
    'edad_repartidor': [22, 35, 19, 28, 40],
    'tiempo_entrega_min': [15, 32, 10, 42, 25] # Lo que queremos predecir
}

df = pd.DataFrame(datos)

# 2. Separar Variables de Entrada (X) y Variable Objetivo (y)
X = df[['distancia_km', 'trafico_nivel', 'edad_repartidor']] # Features / Entradas
y = df['tiempo_entrega_min']                                  # Target / Salida

# 3. Mostrar estructura
print("--- DATOS DE ENTRADA (FEATURES - X) ---")
print(X.head(2))

print("\n--- VARIABLE OBJETIVO (TARGET - y) ---")
print(y.head(2))

```

### Descripción Breve del Código

* **`df`**: Representa la tabla completa de datos donde cada fila es una observación (un pedido).
* **`X` (Matriz de características):** Selecciona múltiples columnas que servirán como entradas para alimentar al algoritmo.
* **`y` (Vector objetivo):** Selecciona únicamente la columna de salida que el modelo debe aprender a predecir.

---

## 3. Reto de Aprendizaje Basado en Problemas (ABP)

> **Planteamiento del Problema para los Estudiantes:**
> Un hospital quiere implementar un modelo de Inteligencia Artificial para detectar si un paciente tiene **riesgo de diabetes** antes de realizar análisis complejos.
> Les entregan un dataset con las siguientes columnas:
> `[id_paciente, edad, nivel_glucosa, presion_arterial, indice_masa_corporal, diagnostico_diabetes]`
> **Instrucciones para la actividad:**
> 1. Identifiquen cuál es el **Target** ($y$).
> 2. Identifiquen cuáles son las **Features** ($X$).
> 3. ¿Existe alguna columna que debamos **eliminar** por no aportar información útil al aprendizaje? Justifiquen su respuesta.
> 
>
