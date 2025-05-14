# ⚙️ 2. Primeros Pasos con Git
Git es un sistema de control de versiones que permite gestionar y rastrear cambios en archivos de código. Para comenzar, se instala Git, se configura el usuario con git config, y se inicia un repositorio con git init. Luego, se pueden agregar archivos con git add y guardar cambios usando git commit
### 🎯 Objetivo
El objetivo de Git es gestionar el control de versiones de un proyecto, facilitando la colaboración simultánea entre múltiples desarrolladores, quienes pueden realizar cambios y mejoras de forma estructurada y eficiente dentro de un repositorio compartido.
### 🧠 ¿Qué es Git?
Git es un sofware de control de versiones de una carpeta que nos permite tener diferentes versiones de una carpeta
Perfecto. A continuación te presento la sección **"💾 Instalación de Git"** en formato **R Markdown (.Rmd)**, con un tono profesional, claro y adecuado para un informe universitario.

---

## 💾 Instalación de Git

Git es una herramienta esencial para el control de versiones en proyectos de software. Antes de poder utilizarla, es necesario instalarla correctamente según el sistema operativo. A continuación, se describen los pasos para su instalación en los sistemas más comunes.

### 🔹 Instalación en Windows

1. Acceder al sitio oficial de Git: [https://git-scm.com/download/win](https://git-scm.com/download/win).
2. Descargar el instalador adecuado para el sistema (32 o 64 bits).
3. Ejecutar el archivo `.exe` y seguir las instrucciones del asistente de instalación.
4. Durante el proceso, se recomienda mantener las opciones por defecto, especialmente las relacionadas con el editor predeterminado, la línea de comandos y la integración con Git Bash.

> 💡 *Consejo:* Al finalizar, se puede abrir **Git Bash** desde el menú de inicio para comenzar a utilizar Git.

### 🍎 Instalación en macOS

Existen dos métodos principales para instalar Git en macOS:

- **Usando Homebrew** (recomendado):

```bash
brew install git
````

* **Descarga manual** desde el sitio oficial: [https://git-scm.com/download/mac](https://git-scm.com/download/mac)

Ambos métodos instalarán la última versión estable de Git disponible para macOS.

### 🐧 Instalación en Linux

En sistemas Linux, Git puede instalarse mediante el gestor de paquetes correspondiente. A continuación se presentan los comandos para las distribuciones más comunes:

* **Debian/Ubuntu**:

```bash
sudo apt update
sudo apt install git
```

* **Fedora**:

```bash
sudo dnf install git
```

* **Arch Linux**:

```bash
sudo pacman -S git
```

#### ✔️ Verificación de la instalación

Una vez finalizado el proceso de instalación, se recomienda verificar que Git esté correctamente instalado. Para ello, se debe ejecutar el siguiente comando en la terminal o línea de comandos:

```bash
git --version
```

Este comando debe mostrar la versión de Git instalada, lo cual confirma que la herramienta está lista para ser utilizada.

---


## ⚙️ Configuración inicial de Git

Antes de comenzar a trabajar con Git, es fundamental establecer la identidad del usuario para que cada confirmación (commit) quede correctamente registrada. Esta sección explica cómo configurar el nombre y el correo electrónico globales, así como verificar todos los ajustes disponibles.

#### 🔹 Definir nombre de usuario

Se utiliza el siguiente comando para asociar su nombre al autor de los commits:

```bash
git config --global user.name "Tu Nombre Completo"
````

> **Nota:** Reemplace `"Tu Nombre Completo"` por el nombre que desea que aparezca en el historial de versiones.

#### 🔹 Definir correo electrónico

Git requiere un correo electrónico válido para identificar al autor de cada cambio. Configurelo con:

```bash
git config --global user.email "tu.email@dominio.com"
```

> **Nota:** Utilice la dirección de correo institucional o personal que esté vinculada a su cuenta de GitHub o al servicio de repositorios que vaya a emplear.

#### 🔹 Verificación de la configuración

Para consultar todas las opciones configuradas (tanto globales como locales), ejecute:

```bash
git config --list
```

Este comando listará pares clave-valor que incluyen `user.name`, `user.email` y otras preferencias. Asegúrese de que los valores sean correctos:

```
user.name=Tu Nombre Completo
user.email=tu.email@dominio.com
...
```

#### 🔹 Configuración adicional recomendada

Aunque es opcional, puede definir el editor predeterminado para mensajes de commit y mejorar la experiencia de uso:

#### Establecer VS Code como editor predeterminado
```bash
git config --global core.editor "code --wait"
```

## 🖥️ Comandos básicos de la terminal

#### 📁 Crear tu primer repositorio

Una vez que se han instalado y configurado las herramientas necesarias, el siguiente paso consiste en crear y gestionar un repositorio Git en un proyecto nuevo o existente. En esta sección se describen los pasos y comandos principales para inicializar un repositorio, preparar archivos, confirmar cambios y explorar el historial de versiones.

#### 🔹 Crear el directorio de trabajo

1. Crear una carpeta para el proyecto y situarse en ella:
   ```bash
   mkdir MiProyecto
   cd MiProyecto


#### 🔹 Inicializar el repositorio

* **`git init`**
  Inicializa un nuevo repositorio Git en el directorio actual y crea la carpeta oculta `.git`:

  ```bash
  git init
  ```

  Tras este comando, el proyecto está bajo control de versiones, aunque aún no contiene historial de confirmaciones.

#### 🔹 Preparar (staging) archivos

1. Crear o modificar archivos en el directorio de trabajo, por ejemplo:

   ```bash
   touch README.md
   ```
2. Añadir un archivo al área de preparación (staging area):

   ```bash
   git add "nombre_del_archivo"
   ```
3. Si es necesario revertir la adición al área de preparación:

   ```bash
   git rm --cached "nombre_del_archivo"
   ```

> **Nota:**
>
> * `git status` muestra en todo momento el estado del directorio de trabajo y del área de preparación.
> * Para un resumen compacto, se puede usar `git status -s`.

#### 🔹 Crear un commit (confirmación)

* **`git commit -m "Descripción del cambio" -a`**
  Crea un nuevo commit que incluye todos los archivos previamente añadidos al área de preparación y, con `-a`, añade automáticamente los cambios en archivos rastreados:

  ```bash
  git commit -m "Añadir README inicial" -a
  ```

> **Concepto clave:**
> Un *commit* es una “fotografía” del estado actual del proyecto: captura todos los cambios preparados hasta ese momento.

#### 🔹 Eliminar y restaurar archivos

* Eliminar un archivo del directorio de trabajo:

  ```bash
  rm "nombre_del_archivo"
  ```
* Restaurar la versión confirmada al área de trabajo:

  ```bash
  git restore "nombre_del_archivo"
  ```

#### 🔹 Navegar entre commits

* Volver al último commit realizado:

  ```bash
  git checkout
  ```
#### 🔄 Modos de `git reset`

Dentro de la sección de “Navegar entre commits”, puede añadir el siguiente bloque que describe los tres modos principales de `git reset`:

##### 🔹 `--soft`

```bash
git reset --soft <ID-del-commit>
````

* Mueve el puntero `HEAD` al commit especificado.
* **Conserva** tanto el área de preparación (staging) como el directorio de trabajo tal como estaban.
* Útil si deseas rehacer uno o varios commits sin perder los cambios preparados.

##### 🔹 `--mixed` (modo por defecto)

```bash
git reset --mixed <ID-del-commit>
```

* Mueve `HEAD` al commit indicado.
* **Deshace** la preparación de los cambios (los quita del área de staging) pero **mantiene** los archivos modificados en el directorio de trabajo.
* Es el comportamiento por defecto al invocar `git reset <ID>` sin especificar opción.

##### 🔹 `--hard`

```bash
git reset --hard <ID-del-commit>
```

* Mueve `HEAD` al commit dado.
* **Descarta** todos los cambios en el área de staging y en el directorio de trabajo, volviendo el proyecto exactamente al estado de ese commit.
* Debe usarse con precaución, ya que se pierden los cambios no confirmados.

  ```
* Ver las diferencias entre el área de preparación y el último commit:

  ```bash
  git diff --staged
  ```

#### 🔹 Explorar el historial

* Listar todos los commits con detalle:

  ```bash
  git log
  ```
* Mostrar un resumen compacto de los commits:

  ```bash
  git log --oneline
  ```
* Mostrar diferencias entre dos commits (por rango de hashes):

  ```bash
  git log <hash1> <hash2>
  ```

> **Configuración opcional:**
> Para abreviar los hashes en los logs, se puede ajustar:
>
> ```bash
> git config --global core.abbrev "n"
> ```

#### 🔹 Gestión de ramas

* Ver las ramas existentes:

  ```bash
  git branch
  ```
* Crear una nueva rama:

  ```bash
  git branch <nombre_rama>
  ```
* Cambiarse a una rama existente:

  ```bash
  git switch <nombre_rama>
  ```
* Crear y cambiar a una nueva rama en un solo paso:

  ```bash
  git switch -c <nombre_rama>
  ```
* Eliminar una rama local (sin estar en ella):

  ```bash
  git branch -d <nombre_rama>
  ```
* Renombrar una rama:

  ```bash
  git branch -m <nombre_antiguo> <nombre_nuevo>
  ```

  o, si ya se está en la rama:

  ```bash
  git branch -n <nuevo_nombre>
  ```

## 📁 Crear tu primer repositorio

## 🧬 Estructura interna del repositorio

## 🖼️ Opciones visuales (GUI)

## ✅ Resultado esperado
