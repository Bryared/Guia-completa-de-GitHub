# 9. 📊 Gestión de proyectos con GitHub Projects

GitHub Projects es una herramienta de gestión visual de tareas, similar a Trello o Jira, integrada directamente en tu repositorio o cuenta de organización. Permite planificar, priorizar y hacer seguimiento al trabajo con tableros Kanban.

---

## 9.1 🗂️ Tipos de Projects: Classic vs. Beta (Projects v2)

| Tipo                   | Descripción                                                               |
| ---------------------- | ------------------------------------------------------------------------- |
| **Classic Projects**   | Tableros tradicionales tipo Kanban (To do, In progress, Done)             |
| **Projects (Beta/v2)** | Basado en una tabla personalizable con filtros, vistas y campos avanzados |

> ✅ Projects v2 es más flexible, escalable y apto para equipos grandes.

---

## 9.2 📌 Crear un nuevo Project

1. Ir a la pestaña **Projects** de tu repositorio.
2. Elegir **Classic** o **Beta**.
3. Seleccionar una plantilla (Kanban, automatizado, vacío).
4. Configurar columnas o vistas.

---

## 9.3 📥 Añadir Issues y Pull Requests a un Project

* Desde el propio Issue o PR, usar la opción **"Projects"** para asignar.
* O arrastrar desde el tablero Kanban.
* En Projects v2: también puedes usar filtros por `label`, `milestone`, `assignee`, etc.

---

## 9.4 🔄 Automatizaciones

#### En Projects Classic

Puedes automatizar columnas para:

* Mover automáticamente un Issue a "In progress" al asignarlo.
* Pasar a "Done" cuando se cierre el PR.

#### En Projects Beta

Puedes usar reglas como:

* Si `status = In Review`, mostrar en columna "Revisión".
* Si se cierra el PR vinculado, cambiar estado a "Hecho".

---

## 9.5 📈 Métricas e Insights del repositorio

GitHub incluye varias métricas útiles:

#### En la pestaña **Insights**:

* Gráfica de commits por usuario
* Actividad en Pull Requests
* Issues abiertos/cerrados en el tiempo
* Contribuyentes principales
* Tráfico del repositorio (vistas y clones)
* Network graph (historial de forks y ramas)

---

## 9.6 💡 Buenas prácticas para equipos

* Usar **labels consistentes** para tareas (ej. `prioridad-alta`, `bloqueado`).
* Establecer una **convención para nombres de Projects** (ej. `Sprint-05`, `Versión-1.2.0`).
* Revisar el Project semanalmente para actualizar estados y priorizar.

---

## 🧠 Tips adicionales

* Puedes tener **Projects a nivel de usuario**, **repositorio** u **organización**.
* Projects v2 permite agregar campos personalizados: fechas, prioridades, estimaciones, etc.
* ¡Puedes vincular GitHub Projects con herramientas como [Zepel](https://zepel.io), [ZenHub](https://www.zenhub.com) o [Linear](https://linear.app) si quieres funciones aún más avanzadas!

---
