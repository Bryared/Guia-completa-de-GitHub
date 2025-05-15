# 1. 📌 Introducción a Git y GitHub
## 1.1 🎯 Objetivos
## 1.2 🧠 ¿Qué es Git?
## 1.3 🌐 ¿Qué es GitHub?
## 1.4 🆚 Git vs. GitHub:
## 1.5 💡 Ventajas del control de versiones
## 1.6 🔄 Flujo de trabajo general
## 1.7 📝 Ejercicio
## 1.8 🔗 Recursos

# 2. ⚙️ Primeros Pasos con Git
## 2.1 🎯 Objetivo:
## 2.2 📝Ventajas de usar git
## 2.3 💾 Instalación de Git
## 2.4 ⚙️ Configuración inicial de Git
## 2.5 🖥️ Comandos básicos de la terminal de Git Bach
## 2.5 🖼️ Opciones visuales (GUI)
## 2.6 📘 Actividad guiada sugerida para cerrar el módulo

# 3. 🧱 Flujo básico de trabajo con Git
## 3.1 🔍 Estado del repositorio
## 3.2 🧾 Agregar y confirmar cambios
## 3.3 📜 Ver historial
## 3.4 🔖 Tags y versiones
## 3.5 🧯 Recuperación rápida
## 3.6 📝 Ejercicio

# 4. 🔁 Gestión de versiones y cambios
## 🎯 Objetivo
## 4.1 📊 Comparación de revisiones
## 4.2 ✍️ Reescritura del historial
## 4.3 🧭 Reflog y recuperación de commits
## 4.4 🧪 Ejercicio práctico

# 5. 🌿 Ramas y flujos de trabajo en equipo
## 5.1 🌿 ¿Qué es una rama en Git?
## 5.2🌿 Crear y gestionar ramas en Git
#### 📌 Crear una rama (`git branch`)
#### 🔍 Ver ramas activas (`git log --decorate`)
#### 🔄 Cambiar de rama con `git switch`
## 5.3 🌿 Procedimientos Básicos: Ramificar y Fusionar
#### 🔧 Flujo de trabajo típico
#### 🔀 Fusionar cambios
#### ⚠️ ¿Y si hay conflictos?
## 5.4 🧬 Rebase vs Merge
#### 🌀 `git rebase` (reescribe el historial):
#### Comparación:
## 5.5 🤝 Trabajo colaborativo en GitHub
#### Clonar un repositorio remoto
#### Crear tu propia rama de trabajo
#### Subir una rama a GitHub
#### Crear un Pull Request (PR)
#### Revisar y aceptar PRs
## 5.6 🧪 Ejercicio colaborativo simulado

# 6. ☁️ Trabajo con repositorios remotos en GitHub
## 6.1 🔄 Conceptos Básicos
#### ¿Qué es un repositorio remoto?
#### 🖥️ Repositorio Local vs Repositorio Remoto
#### ✅ Ventajas de Usar Repositorios Remotos
### ☁️ GitHub como servicio de hosting Git
### 🏗️ Crear un repositorio remoto en GitHub
#### 🖱️ Opción 1: Desde la Interfaz Web
#### 💻 Opción 2: Desde la Terminal con GitHub CLI
## 6.2 ⚖️ Configuración Inicial de Remotos
### 🔗 ¿Qué es un "remote"?
### 🔧 Comandos Clave para Gestionar Remotos
### 🔗 Vincular un repositorio local a uno remoto (GitHub)
#### 📁 Caso: Ya tienes un proyecto local iniciado con Git
#### 📤 Subir tu proyecto por primera vez
#### 🔁 Cambiar la URL del remoto
#### ❌ Eliminar el remoto
## 6.3 🔑 URLs y Autenticación
### 🔗 ¿Por qué necesitas autenticarte?
### 🔀 Formas de conexión con GitHub
### 🔒 HTTPS con Tokens de Acceso Personal (PAT)
#### 🛠️ Cómo generar un PAT:
### 🔐 SSH: Claves Públicas y Privadas
#### 🧰 Pasos para usar SSH:
### 🖥️ Almacenamiento de Credenciales
### ⚡ Alternativa rápida: GitHub CLI
## 6.4 ➡️ Enviar Cambios al Remoto (Push)
### 🔁 ¿Qué significa hacer `push`?
### 📤 Primer Push (inicial)
### 🔁 Comandos de push frecuentes
### 👁️ Ver estado de ramas y seguimiento
### ⬆️ Subir cambios al repositorio remoto
## 6.5 💾 Obtener Cambios del Remoto (Fetch & Pull)
### 🔄 ¿Por qué es importante traer cambios?
### 🧩 Diferencias entre `fetch` y `pull`
### 📥 Comandos esenciales
### 🧨 Posibles conflictos al hacer `pull`
### 🛠️ Herramientas para resolución de conflictos
## 6.6 🔹 Ramas de Seguimiento (Tracking Branches)
### 🔍 ¿Qué es una *tracking branch*?
### 🧠 ¿Cuándo se configura automáticamente una *tracking branch*?
### 🛠️ Comandos útiles
### 📘 Ejemplo completo
### 🔄 Cambiar el seguimiento de una rama existente
## 6.7 🌐 Gestión de múltiples remotos
### 📌 ¿Qué es tener múltiples remotos?
### 🔧 Comandos clave para gestionar remotos adicionales
#### ➕ Añadir un segundo remoto
#### 🔁 Verificar todos los remotos configurados
#### ✏️ Renombrar un remoto existente
#### ❌ Eliminar un remoto
### 🔄 Sincronizar cambios desde otro remoto
### ✅ Mini resumen visual
## 6.8 📖 Clonación de Repositorios
### 🔍 ¿Qué hace `git clone`?
### 🔄 Variantes útiles de clonación
#### 🔸 Clonar una rama específica
#### 🔹 Clonación superficial (shallow clone)
#### 🔍 Clonar sin historial completo + solo una rama:
### 📁 Sparse Checkout: Clonar solo partes del proyecto
## 6.9 🚚 Migrar un repositorio local a GitHub
### 🎯 Objetivo
### 🧱 Caso básico: subir un proyecto local a GitHub
### 🪞 Caso avanzado: migrar un repositorio como espejo
## 6.10 🏢 Organizaciones, Equipos y Permisos en GitHub
### 👥 ¿Qué es una organización en GitHub?
### 🛡️ Gestión de equipos y roles
### 🔐 Permisos avanzados
## 6.11 🗃️ Monorepos y gestión de permisos avanzada
### 🧩 ¿Qué es un monorepo?
### ✅ Ventajas:
### ⚠️ Desafíos:
### 🔐 Permisos por carpeta (con GitHub Teams)
## 6.12 ⚙️ Automatización Local con Git
### 🔁 Git Hooks
### 🧪 Ejemplo: Validar antes de hacer push
### 🕒 Sincronización automática con `cron`
### 🔄 Comparación con GitHub Actions
## 6.13 ⚠️ Manejo de Errores Comunes en Repos Remotos
### 🚫 Permisos denegados (`403`, `401`)
### 🔀 Historia divergente
### 📭 Repositorio no encontrado
### 🧹 Limpiar referencias obsoletas
## 6.14 💡 Buenas Prácticas Fundamentales con Repos Remotos
### 📌 Organización y nombres
### 🔁 Flujo de trabajo profesional
### 🔐 Seguridad básica
### 🛠 Diagnóstico mínimo
### 6.15 🧪 Actividad
#### ✅ Pasos:
### 6.16 📚 Recursos recomendados

# 7. 🤝 Colaboración: Forks, Pull Requests y revisiones
## 7.1 Fork vs. clone
## 7.2 Crear un Pull Request
## 7.3 Review de código

Comentarios en línea, sugerencias, aprobaciones

## 7.4 Etiquetas de estado

WIP, ready for review, approved

## 7.5 Merge y squash

Diferentes estrategias (merge commit, squash, rebase)

## 7.6 Ejercicio

Contribuir a un repositorio de ejemplo mediante fork + PR

# 8. 🐞 Gestión de tareas e incidencias con GitHub Issues
## 8.1 Qué son los Issues

Tracking de bugs, tareas y discusiones

## 8.2 Crear y gestionar Issues

Etiquetas, asignaciones, milestones

## 8.3 Plantillas de Issues

.github/ISSUE_TEMPLATE/bug_report.md

## 8.4 Automatización con keywords

Closes #, Fixes # en commits o PRs

## 8.5 Ejercicio

Diseñar una plantilla de Issue para tu proyecto

# 9. 📊 Gestión de proyectos con GitHub Projects
## 9.1 Introducción a Projects

Vista Kanban vs. tabla vs. roadmap

## 9.2 Crear tableros y columnas

To Do, In Progress, Done

## 9.3 Reglas de automatización

Mover tarjetas según estado de Issues/PRs

## 9.4 Vistas avanzadas

Custom queries y campos

## 9.5 Ejercicio

Crear un proyecto para planificar todo el manual

# 10. ⚙️ Automatización con GitHub Actions
## 10.1 ¿Qué son las Actions?

Runners, workflows y jobs

## 10.2 Anatomía de un workflow

on:, jobs:, steps:

## 10.3 Ejemplo CI básico

Lint de Markdown, tests de Python

## 10.4 Deploy a Pages

actions/deploy-pages@v3

## 10.5 Secrets y entornos

Configurar variables seguras

## 10.6 Ejercicio

Crear un workflow que valide y despliegue tus docs/

# 11. 📄 Compartir código con GitHub Gists
## 11.1 ¿Qué es un Gist?

Snippets públicos vs. secretos

## 11.2 Crear y versionar Gists

Usar la API de Gist

## 11.3 Integración en blogs y foros

Embebidos en Markdown

## 11.4 Ejercicio

Publicar un snippet de tus alias Git como Gist

# 12. 🌐 Publicación de sitios web con GitHub Pages
## 12.1 Modelos de Pages

Proyecto estático vs. Jekyll/MkDocs

## 12.2 Configuración de Pages

Carpeta /docs o rama gh-pages

## 12.3 Temas y personalización

Variables de configuración _config.yml

## 12.4 Dominio personalizado y HTTPS

## 12.5 Ejercicio

Publicar tu manual como sitio web y compartir el link

# 13. 💻 Entornos de desarrollo en la nube
## 13.1 GitHub Codespaces

Crear un Codespace, devcontainer.json

## 13.2 GitHub.dev

Edición ligera en navegador

## 13.3 Comparativa local vs. cloud

## 13.4 Ejercicio

Abrir tu repo en GitHub.dev y modificar un capítulo

# 14. 🛡️ Buenas prácticas, seguridad y herramientas avanzadas
## 14.1 Buenas prácticas de commits

Mensajes claros, convenciones (Conventional Commits)

## 14.2 Protección de ramas

Revisiones obligatorias, status checks

## 14.3 CODEOWNERS y políticas

## 14.4 Escaneo de vulnerabilidades

Dependabot, CodeQL

## 14.5 Herramientas GUI y CLI avanzadas

gh CLI, Sourcetree, GitKraken

## 14.6 Ejercicio

Configurar una regla de protección de ramas y un workflow de CodeQL
