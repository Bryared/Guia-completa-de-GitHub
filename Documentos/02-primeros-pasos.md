# ⚙️ Primeros Pasos con Git
#### 🎯 Objetivo
El objetivo de Git es gestionar el control de versiones de un proyecto, facilitando la colaboración simultánea entre múltiples desarrolladores, quienes pueden realizar cambios y mejoras de forma estructurada y eficiente dentro de un repositorio compartido.
#### 🧠 ¿Qué es Git?
Git es un sofware de control de versiones de una carpeta que nos permite tener diferentes versiones de una carpeta
#### 📝Ventajas de usar git

| Ventaja                          | Descripción                                                                                                |
| -------------------------------- | ---------------------------------------------------------------------------------------------------------- |
| Control de versiones distribuido | Cada colaborador tiene el repositorio completo, permitiendo trabajar sin conexión y mayor resiliencia.     |
| Ramificación ligera              | Creación y fusión de ramas de forma rápida y sencilla, favoreciendo flujos de trabajo basados en features. |
| Historial completo               | Registro detallado de cada cambio con autor, fecha y mensaje, facilitando auditoría y reversión.           |
| Integridad de datos              | Uso de SHA-1 para asegurar que el historial no se corrompa y detectar modificiaciones no autorizadas.      |
| Rendimiento                      | Operaciones locales rápidas (commits, diffs, logs) sin depender de un servidor central.                    |
| Colaboración fluida              | Herramientas como pull requests y forks facilitan revisiones de código y contribuciones externas.          |
| Compatibilidad y extensibilidad  | Gran ecosistema de clientes GUI, hooks, servicios remotos (GitHub, GitLab, Bitbucket) y plugins.           |

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



## 🧬 Estructura interna del repositorio

El directorio oculto `.git` contiene toda la información que Git utiliza para gestionar el historial, las referencias y la configuración del repositorio. A continuación se describen sus principales componentes:

```bash
# Mostrar la estructura principal de .git
tree -a .git
````

* **HEAD**
  Archivo que apunta a la rama o al commit actualmente revisado.

  ```text
  ref: refs/heads/main
  ```

* **config**
  Archivo de configuración local del repositorio, donde se almacenan opciones como nombre de usuario, correo y alias.

* **description**
  Breve descripción del repositorio (utilizado por algunas herramientas como GitWeb).

* **index**
  Base de datos binaria que representa el área de preparación (staging area). Aquí Git guarda el listado de archivos preparados para el siguiente commit.

* **objects/**
  Carpeta que almacena todos los objetos de Git:

  * **blobs**: contenido de los archivos
  * **trees**: estructura de directorios
  * **commits**: snapshots de proyecto
  * **tags**: anotaciones de versiones

* **refs/**
  Contiene referencias (pointers) a commits concretos:

  * **heads/**: punteros a ramas locales
  * **tags/**: punteros a versiones etiquetadas
  * **remotes/**: punteros a ramas remotas

* **logs/**
  Historial de movimientos de punteros (`HEAD`, ramas), útil para recuperar cambios ante un “reset” accidental.

* **hooks/**
  Scripts ejecutables que se disparan en eventos de Git (pre-commit, post-merge, etc.). Se incluyen ejemplos deshabilitados por defecto (`.sample`).

* **info/**
  Información adicional, como `exclude`, que permite ignorar archivos a nivel local sin modificar `.gitignore`.

---

Conocer esta estructura facilita la comprensión profunda de cómo Git almacena y recupera información, así como permite la resolución avanzada de problemas y la personalización de hooks y configuraciones.\`\`\`


## 🖼️ Opciones visuales (GUI)

Para quienes prefieren interfaces gráficas en lugar de la línea de comandos, existen diversas aplicaciones que facilitan la gestión de repositorios Git. A continuación se presentan cuatro alternativas populares, junto con sus características principales y enlaces oficiales.

### 🔹 GitHub Desktop

- **Descripción:** Cliente oficial de GitHub, diseñado para integrarse de forma nativa con repositorios alojados en GitHub y GitHub Enterprise.  
- **Características clave:**  
  - Sincronización automática con GitHub (push/pull).  
  - Gestión de ramas y resolución de conflictos mediante interfaz visual.  
  - Visualización clara de diferencias y estados de archivos.  
- **Enlace:** <https://desktop.github.com/>

### 🔹 GitKraken

- **Descripción:** Cliente multiplataforma (Windows, macOS, Linux) con interfaz intuitiva basada en gráficos de árbol para visualizar el historial de commits y ramas.  
- **Características clave:**  
  - Editor integrado de merge y resolución de conflictos.  
  - Integración con múltiples servicios (GitHub, GitLab, Bitbucket).  
  - Soporte para flujos de trabajo con Git LFS y submódulos.  
- **Enlace:** <https://www.gitkraken.com/>

### 🔹 Sourcetree

- **Descripción:** Aplicación gratuita de Atlassian para Windows y macOS, orientada a usuarios de Bitbucket y repositorios Git locales.  
- **Características clave:**  
  - Visualización de commits en un grafo interactivo.  
  - Herramientas de staging gráfico y terminal integrada.  
  - Soporte nativo para Mercurial, además de Git.  
- **Enlace:** <https://www.sourcetreeapp.com/>

### 🔹 Visual Studio Code (Control de versiones)

- **Descripción:** Editor de código ligero que incluye soporte integrado para Git, ampliable mediante extensiones.  
- **Características clave:**  
  - Panel de fuente (Source Control) con botones para `stage`, `commit`, `push` y `pull`.  
  - Vista de diferencias lado a lado y resaltado de cambios.  
  - Extensiones recomendadas:  
    - **GitLens:** análisis avanzado de historial de commits y autores.  
    - **Git Graph:** visualización de grafo de ramas y commits.  
- **Enlace:** <https://code.visualstudio.com/>  

Con estas herramientas, los usuarios pueden elegir la que mejor se adapte a su flujo de trabajo y entorno, manteniendo una experiencia gráfica que complementa las operaciones de Git en terminal.```


## ✅ Resultado esperado
