---
# 1. 📌 Introducción a Git y GitHub
### 1.1 🎯 Objetivos
### 1.2 🧠 ¿Qué es Git?
### 1.3 🌐 ¿Qué es GitHub?
### 1.4 🆚 Git vs. GitHub:
### 1.5 💡 Ventajas del control de versiones
### 1.6 🔄 Flujo de trabajo general
### 1.7 📝 Ejercicio
### 1.8 🔗 Recursos
---
# 2. ⚙️ Primeros Pasos con Git
### 2.1 🎯 Objetivo:
### 2.2 📝Ventajas de usar git
### 2.3 💾 Instalación de Git
### 2.4 ⚙️ Configuración inicial de Git
### 2.5 🖥️ Comandos básicos de la terminal de Git Bach
### 2.5 🖼️ Opciones visuales (GUI)
### 2.6 📘 Actividad guiada sugerida para cerrar el módulo
---
# 3. 🧱 Flujo básico de trabajo con Git
### 3.1 🔍 Estado del repositorio
### 3.2 🧾 Agregar y confirmar cambios
### 3.3 📜 Ver historial
### 3.4 🔖 Tags y versiones
### 3.5 🧯 Recuperación rápida
### 3.6 📝 Ejercicio
---
# 4. 🔁 Gestión de versiones y cambios
### 🎯 Objetivo
### 4.1 📊 Comparación de revisiones
### 4.2 ✍️ Reescritura del historial
### 4.3 🧭 Reflog y recuperación de commits
### 4.4 🧪 Ejercicio práctico
---
# 5. 🌿 Ramas y flujos de trabajo en equipo
### 5.1 🌿 ¿Qué es una rama en Git?
### 5.2🌿 Crear y gestionar ramas en Git
#### 📌 Crear una rama (`git branch`)
##### 🔍 Ver ramas activas (`git log --decorate`)
##### 🔄 Cambiar de rama con `git switch`
### 5.3 🌿 Procedimientos Básicos: Ramificar y Fusionar
##### 🔧 Flujo de trabajo típico
##### 🔀 Fusionar cambios
##### ⚠️ ¿Y si hay conflictos?
### 5.4 🧬 Rebase vs Merge
##### 🌀 `git rebase` (reescribe el historial):
##### Comparación:
### 5.5 🤝 Trabajo colaborativo en GitHub
##### Clonar un repositorio remoto
##### Crear tu propia rama de trabajo
##### Subir una rama a GitHub
##### Crear un Pull Request (PR)
##### Revisar y aceptar PRs
### 5.6 🧪 Ejercicio colaborativo simulado
---
# 6. ☁️ Trabajo con repositorios remotos en GitHub
### 6.1 🔄 Conceptos Básicos
##### ¿Qué es un repositorio remoto?
##### 🖥️ Repositorio Local vs Repositorio Remoto
##### ✅ Ventajas de Usar Repositorios Remotos
#### ☁️ GitHub como servicio de hosting Git
#### 🏗️ Crear un repositorio remoto en GitHub
##### 🖱️ Opción 1: Desde la Interfaz Web
##### 💻 Opción 2: Desde la Terminal con GitHub CLI
### 6.2 ⚖️ Configuración Inicial de Remotos
#### 🔗 ¿Qué es un "remote"?
#### 🔧 Comandos Clave para Gestionar Remotos
#### 🔗 Vincular un repositorio local a uno remoto (GitHub)
#### 📁 Caso: Ya tienes un proyecto local iniciado con Git
#### 📤 Subir tu proyecto por primera vez
#### 🔁 Cambiar la URL del remoto
#### ❌ Eliminar el remoto
### 6.3 🔑 URLs y Autenticación
#### 🔗 ¿Por qué necesitas autenticarte?
#### 🔀 Formas de conexión con GitHub
#### 🔒 HTTPS con Tokens de Acceso Personal (PAT)
#### 🛠️ Cómo generar un PAT:
#### 🔐 SSH: Claves Públicas y Privadas
#### 🧰 Pasos para usar SSH:
#### 🖥️ Almacenamiento de Credenciales
#### ⚡ Alternativa rápida: GitHub CLI
### 6.4 ➡️ Enviar Cambios al Remoto (Push)
#### 🔁 ¿Qué significa hacer `push`?
#### 📤 Primer Push (inicial)
#### 🔁 Comandos de push frecuentes
#### 👁️ Ver estado de ramas y seguimiento
#### ⬆️ Subir cambios al repositorio remoto
### 6.5 💾 Obtener Cambios del Remoto (Fetch & Pull)
#### 🔄 ¿Por qué es importante traer cambios?
#### 🧩 Diferencias entre `fetch` y `pull`
#### 📥 Comandos esenciales
#### 🧨 Posibles conflictos al hacer `pull`
#### 🛠️ Herramientas para resolución de conflictos
### 6.6 🔹 Ramas de Seguimiento (Tracking Branches)
#### 🔍 ¿Qué es una *tracking branch*?
#### 🧠 ¿Cuándo se configura automáticamente una *tracking branch*?
#### 🛠️ Comandos útiles
#### 📘 Ejemplo completo
#### 🔄 Cambiar el seguimiento de una rama existente
### 6.7 🌐 Gestión de múltiples remotos
#### 📌 ¿Qué es tener múltiples remotos?
#### 🔧 Comandos clave para gestionar remotos adicionales
#### ➕ Añadir un segundo remoto
#### 🔁 Verificar todos los remotos configurados
#### ✏️ Renombrar un remoto existente
#### ❌ Eliminar un remoto
#### 🔄 Sincronizar cambios desde otro remoto
#### ✅ Mini resumen visual
### 6.8 📖 Clonación de Repositorios
#### 🔍 ¿Qué hace `git clone`?
#### 🔄 Variantes útiles de clonación
#### 🔸 Clonar una rama específica
#### 🔹 Clonación superficial (shallow clone)
#### 🔍 Clonar sin historial completo + solo una rama:
#### 📁 Sparse Checkout: Clonar solo partes del proyecto
### 6.9 🚚 Migrar un repositorio local a GitHub
#### 🎯 Objetivo
#### 🧱 Caso básico: subir un proyecto local a GitHub
#### 🪞 Caso avanzado: migrar un repositorio como espejo
### 6.10 🏢 Organizaciones, Equipos y Permisos en GitHub
#### 👥 ¿Qué es una organización en GitHub?
#### 🛡️ Gestión de equipos y roles
#### 🔐 Permisos avanzados
### 6.11 🗃️ Monorepos y gestión de permisos avanzada
#### 🧩 ¿Qué es un monorepo?
#### ✅ Ventajas:
#### ⚠️ Desafíos:
#### 🔐 Permisos por carpeta (con GitHub Teams)
### 6.12 ⚙️ Automatización Local con Git
#### 🔁 Git Hooks
#### 🧪 Ejemplo: Validar antes de hacer push
#### 🕒 Sincronización automática con `cron`
#### 🔄 Comparación con GitHub Actions
### 6.13 ⚠️ Manejo de Errores Comunes en Repos Remotos
#### 🚫 Permisos denegados (`403`, `401`)
#### 🔀 Historia divergente
#### 📭 Repositorio no encontrado
#### 🧹 Limpiar referencias obsoletas
### 6.14 💡 Buenas Prácticas Fundamentales con Repos Remotos
#### 📌 Organización y nombres
#### 🔁 Flujo de trabajo profesional
#### 🔐 Seguridad básica
#### 🛠 Diagnóstico mínimo
### 6.15 🧪 Actividad
#### ✅ Pasos:
### 6.16 📚 Recursos recomendados

---
# 7. 🤝 Colaboración: Forks, Pull Requests y revisiones
### 7.1 🍴 Fork vs. Clone
### 7.2 📤 Crear un Pull Request (PR)
#### 🔹 ¿Cuándo usar un PR?
#### 🔹 Pasos para crear un Pull Request
### 7.3 🧪 Revisar y fusionar PRs
### 7.4 ✍️ Pull Request Drafts
### 7.5 📄 Plantillas de Pull Request
### 7.6 🧑‍💻 GitHub CLI para PRs
#### Instalar GitHub CLI:
#### Comandos útiles:
### 7.7 🧠 Buenas prácticas de colaboración

# 8. 🐞 Gestión de tareas e incidencias con GitHub Issues
### 8.1 🎯 Objetivo
### 8.2 ❓ ¿Qué es un Issue?
### 8.3 ✍️ Crear y configurar un Issue
##### 1. 🔹 Ir a la sección Issues  
##### 2. 🔹 Escribir título y descripción  
##### 3. 🔹 Añadir etiquetas (Labels)  
##### 4. 🔹 Asignar responsables (Assignees)  
##### 5. 🔹 Vincular a un hito (Milestone)  
##### 6. 🔹 Agregar al tablero de proyecto (Projects)  
### 8.4 📆 Milestones y vinculación con Pull Requests
#### Milestones
#### Vincular PR a un Issue
### 8.5 🧩 Templates de Issue
#### Tipos comunes de templates:
### 8.6 💬 GitHub Discussions vs Wiki
#### GitHub Discussions
#### Wiki
### 8.7 ⚙️ Automatización con Issues
#### Cerrar issues automáticamente desde PRs
### 8.8 🧠 Buenas prácticas

---
# 9. 📊 Gestión de proyectos con GitHub Projects
## 9.1 🗂️ Tipos de Projects: Classic vs. Beta (Projects v2)
## 9.2 📌 Crear un nuevo Project en GitHub
#### 1. Acceder a la sección de Projects
#### 2. Iniciar la creación de un nuevo proyecto
#### 3. Elegir una plantilla o empezar desde cero
#### 4. Configurar los detalles del proyecto
#### 5. Crear el proyecto
## 9.3 📥 Añadir Issues y Pull Requests a un Project
## 9.4 🔄 Automatizaciones
#### En Projects Classic
#### En Projects Beta
## 9.5 📈 Métricas e Insights del repositorio
#### En la pestaña **Insights**:
## 9.6 💡 Buenas prácticas para equipos
## 🧠 Tips adicionales
---
# 10. ⚙️ Automatización con GitHub Actions
### 10.1 🧬 Estructura básica de un workflow
### 10.2 🚀 Eventos de disparo (`on:`)
### 10.3 🛠️ Jobs y pasos (`jobs` y `steps`)
### 10.4 🔁 Reutilización con Workflows Reusables
### 10.5 🏪 GitHub Actions Marketplace
### 10.6 🔐 Secretos y seguridad
### 10.7 📦 Ejemplos de automatización
#### ✅ Integración continua (CI)
#### 🌐 Despliegue automático a GitHub Pages
#### 📢 Notificaciones a Slack/Discord
### 🧠 Buenas prácticas

# 11. 📄 Compartir código con GitHub Gists
### 11.1 🧩 ¿Qué es un Gist?
### 11.2 🌐 Tipos de Gists
### 11.3 🛠️ Crear un Gist
#### 1. 🖥️ Crear un Gist desde la web
### 11.4 🌀 Versionado y Forks
### 11.5 💻 Usar Gists desde la terminal
### 11.6 🧪 Usar la GitHub CLI con Gists
### 11.7 🧠 Casos de uso recomendados
### 11.8 ✅ Buenas prácticas

# 12. 🌐 Publicación de sitios web con GitHub Pages
### 12.1 🧭 ¿Qué es GitHub Pages?
### 12.2 🏗️ Métodos de despliegue
### 12.3 🧪 Crear un sitio básico con HTML
### 12.4 💎 Uso de generadores estáticos
#### 🧱 Jekyll (por defecto en GitHub Pages)
#### ⚡ Otros generadores (Hugo, Docusaurus, Astro...)
### 12.5 🛠️ Configurar un dominio personalizado
### 12.6 🔐 HTTPS y seguridad
### 12.7 🧩 Automatización con GitHub Actions
### 12.8 📌 Buenas prácticas
### 12.9 🧠 Recursos adicionales

# 13. 💻 Entornos de desarrollo en la nube
### 13.1 ☁️ ¿Qué es un entorno de desarrollo en la nube?
### 13.2 🧪 GitHub.dev (editor en el navegador)
### 13.3 🚀 GitHub Codespaces (entorno completo en la nube)
#### ✅ Características
### 🧠 ¿Cuándo usar Codespaces?
### 🛠️ ¿Cómo crear un Codespace?
#### 1. Ve al repositorio deseado en GitHub
#### 2. Haz clic en el botón **Code**
#### 3. Selecciona la pestaña **Codespaces**
#### 4. Haz clic en **Create codespace on [rama]**
#### 5. Espera a que el entorno se configure automáticamente
### 13.4 🧩 Configurar con `devcontainer.json`
### 13.5 🧠 Casos de uso recomendados
### 13.6 📊 Limitaciones y consideraciones
### 13.7 🛡️ Seguridad y privacidad
### 13.8 🧪 Consejos avanzados

# 14. 🔧 Herramientas Avanzadas y Extensibilidad en GitHub
## 14.1 🧰 GitHub CLI (`gh`): Potencia GitHub desde tu terminal
### 🔹 ¿Qué puedes hacer con `gh`?
### 🔹 Ejemplo básico
## 14.2 🔌 GitHub REST API y GraphQL API
### 🔹 REST API
### 🔹 GraphQL API
### 🧪 Ejemplo de llamada REST usando `curl`
## 14.3 🧩 GitHub Apps y OAuth Apps
### 🔹 GitHub Apps
### 🔹 OAuth Apps
## 14.4 🌐 Webhooks
### 🔹 Casos de uso:
### 🔹 Ejemplo:
## 14.5 🛒 GitHub Marketplace
### 🔹 Tipos de herramientas disponibles:
## 14.6 ♻️ GitHub Actions: Reusable Workflows
### 🔹 ¿Para qué sirve?
### 🔹 Estructura básica
## 14.7 🔗 Integración con herramientas externas (Slack, Jira, etc.)
### 🔹 Ejemplos comunes:
## 14.8 🧠 Scripts avanzados: combinando Actions + API

# 15. 🚀 Estrategias de Flujo de Trabajo en Proyectos GitHub
## 15.1 🔁 GitHub Flow (el más simple y efectivo)
### 🧭 Flujo:
## 15.2 🌿 Git Flow (estructurado y robusto)
### 🔱 Estructura de ramas:
### 🧭 Flujo:
## 15.3 🤝 Trunk-Based Development
### 🧭 Flujo:
## 15.4 🔀 Forking Workflow
### 🧭 Flujo:
## 15.5 🧱 GitHub Projects + Issues + PRs
### 🔹 Organización visual:
### 🔹 Ejemplo real:
## 15.6 🧠 Recomendaciones Finales para elegir el mejor flujo
## 15.7 🛠️ Herramientas para potenciar tus flujos
## 🎯 Tu Misión Final

# 14. 🛡️ Buenas prácticas, seguridad y herramientas avanzadas
### 14.1 🧱 Buenas prácticas de repositorio
#### Archivos esenciales
#### Estructura ordenada
### 14.2 🔒 Seguridad y protección
#### Protecciones en ramas (`Branch Protection Rules`)
#### Dependabot
#### Code Scanning
#### Secret Scanning
### 14.3 ⚙️ Automatización con GitHub CLI y API
#### GitHub CLI (`gh`)
#### GitHub API
### 14.4 🧰 GitHub Marketplace y herramientas externas
### 14.5 🛡️ CODEOWNERS  
### 14.6 📝 Plantillas de Issues y Pull Requests  
### 14.7 ✅ Checks y políticas de merge  
### 14.8 🔍 Auditoría y registros de actividad  
### 14.9 📦 Releases y versionado  
### 14.10 🗂️ Limpieza y archivado de repositorios  
### 14.11 🧠 Consejos finales para equipos
