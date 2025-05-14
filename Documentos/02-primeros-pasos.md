# 2. ⚙️ Primeros Pasos con Git
## 2.1 🎯 Objetivo:
Aprender a instalar y configurar Git en el sistema local, y familiarizarse con los primeros comandos esenciales para gestionar repositorios.

#### 🧠 Recordando que es Git!
Git es un sofware de control de versiones de una carpeta que nos permite tener diferentes versiones de una carpeta
#### 2.2 📝Ventajas de usar git

| Ventaja                          | Descripción                                                                                                |
| -------------------------------- | ---------------------------------------------------------------------------------------------------------- |
| Control de versiones distribuido | Cada colaborador tiene el repositorio completo, permitiendo trabajar sin conexión y mayor resiliencia.     |
| Ramificación ligera              | Creación y fusión de ramas de forma rápida y sencilla, favoreciendo flujos de trabajo basados en features. |
| Historial completo               | Registro detallado de cada cambio con autor, fecha y mensaje, facilitando auditoría y reversión.           |
| Rendimiento                      | Operaciones locales rápidas (commits, diffs, logs) sin depender de un servidor central.                    |
| Colaboración fluida              | Herramientas como pull requests y forks facilitan revisiones de código y contribuciones externas.          |
| Compatibilidad y extensibilidad  | Gran ecosistema de clientes GUI, hooks, servicios remotos (GitHub, GitLab, Bitbucket) y plugins.           |

---

## 2.3 💾 Instalación de Git

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

* **Descarga manual** desde el sitio oficial: [Descarga git en macOS](https://git-scm.com/download/mac)

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


## 2.4 ⚙️ Configuración inicial de Git

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
#### Establecer VS Code como editor predeterminado
Aunque es opcional, puede definir el editor predeterminado para mensajes de commit y mejorar la experiencia de uso:
```bash
git config --global core.editor "code --wait"
```
---
## 2.5 🖥️ Comandos básicos de la terminal de Git Bach
Aquí verás detalladamente los comandos basicos de la terminal
El resumen puedes encontrarlo [aqui](https://github.com/Bryared/Guia-completa-de-GitHub/blob/main/Resumenes/comandos-git-bach.md) <-

#### 1.🔹 Crear el directorio de trabajo
   * `mkdir MiProyecto` Crea un directorio de trabajo
   
   * `cd MiProyecto` Te posicionas en el directorio de trabajo

#### 2.🔹 Inicializar el repositorio

* **`git init`**
  Inicializa un nuevo repositorio Git en el directorio actual y crea la carpeta oculta `.git`:

  ```bash
  git init
  ```

  Tras este comando, el proyecto está bajo control de versiones, aunque aún no contiene historial de confirmaciones.
#### 3.🔹 Preparar (staging) archivos
   Añadir un archivo al área de preparación (staging area):
   
* **`.gitignore`**
   Evita que ciertos archivos o carpetas se suban al repositorio (si no han sido *trackeados* con `git add`).
   **¿Cómo usarlo?** Crea un archivo llamado `.gitignore` en la raíz del repo. Dentro, especifica qué ignorar:

   * `nombre.txt` → Ignora solo el archivo nombre.txt
   * `*.log` → Ignora todos los archivos `.log`
   * `carpeta/` → Ignora todo el contenido de la carpeta
   * `!importante.log` → **No ignora** este archivo (aunque coincida con otra regla)

   > El `.gitignore` **solo afecta archivos nuevos** (no ya versionados).
* **`git add`**
   ```bash
   git add "nombre_del_archivo"
   ```
   > También puedes añadir todos los archivos del repositorio con `git add .`
* **`git rm`**
   Y si es necesario revertir la adición al área de preparación:
   ```bash
   git rm --cached "nombre_del_archivo"
   ```
* **`git status`**
   Muestra en todo momento el estado del directorio de trabajo y del área de preparación.
  ```bash
   git status
   ```
  > Para un resumen compacto, se puede usar `git status -s`.
#### 4.🔹 Crear un commit (confirmación)
Un *commit* es como decir una “fotografía” del estado actual del proyecto: captura todos los cambios preparados hasta ese momento.
* **`git commit -m "Descripción del cambio" -a`**
  Crea un nuevo commit que incluye todos los archivos previamente añadidos al área de preparación
  ```bash
  git commit -m "Añadir README inicial"
  ```
  > Usa `git commit -m "Añadir README inicial -a` por si aun no se ha añadido el archivo con add
#### 5. 🔹 Explorar el historial
* **`git status`**
  Muestra qué archivos han cambiado, cuáles están listos para commit, y cuáles no:
  ```bash
  git status
  ```
* **`git log`**
  Lista la informacion y hash de todos los commits con detalle:
  ```bash
  git log
  ```
  > Para mostrar un resumen compacto de los commits usa `git log --oneline`
  
  > Para mostrar diferencias entre dos commits usa `git log <hash1> <hash2>`
* **Configuración opcional:**
 Para abreviar los hashes en los logs, se puede ajustar:
   > ```bash
   > git config --global core.abbrev "n"
   > ```
---

## 2.5 🖼️ Opciones visuales (GUI)

Para quienes prefieren interfaces gráficas en lugar de la línea de comandos, existen diversas aplicaciones que facilitan la gestión de repositorios Git. A continuación se presentan cuatro alternativas populares, junto con sus características principales y enlaces oficiales.

#### 🔹 GitHub Desktop

- **Descripción:** Cliente oficial de GitHub, diseñado para integrarse de forma nativa con repositorios alojados en GitHub y GitHub Enterprise.  
- **Características clave:**  
  - Sincronización automática con GitHub (push/pull).  
  - Gestión de ramas y resolución de conflictos mediante interfaz visual.  
  - Visualización clara de diferencias y estados de archivos.  
- **Enlace:** <https://desktop.github.com/>

#### 🔹 GitKraken

- **Descripción:** Cliente multiplataforma (Windows, macOS, Linux) con interfaz intuitiva basada en gráficos de árbol para visualizar el historial de commits y ramas.  
- **Características clave:**  
  - Editor integrado de merge y resolución de conflictos.  
  - Integración con múltiples servicios (GitHub, GitLab, Bitbucket).  
  - Soporte para flujos de trabajo con Git LFS y submódulos.  
- **Enlace:** <https://www.gitkraken.com/>
- 
#### 🔹 Visual Studio Code (Control de versiones)

- **Descripción:** Editor de código ligero que incluye soporte integrado para Git, ampliable mediante extensiones.  
- **Características clave:**  
  - Panel de fuente (Source Control) con botones para `stage`, `commit`, `push` y `pull`.  
  - Vista de diferencias lado a lado y resaltado de cambios.  
  - Extensiones recomendadas:  
    - **GitLens:** análisis avanzado de historial de commits y autores.  
    - **Git Graph:** visualización de grafo de ramas y commits.  
- **Enlace:** <https://code.visualstudio.com/>  

> Con estas herramientas, los usuarios pueden elegir la que mejor se adapte a su flujo de trabajo y entorno, manteniendo una experiencia gráfica que complementa las operaciones de Git en terminal.

## 2.6 📘 Actividad guiada sugerida para cerrar el módulo

> ### 🧪 Práctica: Crea tu primer repositorio

1. Crea una carpeta nueva:
   `mkdir mi-primer-repo && cd mi-primer-repo`
2. Inicializa Git:
   `git init`
3. Crea un archivo README.md y edítalo:
   `echo "# Mi Primer Repo" > README.md`
4. Añádelo al staging:
   `git add README.md`
5. Haz tu primer commit:
   `git commit -m "Primer commit"`
6. Verifica el historial:
   `git log --oneline`
7. Crea una rama:
   `git switch -c mi-rama`
8. Cambia algo en el README y haz un segundo commit.
9. Usa `git log --oneline` para ver el historial.
