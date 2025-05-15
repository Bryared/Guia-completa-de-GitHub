# 10. ⚙️ Automatización con GitHub Actions 🤖
---

**GitHub Actions** te permite diseñar y ejecutar pipelines de CI/CD directamente desde tu repositorio. Con ellas puedes:

- Ejecutar pruebas en cada push o PR  
- Generar documentación automáticamente  
- Desplegar artefactos a producción o entornos de staging  
- Integrar tareas de mantenimiento o notificaciones
  
| Ventaja                        | Descripción                                                             |
| ------------------------------ | ----------------------------------------------------------------------- |
| ⚡ **Eficiencia operativa**     | Reduce tareas repetitivas manuales, ahorra tiempo y errores.            |
| 🧪 **Integración continua**    | Ejecuta pruebas automáticamente con cada `push` o `pull request`.       |
| 🚀 **Despliegue automatizado** | Publica tu app o sitio web automáticamente en producción o staging.     |
| 📦 **Gestión de dependencias** | Usa bots como Dependabot para mantener paquetes seguros y actualizados. |
| 👀 **Mayor visibilidad**       | Revisa logs y flujos desde la interfaz de GitHub.                       |
| 📈 **Escalabilidad**           | Maneja múltiples tareas sin afectar el rendimiento del proyecto.        |
| 🔒 **Seguridad integrada**     | Escanea código, secretos y dependencias por vulnerabilidades.           |
| 🧰 **Personalización total**   | Crea workflows a medida según las necesidades de tu proyecto.           |

---
### 10.1 🧬 Estructura básica de un workflow

📁 Todos los workflows se almacenan en `.github/workflows/*.yml`.

```yaml
name: Nombre del workflow
on: [push, pull_request]

jobs:
  nombre_del_job:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - name: Paso personalizado
        run: echo "¡Hola desde GitHub Actions!"
```

---

### 10.2 🚀 Eventos de disparo (`on:`)

Puedes activar un workflow con distintos eventos:

| Evento              | Descripción                        |
| ------------------- | ---------------------------------- |
| `push`              | Cada vez que haces push a una rama |
| `pull_request`      | Cuando se abre/modifica un PR      |
| `schedule`          | Cron jobs (`cron: "0 0 * * *"`)    |
| `workflow_dispatch` | Manualmente desde la interfaz      |

---

### 10.3 🛠️ Jobs y pasos (`jobs` y `steps`)

* **Job**: conjunto de pasos que se ejecutan en un entorno.
* **Step**: cada comando o acción dentro del job.

```yaml
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - run: echo "Compilando el proyecto..."
```

---

### 10.4 🔁 Reutilización con Workflows Reusables

Puedes definir **workflows reutilizables** para compartir lógica entre repositorios o jobs.

```yaml
uses: usuario/repo/.github/workflows/workflow.yml@main
with:
  parametro: valor
```

---

### 10.5 🏪 GitHub Actions Marketplace

Repositorio oficial de **acciones preconstruidas** por la comunidad.

🔍 [marketplace.github.com](https://github.com/marketplace?type=actions)

Ejemplos:

* `actions/checkout`: clona el repo
* `actions/setup-node`: instala Node.js
* `peaceiris/actions-gh-pages`: despliegue a GitHub Pages

---

### 10.6 🔐 Secretos y seguridad

GitHub permite usar **secretos cifrados** para proteger tokens o contraseñas.

Configura desde:

> `Settings → Secrets and variables → Actions`

Y accede en el workflow como:

```yaml
env:
  TOKEN: ${{ secrets.MI_TOKEN }}
```

---

### 10.7 📦 Ejemplos de automatización

#### ✅ Integración continua (CI)

```yaml
on: push
jobs:
  test:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - name: Instalar dependencias
        run: npm install
      - name: Ejecutar pruebas
        run: npm test
```

#### 🌐 Despliegue automático a GitHub Pages

```yaml
uses: peaceiris/actions-gh-pages@v3
with:
  github_token: ${{ secrets.GITHUB_TOKEN }}
  publish_dir: ./dist
```

#### 📢 Notificaciones a Slack/Discord

Con Webhooks o usando acciones como:

* `8398a7/action-slack`
* `Ilshidur/action-discord`

---

### 🧠 Buenas prácticas

* Usar nombres claros y comentarios en los pasos
* No subir secretos en texto plano
* Modularizar y reutilizar workflows
* Hacer pruebas en ramas antes de aplicar en `main`

---
