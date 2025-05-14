# 1. 📌 Introducción a Git y GitHub
## 1.1 Objetivos

Entender el propósito de un sistema de control de versiones.

Conocer la historia y evolución de Git y GitHub.

## 1.2 ¿Qué es Git?

Definición y características principales

Arquitectura distribuida vs. centralizada

## 1.3 ¿Qué es GitHub?

Plataforma colaborativa: repositorios remotos, social coding

Diferencias clave frente a Git local

## 1.4 Ventajas del control de versiones

Colaboración y trazabilidad

Historias de éxito (proyectos open-source, empresas)

## 1.5 Flujo de trabajo general

Local → Remoto → Colaborativo

Diagrama de alto nivel

## 1.6 Ejercicio

Investigar un proyecto open-source y describir su flujo de Git/GitHub.

## 1.7 Recursos

Enlace a la documentación oficial de Git y GitHub

# 2. ⚙️ Primeros pasos con Git
## 2.1 Instalación de Git

Windows (Git for Windows), macOS (Homebrew), Linux (apt/yum)

## 2.2 Configuración inicial

git config --global user.name / user.email

Archivo .gitconfig y secciones comunes

## 2.3 Alias y personalización

Crear alias (git config alias.co checkout)

Colores, prompts y hooks de cliente

## 2.4 .gitignore y .gitattributes

Sintaxis básica de .gitignore

Uso de .gitattributes para fin de línea y diffs personalizados

## 2.5 Primer repositorio

git init vs. git clone

Estructura del directorio .git/

## 2.6 Ejercicio

Configurar un alias y un .gitignore para un proyecto Python

## 2.7 Recursos

Cheatsheet de configuración de Git

# 3. 🧱 Flujo básico de trabajo con Git
## 3.1 Estado del repositorio

git status y sus interpretaciones

## 3.2 Agregar y confirmar cambios

git add (área de staging)

git commit -m vs. -v vs. --amend

## 3.3 Ver historial

git log (formatos, alias, --graph)

git show, git diff

## 3.4 Tags y versiones

git tag ligero vs. anotado

Uso en liberaciones (semver)

## 3.5 Recuperación rápida

git reset --soft/mixed/hard

git restore

## 3.6 Ejercicio

Crear varios commits y practicar reset y restore para deshacer

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
## 6.1 Crear un repo remoto

Opciones de visibilidad, README, plantilla de licencia

## 6.2 Conexión local-remoto

git remote add origin

git push -u origin main

## 6.3 Operaciones remotas

git fetch vs. git pull

git push (forzar, tags)

## 6.4 Autenticación

HTTPS con token personal

SSH (generar par de llaves, ssh-agent)

## 6.5 Sincronización de forks

upstream remoto, fetch + rebase

## 6.6 Ejercicio

Clonar un fork, sincronizar con el repo original

# 7. 🤝 Colaboración: Forks, Pull Requests y revisiones
## 7.1 Fork vs. clone

Flujo de contribución en proyectos open-source

## 7.2 Crear un Pull Request

Descripción clara, checklist, reviewers

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
