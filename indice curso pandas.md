# Índice del curso de Pandas: de Principiante a Avanzado

Curso orientado a estudiantes de **preparatoria**, con enfoque práctico en **Python, análisis de datos, Ciencia de Datos, Machine Learning e Inteligencia Artificial**.

## Módulo 1. Introducción a Pandas — Principiante

1. **¿Qué es Pandas?**

   * Concepto de Pandas
   * Características principales
   * Ventajas
   * Aplicaciones reales
   * Pandas vs NumPy

2. **Instalación y configuración**

   * Instalación de Pandas
   * Verificación de la instalación
   * Importación de Pandas
   * Pandas en VS Code
   * Pandas en Jupyter Notebook

3. **Estructuras de datos**

   * `Series`
   * `DataFrame`
   * Índices
   * Columnas
   * Datos y etiquetas

4. **Crear Series**

   * Series desde listas
   * Series desde diccionarios
   * Índices personalizados
   * Propiedades de una Series

5. **Crear DataFrames**

   * DataFrame desde listas
   * DataFrame desde diccionarios
   * DataFrame desde NumPy
   * Crear columnas
   * Crear índices

---

# Módulo 2. Exploración de datos — Principiante

6. **Visualizar información**

   * `head()`
   * `tail()`
   * `sample()`
   * `info()`
   * `describe()`

7. **Propiedades de un DataFrame**

   * `shape`
   * `columns`
   * `index`
   * `dtypes`
   * `size`

8. **Seleccionar columnas**

   * Una columna
   * Varias columnas
   * Selección mediante listas

9. **Seleccionar filas**

   * `loc[]`
   * `iloc[]`
   * Índices
   * Rangos

10. **Modificar datos**

* Cambiar valores
* Agregar columnas
* Eliminar columnas
* Cambiar nombres

---

# Módulo 3. Importación y exportación de datos — Principiante

11. **Archivos CSV**

* `read_csv()`
* Parámetros principales
* Guardar con `to_csv()`

12. **Archivos Excel**

* `read_excel()`
* `to_excel()`
* Hojas de cálculo

13. **Archivos JSON**

* `read_json()`
* `to_json()`

14. **Otros formatos**

* TXT
* HTML
* SQL
* Parquet

15. **Proyecto práctico**

* Importar un archivo de ventas
* Explorar los datos
* Modificar información
* Exportar resultados

---

# Módulo 4. Filtrado y selección de datos — Principiante/Intermedio

16. **Condiciones**

* Comparaciones
* Operadores lógicos
* `&`
* `|`
* `~`

17. **Filtrar DataFrames**

* Filtrar por números
* Filtrar por texto
* Filtrar por fechas

18. **Filtros múltiples**

* Varias condiciones
* Condiciones combinadas
* `isin()`
* `between()`

19. **Búsqueda de datos**

* `query()`
* `filter()`
* `isin()`

20. **Ordenamiento**

* `sort_values()`
* `sort_index()`
* Orden ascendente
* Orden descendente

---

# Módulo 5. Limpieza de datos — Intermedio

21. **Datos faltantes**

* Identificar valores nulos
* `isna()`
* `isnull()`
* `notna()`

22. **Eliminar datos faltantes**

* `dropna()`
* Filas
* Columnas

23. **Reemplazar datos faltantes**

* `fillna()`
* Valores constantes
* Media
* Mediana
* Moda

24. **Datos duplicados**

* `duplicated()`
* `drop_duplicates()`

25. **Corrección de datos**

* Valores incorrectos
* Datos inconsistentes
* Conversión de tipos

26. **Renombrar información**

* `rename()`
* Columnas
* Índices

---

# Módulo 6. Manipulación y transformación — Intermedio

27. **Agregar columnas**

* Columnas calculadas
* Operaciones matemáticas
* Condiciones

28. **Eliminar información**

* `drop()`
* Eliminar filas
* Eliminar columnas

29. **Modificar valores**

* `replace()`
* `map()`
* `apply()`

30. **Funciones lambda**

* Concepto
* Aplicación en columnas
* Transformación de datos

31. **Transformación de tipos**

* `astype()`
* Conversión numérica
* `to_numeric()`

32. **Categorías**

* Datos categóricos
* `astype("category")`

---

# Módulo 7. Agrupación y análisis — Intermedio

33. **Agrupaciones con `groupby()`**

* Concepto
* Agrupar por una columna
* Agrupar por varias columnas

34. **Funciones de agregación**

* `sum()`
* `mean()`
* `count()`
* `min()`
* `max()`
* `median()`

35. **Múltiples agregaciones**

* `agg()`
* Estadísticas combinadas

36. **Tablas dinámicas**

* `pivot_table()`
* Índices
* Columnas
* Valores

37. **Crosstab**

* `crosstab()`
* Tablas de frecuencia

38. **Proyecto de análisis**

* Ventas por producto
* Ventas por mes
* Ventas por vendedor
* Productos más vendidos

---

# Módulo 8. Combinar DataFrames — Intermedio

39. **Concatenación**

* `concat()`
* Filas
* Columnas

40. **Unión de datos**

* `merge()`
* `inner`
* `left`
* `right`
* `outer`

41. **Join**

* `join()`
* Índices

42. **Comparación de métodos**

* `concat()`
* `merge()`
* `join()`

43. **Proyecto**

* Clientes
* Productos
* Ventas
* Integración de bases de datos

---

# Módulo 9. Fechas y series temporales — Intermedio

44. **Fechas en Pandas**

* `datetime`
* `to_datetime()`

45. **Extraer información**

* Año
* Mes
* Día
* Semana
* Día de la semana

46. **Filtrar por fechas**

* Rangos
* Fechas específicas

47. **Series temporales**

* `date_range()`
* Índices temporales

48. **Resampling**

* `resample()`
* Datos diarios
* Semanales
* Mensuales

49. **Análisis de ventas por tiempo**

* Ventas mensuales
* Tendencias
* Comparaciones

---

# Módulo 10. Estadística y análisis exploratorio

50. **Estadística descriptiva**

* Media
* Mediana
* Moda
* Varianza
* Desviación estándar

51. **Percentiles y cuantiles**

* `quantile()`
* Distribución de datos

52. **Correlación**

* `corr()`
* Relaciones entre variables

53. **Detección de valores atípicos**

* Outliers
* Método IQR
* Filtrado de valores extremos

54. **Análisis exploratorio de datos**

* Estructura
* Distribuciones
* Relaciones
* Tendencias

---

# Módulo 11. Pandas + NumPy + Matplotlib

55. **Pandas y NumPy**

* DataFrame → NumPy
* NumPy → DataFrame

56. **Pandas y Matplotlib**

* Gráficas de líneas
* Barras
* Histogramas
* Dispersión

57. **Visualización desde Pandas**

* `plot()`
* `hist()`
* `bar()`
* `line()`

58. **Proyecto de análisis visual**

* Importar dataset
* Limpiar datos
* Analizar datos
* Crear gráficas
* Interpretar resultados

---

# Módulo 12. Pandas para Machine Learning — Intermedio/Avanzado

59. **Preparación de datasets**

* Variables independientes
* Variable objetivo
* Características (`features`)
* Etiquetas (`target`)

60. **Limpieza para Machine Learning**

* Valores faltantes
* Datos duplicados
* Datos incorrectos

61. **Transformación de variables**

* Variables numéricas
* Variables categóricas
* Codificación

62. **División de datos**

* Entrenamiento
* Prueba
* Validación

63. **Pandas + Scikit-learn**

* Preparación de `X`
* Preparación de `y`
* Entrenamiento
* Predicción

64. **Proyecto de Machine Learning**

* Crear dataset
* Preparar datos con Pandas
* Entrenar modelo
* Realizar predicciones
* Evaluar resultados

---

# Módulo 13. Pandas avanzado

65. **MultiIndex**

* Índices múltiples
* Crear MultiIndex
* Selección de datos

66. **Operaciones avanzadas**

* `stack()`
* `unstack()`
* `melt()`
* `pivot()`

67. **Transformaciones avanzadas**

* `transform()`
* `apply()`
* `agg()`

68. **Ventanas móviles**

* `rolling()`
* `expanding()`
* Estadísticas móviles

69. **Optimización**

* Tipos de datos
* Uso de memoria
* Vectorización
* Evitar operaciones innecesarias

70. **Performance**

* Medición del tiempo
* Operaciones eficientes
* Procesamiento de datasets grandes

---

# Módulo 14. Pandas para Ciencia de Datos avanzada

71. **Datasets grandes**

* Lectura por bloques (`chunksize`)
* Procesamiento por partes
* Optimización de memoria

72. **Datos de múltiples fuentes**

* CSV
* Excel
* JSON
* SQL
* APIs

73. **Pandas y bases de datos**

* Conexión SQL
* `read_sql()`
* Consultas
* Exportación

74. **Pipelines de datos**

* Importación
* Limpieza
* Transformación
* Análisis
* Exportación

75. **Automatización**

* Procesamiento automático
* Generación de reportes
* Procesamiento de múltiples archivos

---

# Módulo 15. Proyectos integradores

76. **Proyecto 1 — Análisis de calificaciones**

* Importar alumnos
* Calcular promedios
* Identificar aprobados y reprobados
* Generar estadísticas

77. **Proyecto 2 — Sistema de análisis de ventas**

* Productos
* Clientes
* Vendedores
* Ventas
* Análisis mensual

78. **Proyecto 3 — Análisis de precios**

* Histórico de precios
* Variación mensual
* Promedios
* Tendencias

79. **Proyecto 4 — Análisis de datos reales**

* Obtener dataset
* Limpieza
* Exploración
* Estadística
* Visualización

80. **Proyecto 5 — Preparación de datos para IA**

* Importar dataset
* Limpiar datos
* Transformar variables
* Crear `X` e `y`
* Preparar datos para Machine Learning

81. **Proyecto final — Pipeline completo de Ciencia de Datos**

* Obtención de datos
* Limpieza
* Transformación
* Exploración
* Análisis estadístico
* Visualización
* Preparación para Machine Learning
* Interpretación de resultados
* Presentación del proyecto

---

## Ruta de aprendizaje

| Nivel                      | Módulos | Competencia                                                    |
| -------------------------- | ------- | -------------------------------------------------------------- |
| 🟢 **Principiante**        | 1–4     | Crear, consultar y filtrar DataFrames                          |
| 🟡 **Intermedio**          | 5–9     | Limpiar, transformar, agrupar y combinar datos                 |
| 🟠 **Intermedio-Avanzado** | 10–12   | Analizar datos y prepararlos para Machine Learning             |
| 🔴 **Avanzado**            | 13–14   | Trabajar con operaciones, datasets y flujos de datos avanzados |
| 🔵 **Integrador**          | 15      | Desarrollar proyectos completos de Ciencia de Datos            |

**Resultado esperado:** al finalizar el curso, el estudiante podrá utilizar **Pandas para importar, limpiar, transformar, analizar y visualizar datos**, así como preparar datasets para **Machine Learning e Inteligencia Artificial**.
