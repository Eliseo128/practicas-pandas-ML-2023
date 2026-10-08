Claro. A continuación tienes una **secuencia completa, lógica y funcional** para enviar un proyecto que ya tienes en tu computadora desde **VS Code → Git → GitHub**, utilizando únicamente la **terminal de VS Code**.

# Guía: Enviar repositorio local a GitHub desde VS Code

## 1. Preparación

Antes de comenzar, verifica que tengas:

* VS Code instalado.
* Git instalado.
* Una cuenta en GitHub.
* Un proyecto creado en una carpeta local.
* Conexión a Internet.

Ejemplo de proyecto:

```text
C:\proyectos\mi-proyecto
```

Abre esta carpeta con **VS Code**.

---

# 2. Verificar la versión de Git

Abre VS Code y después:

**Terminal → New Terminal**

También puedes utilizar:

```text
Ctrl + `
```

Ejecuta:

```bash
git --version
```

Deberás obtener algo similar a:

```text
git version 2.51.0.windows.1
```

La versión exacta puede ser diferente.

### Si Git está instalado

Puedes continuar con el siguiente paso.

### Si aparece:

```text
'git' is not recognized as an internal or external command
```

Git no está correctamente instalado o no está agregado al PATH de Windows.

---

# 3. Configurar usuario de Git

Esta configuración identifica al autor de los commits.

Ejecuta:

```bash
git config --global user.name "Eliseo Nava"
```

Después configura tu correo:

```bash
git config --global user.email "TU_CORREO_DE_GITHUB"
```

Por ejemplo:

```bash
git config --global user.email "eliseo128@ejemplo.com"
```

**Importante:** utiliza el correo que tengas asociado a tu cuenta de GitHub, o un correo válido configurado en GitHub.

---

# 4. Verificar la configuración

Ejecuta:

```bash
git config --global user.name
```

Debe mostrar:

```text
Eliseo Nava
```

Después:

```bash
git config --global user.email
```

Debe mostrar el correo configurado.

También puedes revisar toda la configuración:

```bash
git config --global --list
```

---

# 5. Preparar el proyecto local

Supongamos que tienes:

```text
C:\proyectos\mi-proyecto
```

En VS Code selecciona:

**File → Open Folder**

y abre:

```text
C:\proyectos\mi-proyecto
```

Después abre la terminal.

Comprueba en qué carpeta estás:

```bash
pwd
```

En PowerShell puede aparecer algo parecido a:

```text
Path
----
C:\proyectos\mi-proyecto
```

También puedes utilizar:

```bash
Get-Location
```

---

# 6. Revisar los archivos del proyecto

Ejecuta:

```bash
dir
```

Por ejemplo:

```text
    main.py
    README.md
    requirements.txt
    .gitignore
```

La idea es que estés ubicado **dentro de la carpeta raíz del proyecto**.

---

# 7. Crear el archivo `.gitignore`

Antes de inicializar Git, es recomendable evitar subir archivos innecesarios.

Para un proyecto Python, por ejemplo, crea:

```text
.gitignore
```

Contenido recomendado:

```gitignore
.venv/
venv/
__pycache__/
*.pyc
.env
.vscode/
.ipynb_checkpoints/
```

Esto evita enviar al repositorio archivos como:

```text
.venv/
__pycache__/
.env
```

**No debes subir contraseñas, claves API, tokens ni archivos con información privada.**

---

# 8. Inicializar el repositorio local

En la terminal de VS Code ejecuta:

```bash
git init
```

Git responderá con algo similar a:

```text
Initialized empty Git repository in C:/proyectos/mi-proyecto/.git/
```

Esto significa que la carpeta ya es un **repositorio Git local**.

Se crea internamente:

```text
mi-proyecto/
│
├── .git/
├── .gitignore
├── main.py
├── README.md
└── requirements.txt
```

La carpeta `.git` contiene la información necesaria para administrar las versiones del proyecto.

---

# 9. Revisar el estado del repositorio

Ejecuta:

```bash
git status
```

Podrías obtener:

```text
Untracked files:

    main.py
    README.md
    requirements.txt
```

Esto significa que Git detectó los archivos, pero todavía no están preparados para el commit.

---

# 10. Agregar los archivos al área de preparación

Para agregar todos los archivos:

```bash
git add .
```

Después verifica:

```bash
git status
```

Ahora deberían aparecer como archivos preparados para realizar el commit.

---

# 11. Realizar el primer commit

Ejecuta:

```bash
git commit -m "Primer commit"
```

Git mostrará algo parecido a:

```text
[master (root-commit) abc1234] Primer commit
 3 files changed
```

El **commit** representa una versión registrada del proyecto.

Puedes utilizar un mensaje más descriptivo:

```bash
git commit -m "Agrega estructura inicial del proyecto"
```

---

# 12. Cambiar la rama principal a `main`

Para utilizar `main` como rama principal:

```bash
git branch -M main
```

Comprueba la rama:

```bash
git branch
```

Deberías observar:

```text
* main
```

---

# 13. Crear el repositorio en GitHub

Ahora debes crear el repositorio remoto.

Ingresa a:

[GitHub](https://github.com/?utm_source=chatgpt.com)

Inicia sesión.

Selecciona:

**New repository**

o el botón:

**+ → New repository**

---

# 14. Configurar el nuevo repositorio

Por ejemplo:

**Repository name:**

```text
mi-proyecto
```

Puedes agregar una descripción:

```text
Proyecto realizado con Python desde VS Code
```

Selecciona:

```text
Public
```

o:

```text
Private
```

según la finalidad del proyecto.

### Importante

Si ya tienes el proyecto local y acabas de realizar `git init`, **no selecciones**:

```text
Add a README file
```

Tampoco es necesario crear:

```text
.gitignore
License
```

desde GitHub.

Esto evita crear un historial remoto diferente al local y simplifica el primer envío.

Después selecciona:

**Create repository**

---

# 15. Copiar la dirección del repositorio remoto

GitHub mostrará una dirección similar a:

```text
https://github.com/USUARIO/mi-proyecto.git
```

Por ejemplo:

```text
https://github.com/eliseo128/mi-proyecto.git
```

La dirección real debe ser la que GitHub te proporciona.

---

# 16. Conectar el repositorio local con GitHub

Regresa a la terminal de VS Code.

Ejecuta:

```bash
git remote add origin https://github.com/USUARIO/mi-proyecto.git
```

Ejemplo:

```bash
git remote add origin https://github.com/eliseo128/mi-proyecto.git
```

Aquí:

```text
origin
```

es el nombre convencional que recibe el repositorio remoto.

---

# 17. Verificar la conexión

Ejecuta:

```bash
git remote -v
```

Deberás obtener algo parecido a:

```text
origin  https://github.com/USUARIO/mi-proyecto.git (fetch)
origin  https://github.com/USUARIO/mi-proyecto.git (push)
```

Esto confirma que el repositorio local conoce la dirección del repositorio de GitHub.

---

# 18. Enviar el repositorio local a GitHub

Ahora viene el paso principal.

Ejecuta:

```bash
git push -u origin main
```

La instrucción significa:

```text
git       → utilizar Git
push      → enviar cambios
-u        → establecer la relación de seguimiento
origin    → repositorio remoto
main      → rama que vamos a enviar
```

Git enviará tu repositorio local a GitHub.

---

# 19. Autenticación con GitHub

Dependiendo de la configuración de tu computadora, GitHub puede solicitar autenticación.

Actualmente, **no debes utilizar tu contraseña normal de GitHub como contraseña de Git** mediante HTTPS.

Puedes utilizar mecanismos de autenticación compatibles con GitHub, como:

* Git Credential Manager.
* Personal Access Token (PAT).
* GitHub CLI.
* SSH.

Para una práctica inicial en Windows, **Git Credential Manager** suele ser una opción sencilla porque permite autenticarte y conservar las credenciales de forma segura.

---

# 20. Comprobar el resultado

Regresa al navegador y actualiza tu repositorio de GitHub.

Deberías observar:

```text
mi-proyecto
│
├── .gitignore
├── main.py
├── README.md
└── requirements.txt
```

El proyecto local ya fue enviado al repositorio remoto.

---

# 21. Secuencia completa de comandos

Una vez que el proyecto está preparado, la secuencia básica queda así:

```bash
git --version
```

```bash
git config --global user.name "Eliseo Nava"
```

```bash
git config --global user.email "TU_CORREO"
```

Entrar a la carpeta del proyecto:

```bash
cd C:\proyectos\mi-proyecto
```

Inicializar:

```bash
git init
```

Revisar:

```bash
git status
```

Agregar archivos:

```bash
git add .
```

Realizar commit:

```bash
git commit -m "Primer commit"
```

Cambiar a `main`:

```bash
git branch -M main
```

Conectar GitHub:

```bash
git remote add origin https://github.com/USUARIO/mi-proyecto.git
```

Verificar:

```bash
git remote -v
```

Enviar:

```bash
git push -u origin main
```

---

# 22. ¿Qué sucede después del primer envío?

Una vez que el repositorio local ya está conectado con GitHub, **no necesitas repetir `git init` ni `git remote add origin`**.

Cuando hagas modificaciones:

```text
Proyecto local
     ↓
Modificar archivos
     ↓
git status
     ↓
git add .
     ↓
git commit
     ↓
git push
     ↓
GitHub
```

Por ejemplo:

```bash
git status
```

```bash
git add .
```

```bash
git commit -m "Actualiza funcionalidad del proyecto"
```

```bash
git push
```

---

# 23. Ejemplo completo para un alumno

Supongamos que el alumno tiene:

```text
C:\Users\Alumno\Documents\practica-python
```

Dentro:

```text
practica-python/
│
├── .gitignore
├── README.md
├── practica1.py
└── requirements.txt
```

En VS Code:

```bash
cd C:\Users\Alumno\Documents\practica-python
```

Después:

```bash
git --version
```

```bash
git config --global user.name "Nombre Alumno"
```

```bash
git config --global user.email "correo@ejemplo.com"
```

```bash
git init
```

```bash
git status
```

```bash
git add .
```

```bash
git commit -m "Primer commit de practica Python"
```

```bash
git branch -M main
```

Después de crear en GitHub el repositorio:

```text
practica-python
```

se conecta:

```bash
git remote add origin https://github.com/USUARIO/practica-python.git
```

Se verifica:

```bash
git remote -v
```

Y finalmente:

```bash
git push -u origin main
```

### Resultado

```text
VS Code
   │
   │ git init
   ↓
Repositorio local
   │
   │ git add .
   │
   │ git commit
   │
   │ git push
   ↓
Repositorio remoto
GitHub
```

## 24. Errores frecuentes

### Error 1: `remote origin already exists`

Si aparece:

```text
error: remote origin already exists
```

verifica:

```bash
git remote -v
```

Si la dirección es incorrecta:

```bash
git remote set-url origin https://github.com/USUARIO/REPOSITORIO.git
```

---

### Error 2: `src refspec main does not match any`

Normalmente significa que todavía no existe un commit.

Ejecuta:

```bash
git add .
```

```bash
git commit -m "Primer commit"
```

Después:

```bash
git branch -M main
```

y:

```bash
git push -u origin main
```

---

### Error 3: `rejected`

Si GitHub ya contiene archivos que no están en tu repositorio local, puede rechazar el envío.

En ese caso **no conviene utilizar `--force` como primera solución**. Primero hay que revisar el historial:

```bash
git pull origin main --rebase
```

Resolver cualquier conflicto que aparezca y posteriormente:

```bash
git push
```

---

## 25. Regla fundamental para los alumnos

Después de la primera configuración, para trabajar diariamente con GitHub basta recordar:

```bash
git status
git add .
git commit -m "Descripción del cambio"
git push
```

**Significado:**

| Comando      | Función                    |
| ------------ | -------------------------- |
| `git status` | Consulta el estado         |
| `git add .`  | Prepara los cambios        |
| `git commit` | Guarda una versión local   |
| `git push`   | Envía los commits a GitHub |

La idea fundamental es:

**Modificar → preparar → confirmar → enviar**

```text
ARCHIVOS
   ↓
git add .
   ↓
STAGING
   ↓
git commit
   ↓
REPOSITORIO LOCAL
   ↓
git push
   ↓
GITHUB
```
