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
## 4.1 Comparación de revisiones

git diff <commit> <commit>

git difftool

## 4.2 Reescritura de historial

git commit --amend

git rebase -i para squash y reordenar

## 4.3 Reflog y recuperación

git reflog para encontrar HEAD antiguas

git cherry-pick para rescatar commits específicos

## 4.4 Branches ligeros vs. pesados

Impacto en el historial

## 4.5 Ejercicio

Simular una mala rebase y recuperarse con reflog

# 5. 🌿 Ramas y flujos de trabajo en equipo
## 5.1 Concepto de rama

Rama como puntero movible

## 5.2 Crear y cambiar ramas

git branch, git switch, git checkout -b

## 5.3 Fusionar ramas

git merge (fast-forward vs. no-ff)

Estructura de commits de merge

## 5.4 Flujos populares

GitHub Flow

Git Flow (feature/release/hotfix)

Trunk-based Development

## 5.5 Resolución de conflictos

Marcas en archivos

Herramientas de merge (VSCode, meld)

## 5.6 Ejercicio

Recrear un conflicto entre dos ramas y resolverlo manualmente

# 6. ☁️ Trabajo con repositorios remotos en GitHub
## 6.1 🔄 Conceptos Básicos
## ☁️ GitHub como servicio de hosting Git
## 🏗️ Crear un repositorio remoto en GitHub
## 6.2 ⚖️ Configuración Inicial de Remotos
## 6.3 🔑 URLs y Autenticación
## 6.4 ➡️ Enviar Cambios al Remoto (Push)
## 6.5 💾 Obtener Cambios del Remoto (Fetch & Pull)
## 6.6 🔹 Ramas de Seguimiento (Tracking Branches)
## 6.7 🌐 Gestión de múltiples remotos
## 6.8 📖 Clonación de Repositorios
## 6.9 🚚 Migrar un repositorio local a GitHub
## 6.10 🏢 Organizaciones, Equipos y Permisos en GitHub
## 6.11 🗃️ Monorepos y gestión de permisos avanzada
## 6.12 ⚙️ Automatización Local con Git
## 6.13 ⚠️ Manejo de Errores Comunes en Repos Remotos
## 6.14 💡 Buenas Prácticas Fundamentales con Repos Remotos
## 6.14 💡 Buenas Prácticas con Repos Remotos

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
