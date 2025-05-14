# ⚙️ 2. Primeros Pasos con Git
Git es un sistema de control de versiones que permite gestionar y rastrear cambios en archivos de código. Para comenzar, se instala Git, se configura el usuario con git config, y se inicia un repositorio con git init. Luego, se pueden agregar archivos con git add y guardar cambios usando git commit
## 🎯 Objetivo
El objetivo de Git es gestionar el control de versiones de un proyecto, facilitando la colaboración simultánea entre múltiples desarrolladores, quienes pueden realizar cambios y mejoras de forma estructurada y eficiente dentro de un repositorio compartido.
## 🧠 ¿Qué es Git?
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

### ✔️ Verificación de la instalación

Una vez finalizado el proceso de instalación, se recomienda verificar que Git esté correctamente instalado. Para ello, se debe ejecutar el siguiente comando en la terminal o línea de comandos:

```bash
git --version
```

Este comando debe mostrar la versión de Git instalada, lo cual confirma que la herramienta está lista para ser utilizada.

---


## ⚙️ Configuración inicial de Git

Antes de comenzar a trabajar con Git, es fundamental establecer la identidad del usuario para que cada confirmación (commit) quede correctamente registrada. Esta sección explica cómo configurar el nombre y el correo electrónico globales, así como verificar todos los ajustes disponibles.

### 🔹 Definir nombre de usuario

Se utiliza el siguiente comando para asociar su nombre al autor de los commits:

```bash
git config --global user.name "Tu Nombre Completo"
````

> **Nota:** Reemplace `"Tu Nombre Completo"` por el nombre que desea que aparezca en el historial de versiones.

### 🔹 Definir correo electrónico

Git requiere un correo electrónico válido para identificar al autor de cada cambio. Configurelo con:

```bash
git config --global user.email "tu.email@dominio.com"
```

> **Nota:** Utilice la dirección de correo institucional o personal que esté vinculada a su cuenta de GitHub o al servicio de repositorios que vaya a emplear.

### 🔹 Verificación de la configuración

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

### 🔹 Configuración adicional recomendada

Aunque es opcional, puede definir el editor predeterminado para mensajes de commit y mejorar la experiencia de uso:

### Establecer VS Code como editor predeterminado
```bash
git config --global core.editor "code --wait"
```

Con estos ajustes iniciales completados, Git estará listo para rastrear cambios bajo su identidad académica o profesional.

## 🖥️ Comandos básicos de la terminal

## 📁 Crear tu primer repositorio

## 🧬 Estructura interna del repositorio

## 🖼️ Opciones visuales (GUI)

## ✅ Resultado esperado
