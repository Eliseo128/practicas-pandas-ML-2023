Claro. A continuación se presenta el procedimiento **paso a paso para trabajar con Pandas desde la terminal de Visual Studio Code**, utilizando un entorno virtual llamado `.venv3` y un archivo principal `practica3.py`.

# Práctica 3: Instalación y uso de Pandas en Python

## 1. Crear la carpeta de trabajo `practica3`

Primero, abre **Visual Studio Code**.

### Opción A: Desde la terminal de VS Code

Abre la terminal con:

**Terminal → Nueva terminal**

En Windows, escribe:

```powershell
mkdir practica3
```

Entra a la carpeta:

```powershell
cd practica3
```

Para comprobar que estás dentro de la carpeta:

```powershell
pwd
```

La terminal deberá mostrar una ubicación similar a:

```text
C:\Users\TuUsuario\practica3
```

### Estructura inicial

En este momento tendremos:

```text
practica3/
```

---

# 2. Crear el entorno de trabajo `.venv3`

El entorno virtual permite instalar Pandas y otras bibliotecas **sin afectar la instalación global de Python**.

Desde la terminal, estando dentro de `practica3`, ejecuta:

```powershell
python -m venv .venv3
```

Después de unos segundos se creará:

```text
practica3/
└── .venv3/
```

### ¿Qué significa el comando?

```powershell
python -m venv .venv3
```

* `python` → ejecuta Python.
* `-m venv` → utiliza el módulo para crear entornos virtuales.
* `.venv3` → nombre que tendrá nuestro entorno virtual.

---

# 3. Activar el entorno de trabajo `.venv3`

Como estamos trabajando en **Windows con PowerShell**, ejecuta:

```powershell
.\.venv3\Scripts\Activate.ps1
```

Si se activa correctamente, aparecerá algo parecido a:

```text
(.venv3) PS C:\Users\TuUsuario\practica3>
```

La parte:

```text
(.venv3)
```

indica que el entorno virtual está activo.

### Si utilizas CMD

El comando sería:

```cmd
.venv3\Scripts\activate
```

---

# 4. Verificar que el entorno está activo

Ejecuta:

```powershell
python --version
```

Por ejemplo:

```text
Python 3.13.5
```

También podemos comprobar qué Python está utilizando la terminal:

```powershell
where.exe python
```

Deberá aparecer una ruta relacionada con:

```text
practica3\.venv3\Scripts\python.exe
```

Esto confirma que estamos utilizando el Python del entorno virtual.

---

# 5. Seleccionar el intérprete de Python en VS Code

Este paso es importante porque **VS Code debe utilizar el mismo Python del entorno `.venv3`**.

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

**Python: Select Interpreter**

### Paso 3

Selecciona el intérprete que corresponda al entorno:

```text
.venv3\Scripts\python.exe
```

Por ejemplo:

```text
Python 3.x.x ('.venv3': venv)
```

### Paso 4

En la parte inferior de VS Code deberá aparecer el intérprete seleccionado, por ejemplo:

```text
Python 3.13.x ('.venv3')
```

> **Importante:** La terminal y VS Code deben utilizar el mismo entorno `.venv3`.

---

# 6. Instalar Pandas

Con el entorno `.venv3` activado, ejecuta:

```powershell
python -m pip install pandas
```

Se instalará Pandas junto con las dependencias necesarias.

También puedes actualizar `pip` antes de instalar:

```powershell
python -m pip install --upgrade pip
```

Después:

```powershell
python -m pip install pandas
```

---

# 7. Verificar la instalación de Pandas

Existen varias formas de comprobar que Pandas se instaló correctamente.

## Método 1: Consultar la versión

En la terminal:

```powershell
python -c "import pandas as pd; print(pd.__version__)"
```

Si aparece algo similar a:

```text
2.3.2
```

Pandas está instalado correctamente.

---

## Método 2: Utilizar pip

También puedes ejecutar:

```powershell
python -m pip show pandas
```

Aparecerá información similar a:

```text
Name: pandas
Version: 2.3.2
Location: C:\Users\TuUsuario\practica3\.venv3\Lib\site-packages
```

La ubicación debe corresponder al entorno `.venv3`.

---

# 8. Crear el archivo de requerimientos

El archivo de requerimientos se utiliza para registrar las bibliotecas que necesita nuestro proyecto.

El archivo se llamará:

```text
requirements.txt
```

Como ya tenemos Pandas instalado, ejecutamos:

```powershell
python -m pip freeze > requirements.txt
```

Esto creará:

```text
requirements.txt
```

Podemos consultar su contenido:

```powershell
type requirements.txt
```

Podremos encontrar una línea similar a:

```text
pandas==2.3.2
```

También aparecerán las dependencias de Pandas, como `numpy`, `python-dateutil`, `pytz` o `tzdata`, dependiendo de la versión instalada.

### ¿Para qué sirve?

Permite instalar posteriormente las mismas dependencias mediante:

```powershell
python -m pip install -r requirements.txt
```

---

# 9. Crear el archivo `practica3.py`

En VS Code, en el **Explorador de archivos**, selecciona:

**Nuevo archivo**

Escribe:

```text
practica3.py
```

La estructura del proyecto quedará aproximadamente así:

```text
practica3/
│
├── .venv3/
│
├── practica3.py
│
└── requirements.txt
```

> La carpeta `.venv3` contiene muchos archivos internos; normalmente no necesitamos modificarlos manualmente.

---

# 10. Importar Pandas

Abre:

```text
practica3.py
```

Escribe:

```python
import pandas as pd
```

Esta es la forma habitual de importar Pandas.

### ¿Qué significa?

```python
import pandas
```

Importa la biblioteca Pandas.

Mientras que:

```python
import pandas as pd
```

importa Pandas y le asigna el alias:

```text
pd
```

Esto permite utilizar Pandas de una manera más corta.

Por ejemplo:

```python
import pandas as pd

datos = pd.DataFrame({
    "Nombre": ["Ana", "Luis", "Pedro"],
    "Edad": [17, 18, 17]
})

print(datos)
```

Resultado aproximado:

```text
  Nombre  Edad
0    Ana    17
1   Luis    18
2  Pedro    17
```

---

# 11. Ejecutar `practica3.py`

Antes de ejecutar, verifica que aparezca:

```text
(.venv3)
```

en la terminal.

Después ejecuta:

```powershell
python practica3.py
```

Si solamente tienes:

```python
import pandas as pd
```

el programa terminará sin mostrar ningún mensaje. Para comprobar visualmente que Pandas funciona, utiliza:

```python
import pandas as pd

print("Pandas instalado correctamente")
print("Versión de Pandas:", pd.__version__)
```

Ejecuta:

```powershell
python practica3.py
```

Resultado:

```text
Pandas instalado correctamente
Versión de Pandas: 2.3.2
```

---

# 12. Procedimiento completo resumido

Los comandos principales, en orden, son:

```powershell
mkdir practica3
cd practica3
python -m venv .venv3
.\.venv3\Scripts\Activate.ps1
python --version
python -m pip install --upgrade pip
python -m pip install pandas
python -c "import pandas as pd; print(pd.__version__)"
python -m pip freeze > requirements.txt
python practica3.py
```

Y dentro de `practica3.py`:

```python
import pandas as pd

print("Pandas instalado correctamente")
print("Versión:", pd.__version__)
```

## Estructura final

```text
practica3/
│
├── .venv3/
│   ├── Scripts/
│   ├── Lib/
│   └── ...
│
├── practica3.py
│
└── requirements.txt
```

### Flujo de trabajo que debe aprender el alumno

```text
Crear proyecto
      ↓
Crear .venv3
      ↓
Activar .venv3
      ↓
Seleccionar intérprete en VS Code
      ↓
Instalar Pandas
      ↓
Verificar Pandas
      ↓
Crear requirements.txt
      ↓
Crear practica3.py
      ↓
import pandas as pd
      ↓
Ejecutar programa
```

**Nota docente:** para las siguientes prácticas de Machine Learning, conviene mantener este mismo procedimiento: **un proyecto → un entorno virtual → sus dependencias en `requirements.txt` → código Python**.
