# 8. 🐞 Gestión de tareas e incidencias con GitHub Issues

GitHub Issues permite rastrear bugs, planificar tareas, recopilar ideas y mantener discusiones organizadas dentro de los proyectos.

---

### 8.1 📝 Crear, asignar y etiquetar Issues

#### Crear un Issue

Desde la pestaña **"Issues"** → **New Issue**

Un issue suele incluir:

* Título claro y descriptivo
* Descripción del problema o solicitud
* Pasos para reproducir (si es bug)
* Comportamiento esperado

#### Asignar responsables

Puedes asignar un **responsable** del issue desde la columna derecha del issue.

#### Etiquetas (labels)

Las etiquetas ayudan a clasificar los issues. Ejemplos:

* `bug`
* `enhancement`
* `question`
* `documentation`
* `help wanted`

> Puedes crear etiquetas personalizadas con colores distintivos.

---

### 8.2 📆 Milestones y vinculación con Pull Requests

#### Milestones

Permiten agrupar issues y PRs bajo un objetivo común, como una versión de lanzamiento.

```text
Ejemplo: Milestone “v1.0” incluye 10 issues
```

#### Vincular PR a un Issue

Puedes vincular un PR directamente usando:

```markdown
Fixes #123
Closes #456
```

> Esto cierra automáticamente el Issue al fusionar el PR.

---

### 8.3 🧩 Templates de Issue

Puedes definir plantillas para estructurar la creación de issues y mejorar la calidad de los reportes.

📁 `.github/ISSUE_TEMPLATE/bug_report.md`

```markdown
## Descripción del error
...

## Pasos para reproducir
1.
2.
3.

## Comportamiento esperado
...

## Capturas de pantalla
(Si aplica)
```

#### Tipos comunes de templates:

* Bug report
* Feature request
* Documentation issue

---

### 8.4 💬 GitHub Discussions vs Wiki

#### GitHub Discussions

* Ideal para **preguntas abiertas**, ideas y debates.
* Soporta respuestas votadas y categorización.
* Fomenta comunidad.

#### Wiki

* Documentación estructurada.
* Soporte para páginas enlazadas y navegación por árbol.

> Ideal para manuales técnicos, guías de usuario, etc.

---

### 8.5 ⚙️ Automatización con Issues

#### Cerrar issues automáticamente desde PRs

Usa palabras clave como:

* `Fixes #12`
* `Resolves #45`
* `Closes #78`

> El Issue se cierra cuando el PR se fusiona en la rama principal.

---

### 🧠 Buenas prácticas

* Escribir títulos claros y concisos.
* Usar checklists para tareas múltiples.
* Comentar progreso en el mismo issue.
* Etiquetar y asignar para mantener orden.

---
