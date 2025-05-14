# 8. 🐞 Gestión de tareas e incidencias con GitHub Issues

GitHub Issues permite rastrear bugs, planificar tareas, recopilar ideas y mantener discusiones organizadas dentro de los proyectos.

---
### 8.1 🎯 Objetivo

En esta sección aprenderás a utilizar **GitHub Issues** para organizar tareas, reportar errores y colaborar eficientemente dentro de un repositorio.

> 📌 **GitHub Issues** es una herramienta de seguimiento integrada que permite:
> - Registrar bugs, tareas y mejoras.
> - Asignar responsabilidades.
> - Priorizar y etiquetar incidencias.
> - Automatizar flujos de trabajo conectados con commits y Pull Requests.
---
### 8.2 ❓ ¿Qué es un Issue?

Un **Issue** en GitHub es una entrada que permite comunicar tareas, errores, ideas o solicitudes dentro de un proyecto.

> 📌 Se usan como sistema de seguimiento (issue tracking) para llevar control del trabajo pendiente o en discusión.

Cada Issue puede incluir:
- ✅ Título y descripción detallada.
- 🏷️ Etiquetas (labels) para categorizar (bug, feature, help wanted…).
- 👥 Asignaciones (assignees) para responsables.
- 📅 Fechas límite (milestones) o versiones objetivo.
- 💬 Comentarios para discutir soluciones o avances.
- 🔗 Referencias automáticas desde commits o Pull Requests (`Fixes #123`).

> 💡 Ideal para trabajar de forma colaborativa y transparente en proyectos de cualquier tamaño.

- Definición y casos de uso.
- Diferencias con Pull Requests.
---

### 8.3 ✍️ Crear y configurar un Issue

Aquí aprenderás a crear un Issue correctamente y a configurarlo para que sea claro y fácil de gestionar.

##### 1. 🔹 Ir a la sección Issues  
- En tu repositorio de GitHub, haz clic en la pestaña **Issues**.
- ![image](https://github.com/user-attachments/assets/295ac87c-f655-4b4e-a2b6-d477a7285963)

- Pulsar el botón **New issue**.
- ![image](https://github.com/user-attachments/assets/f066eb9b-76fd-4152-a293-f891328f8fd1)



##### 2. 🔹 Escribir título y descripción  
1. **Título**: breve y descriptivo.

2. **Descripción**: detalla  
   - Qué ocurre y qué debería ocurrir.  
   - Pasos para reproducir (si es un bug).  
   - Capturas de pantalla o enlaces relevantes.
   - ![image](https://github.com/user-attachments/assets/18ca05b0-6969-4799-8c48-7a32794f4ab9)



##### 3. 🔹 Añadir etiquetas (Labels)  
- Selecciona etiquetas predefinidas (`bug`, `enhancement`, `question`, etc.).  
- O crea etiquetas personalizadas si tienes permisos.
- ![image](https://github.com/user-attachments/assets/f9dc9f9b-f751-47ad-bcbb-4eaee902919e)


##### 4. 🔹 Asignar responsables (Assignees)  
- Elige uno o varios colaboradores encargados de resolver el Issue.
- ![image](https://github.com/user-attachments/assets/8349531f-c0fa-4f0e-a29b-4c36d05faa3e)

##### 5. 🔹 Vincular a un hito (Milestone)  
- Agrupa el Issue en una **release** o fase del proyecto.

##### 6. 🔹 Agregar al tablero de proyecto (Projects)  
- Si usas **GitHub Projects**, muévelo a la columna correspondiente (To do, In progress, Done).

> Estas configuraciones facilitan la priorización y el seguimiento del trabajo.
---
### 8.4 📆 Milestones y vinculación con Pull Requests

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

### 8.5 🧩 Templates de Issue

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

### 8.6 💬 GitHub Discussions vs Wiki

#### GitHub Discussions

* Ideal para **preguntas abiertas**, ideas y debates.
* Soporta respuestas votadas y categorización.
* Fomenta comunidad.

#### Wiki

* Documentación estructurada.
* Soporte para páginas enlazadas y navegación por árbol.

> Ideal para manuales técnicos, guías de usuario, etc.

---

### 8.7 ⚙️ Automatización con Issues

#### Cerrar issues automáticamente desde PRs

Usa palabras clave como:

* `Fixes #12`
* `Resolves #45`
* `Closes #78`

> El Issue se cierra cuando el PR se fusiona en la rama principal.

---

### 8.8 🧠 Buenas prácticas

* Escribir títulos claros y concisos.
* Usar checklists para tareas múltiples.
* Comentar progreso en el mismo issue.
* Etiquetar y asignar para mantener orden.

---
