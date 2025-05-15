# 9. 📊 Gestión de proyectos con GitHub Projects

GitHub Projects es una herramienta de gestión visual de tareas, similar a Trello o Jira, integrada directamente en tu repositorio o cuenta de organización. Permite planificar, priorizar y hacer seguimiento al trabajo con tableros Kanban.
![image](https://github.com/user-attachments/assets/d99761fb-e216-4e2e-899d-5c0c3cf97e9f)


---

## 9.1 🗂️ Tipos de Projects: Classic vs. Beta (Projects v2)

| Tipo                   | Descripción                                                               |
| ---------------------- | ------------------------------------------------------------------------- |
| **Classic Projects**   | Tableros tradicionales tipo Kanban (To do, In progress, Done)             |
| **Projects (Beta/v2)** | Basado en una tabla personalizable con filtros, vistas y campos avanzados |

> ✅ Projects v2 es más flexible, escalable y apto para equipos grandes.

---

## 9.2 📌 Crear un nuevo Project en GitHub

#### 1. Acceder a la sección de Projects

* Haz clic en tu foto de perfil en la esquina superior derecha y selecciona **Your profile**.
* En tu perfil, haz clic en la pestaña **Projects**.([GitHub Docs][2])
* ![image](https://github.com/user-attachments/assets/385f6f5f-f000-4dec-9bd3-f2f2293e6f75)

> Si deseas crear un proyecto a nivel de organización, ve a la página de tu organización y selecciona la pestaña **Projects**.

#### 2. Iniciar la creación de un nuevo proyecto

* Haz clic en el botón **New project**.
* ![image](https://github.com/user-attachments/assets/8163a1f7-491a-4db0-afaa-981398318c1c)


#### 3. Elegir una plantilla o empezar desde cero

* Para comenzar desde cero, selecciona una de las siguientes opciones bajo "Start from scratch":

  * **Table**: Vista de tabla para gestionar tareas con campos personalizados.
  * **Board**: Vista tipo tablero Kanban para seguimiento visual del flujo de trabajo.
  * **Roadmap**: Vista para planificar y visualizar el progreso a lo largo del tiempo.([GitHub Docs][2], [GitHub Docs][3])

* También puedes elegir una plantilla predefinida que se adapte a tus necesidades.
*   ![image](https://github.com/user-attachments/assets/3a3c2714-3b7d-4eb0-9680-5df77ff66c2f)
> Las plantillas ofrecen configuraciones predeterminadas que pueden incluir campos, vistas y automatizaciones específicas.

#### 4. Configurar los detalles del proyecto

* En el campo **Project name**, ingresa un nombre descriptivo para tu proyecto.
* Opcionalmente, añade una descripción que detalle el propósito y alcance del proyecto.([GitHub Docs][3])

#### 5. Crear el proyecto

* Haz clic en **Create project** para finalizar la creación.([GitHub Docs][3])

> Una vez creado, podrás personalizar las vistas, agregar campos personalizados, establecer automatizaciones y vincular issues o pull requests según las necesidades de tu equipo.

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
* Aqui tienes una lista de videos que te pueden ayudar con este tema:
    1. GITHUB PROJECTS: Como Generar un tablero de proyectos [youtube.com/watch?v=RZD9bgySx8s&ab_channel=8Dev](https://www.youtube.com/watch?v=RZD9bgySx8s&ab_channel=8Dev)
---
