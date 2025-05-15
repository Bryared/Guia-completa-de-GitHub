# 15. 🚀 Estrategias de Flujo de Trabajo en Proyectos GitHub

> *“Todo conocimiento sin aplicación se evapora. Aquí es donde lo haces funcionar.”*

Este apartado te muestra cómo aplicar, organizar y optimizar todo lo aprendido para trabajar en proyectos reales con Git y GitHub, en equipo o de forma individual. Aquí se presentan los principales **flujos de trabajo (workflows)** utilizados por desarrolladores y organizaciones profesionales.

### 🧭 ¿Qué es un flujo de trabajo?

Un **flujo de trabajo (workflow)** en Git/GitHub define **cómo se colabora, ramifica, revisa y despliega** el código. Implica:

* Cómo y cuándo se crean ramas.
* Qué reglas se siguen para hacer commits y PRs.
* Qué rama representa la versión “estable” del proyecto.
* Cuándo se hace `merge` o `release`.

> 💡 El objetivo es asegurar que el código sea colaborativo, mantenible y entregable de forma predecible.

---

### 🧱 Componentes de un flujo de trabajo

* **Ramas (`branches`)**: Dividen tareas, nuevas features, arreglos.
* **Commits**: Cambios versionados con mensajes significativos.
* **Pull Requests**: Solicitudes de integración, con revisión y discusión.
* **Revisiones**: Control de calidad antes de fusionar.
* **Integración continua (CI)**: Automatiza pruebas y builds.
* **Deploy (CD)**: Entrega automática al entorno final.

---

## 15.1 🔁 GitHub Flow (el más simple y efectivo,  ideal para proyectos web)

Ideal para proyectos pequeños o medianos, y especialmente para **desarrollo continuo**.

### 🧭 Flujo:

1. Crea una rama (`feature-login`)
2. Haz tus cambios y **commits**
3. Sube la rama (`git push origin feature-login`)
4. Abre un **Pull Request**
5. Recibe revisiones o aprueba directamente
6. Haz **merge** a `main`
7. Se despliega automáticamente (opcional con GitHub Actions)

✅ Recomendado para: sitios web, apps modernas, desarrollo ágil.
❌ No ideal para software que requiere versiones estables o múltiples entornos.

---

## 15.2 🌿 Git Flow (estructurado y robusto, ideal para software en producción)

Ideal para proyectos grandes con múltiples versiones en paralelo.

### 🔱 Estructura de ramas:

* `main`: producción estable
* `develop`: versión de desarrollo (pre-producción)
* `feature/*`: nuevas funcionalidades
* `release/*`: preparación para lanzamientos
* `hotfix/*`: arreglos críticos de producción

### 🧭 Flujo:

1. Se parte de `develop` para crear ramas `feature/`
2. Al completar una función → merge a `develop`
3. Cuando se prepara un lanzamiento → `release/` → merge a `main` y `develop`
4. Si hay bugs críticos → `hotfix/` → merge a `main` y `develop`

✅ Recomendado para: software empresarial, sistemas complejos, apps con roadmap definido.
❌ Puede ser complejo de manejar sin automatización.

---

## 15.3 🤝 Trunk-Based Development

Desarrollo basado en una sola rama principal (`main` o `trunk`) con ramas de vida muy corta.

### 🧭 Flujo:

1. Se trabaja directo sobre `main` o ramas muy pequeñas (`<1 día`)
2. Integración y despliegue continuo
3. Tests automáticos para asegurar estabilidad

✅ Recomendado para: equipos DevOps, CI/CD intenso, entornos ágiles.
❌ Requiere testeo y CI/CD impecable.

---

## 15.4 🔀 Forking Workflow

Usado cuando no todos los colaboradores tienen acceso directo al repositorio (open source, proyectos públicos).

### 🧭 Flujo:

1. Cada contribuyente hace un **fork** del repositorio
2. Crea ramas de trabajo en su fork
3. Abre un **Pull Request** hacia el repositorio original
4. Revisión y aprobación por los mantenedores

✅ Recomendado para: proyectos open source, repos públicos, colaboración externa.

---

## 15.5 🧱 GitHub Projects + Issues + PRs

Cómo estructurar el trabajo usando las herramientas de GitHub de forma integrada.

### 🔹 Organización visual:

* Usa **GitHub Projects** (tipo Kanban o Tabla)
* Cada **Issue** representa una tarea
* Cada **Pull Request** referencia uno o más issues
* Automatiza columnas: PR abierto → In Progress, cerrado → Done

### 🔹 Ejemplo real:

* Crear un issue: *"Agregar autenticación con Google"*
* Asignar a desarrollador, milestone y etiqueta
* Crea una rama `feature/google-auth`
* Al terminar, abre PR: *Fixes #23*
* Al hacer merge, el issue se cierra automáticamente

---

## 15.6 🧠 Recomendaciones Finales para elegir el mejor flujo

| Tipo de Proyecto               | Mejor flujo sugerido           |
| ------------------------------ | ------------------------------ |
| Sitio web personal             | GitHub Flow                    |
| App empresarial compleja       | Git Flow                       |
| Proyecto open source           | Forking Workflow               |
| Startup con CI/CD ágil         | Trunk-Based Development        |
| Equipo híbrido (junior/senior) | Git Flow + Projects integrados |

---

## 15.7 🛠️ Herramientas para potenciar tus flujos

* **GitHub CLI**: para automatizar ramas, PRs, releases
* **GitHub Actions**: para CI/CD según eventos del flujo
* **GitHub Projects**: gestión visual del equipo
* **GraphQL o REST API**: monitoreo y personalización
* **Slack, Jira, Notion**: integraciones para mejorar la coordinación

---

## 🎯 Tu Misión Final

Pon en práctica uno de estos flujos:

1. Crea un nuevo repositorio real (puede ser un portafolio, app, API, etc.)
2. Elige un flujo de trabajo (GitHub Flow si estás empezando)
3. Automatiza deploy con GitHub Actions
4. Gestiona tus tareas con Issues + GitHub Projects
5. Invita a alguien a colaborar vía Pull Request

---

> **“El flujo perfecto no es el más complejo, sino el que mejor se adapta a tu equipo.”**

---
