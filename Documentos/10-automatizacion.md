# 10. ⚙️ Automatización con GitHub Actions 🤖

GitHub Actions es la solución integrada de **automatización** dentro de GitHub. Permite crear flujos de trabajo que se ejecutan automáticamente en respuesta a eventos del repositorio, como *push*, *pull requests*, *releases*, o tareas programadas. Es ideal para CI/CD, pruebas automáticas, despliegues, y mucho más.

---
## 10.0 🤖 Conceptos de Automatización

* **Automatización**: uso de scripts y herramientas para ejecutar tareas repetitivas sin intervención manual.
* **Pipeline**: secuencia de etapas (build, test, deploy, monitor) que se ejecutan de forma automática.
* **Idempotencia**: cada ejecución produce el mismo resultado si parte del mismo estado; evita efectos secundarios inesperados.
* **Modularidad**: dividir el pipeline en jobs y steps independientes para facilitar el mantenimiento y la depuración.
* **Paralelismo**: ejecución concurrente de tareas (por ejemplo, tests en diferentes entornos) para acelerar tiempos de respuesta.
* **Retroalimentación rápida (Fast Feedback)**: informar inmediatamente sobre fallos en cualquier etapa para corregir a tiempo.
* **Observabilidad**: recogida de logs, métricas y alertas en cada paso del pipeline para monitorizar su salud y rendimiento.
* **Infraestructura como Código (IaC)**: definir y gestionar entornos y configuraciones mediante archivos (por ejemplo, Terraform, Ansible).
* **Gestión de secretos**: almacenamiento seguro de credenciales y tokens para evitar filtraciones.

### 📝 YAML

YAML (“YAML Ain’t Markup Language”) es un formato de texto sencillo y legible, ideal para definir workflows en GitHub Actions.

- **Indentación con espacios**  
  - Usa siempre **2 espacios** por nivel (¡nunca tabuladores!).  
  - Los niveles de indentación delimitan la jerarquía.

* **Claves y valores**:
  - Se definen con `clave: valor`.  
  - El valor puede ser texto, número, booleano (`true`/`false`) o lista anidada.
 
  ```yaml
  clave: valor
  nombre: Juan
  edad: 30
  ```
* **Listas**:

  ```yaml
  lista:
    - item1
    - item2
  frutas:
    - manzana
    - banana
  ```
* **Jerarquía** (bloques anidados):

  ```yaml
  jobs:
    build:
      steps:
        - run: echo "Hola"
  ```
* **Comentarios**: Usa `#` para añadir notas.


## 10.1 🧠 ¿Qué es GitHub Actions?

GitHub Actions es un sistema de automatización basado en **archivos YAML** que viven dentro de tu repositorio. Define “**qué hacer**”, “**cuándo hacerlo**” y “**dónde ejecutarlo**”.

**GitHub Actions** te permite diseñar y ejecutar pipelines de Integración(CI)/Despliegue(CD) Continuo directamente desde tu repositorio. Con ellas puedes:

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

## 10.2 🧬 Estructura básica de un workflow

📁 Todos los workflows se almacenan en `.github/workflows/*.yml`.

```
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

## 10.3 🚀 Eventos de disparo (`on:`)

Puedes activar un workflow con distintos eventos:

| Evento              | Descripción                        |
| ------------------- | ---------------------------------- |
| `push`              | Cada vez que haces push a una rama |
| `pull_request`      | Cuando se abre/modifica un PR      |
| `schedule`          | Cron jobs (`cron: "0 0 * * *"`)    |
| `workflow_dispatch` | Manualmente desde la interfaz      |

---

## 10.4 🛠️ Jobs y pasos (`jobs` y `steps`)

* **Job**: conjunto de pasos que se ejecutan en un entorno.
* **Step**: cada comando o acción dentro del job.

```
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - run: echo "Compilando el proyecto..."
```

---
## 10.5 🔄 CI/CD: Integración y Despliegue Continuo

CI/CD es una práctica que automatiza todo el ciclo de vida de una aplicación: desde integrar y probar cambios (Integración Continua, CI) hasta preparar y entregar nuevas versiones a entornos de prueba o producción (Entrega/Despliegue Continuo, CD). Al usar pipelines automatizados, elimina errores manuales y evita el “Integration Hell”, permitiendo lanzar actualizaciones frecuentes y fiables con el apoyo de metodologías DevOps.

### CI – *Integración Continua* (Continuous Integration)

Proceso donde cada cambio en el código es **integrado y probado automáticamente**.

✅ Automatiza la construcción y prueba de tu código en cada cambio.

✅ Asegura que el nuevo código **no rompa lo anterior**: Mantiene la calidad del código

✅ Detecta errores **tempranamente** en el ciclo de desarrollo.

![](https://www.simplilearn.com/ice9/free_resources_article_thumb/Continuous_Integration.png)


### CD – *Entrega Continua / Despliegue Continuo* (Continuous Delivery / Deployment)

Permite que el software sea **entregado automáticamente a entornos de staging o producción** después de pasar las pruebas.

🚀 Minimiza el tiempo entre escribir código (time-to-market) y verlo funcionando en vivo (errores manuales).

![](https://vitolavecchia.altervista.org/wp-content/uploads/2020/02/Caratteristiche-e-differenza-tra-Continuous-Integration-Continuous-Delivery-e-Continuous-Deployment-nello-sviluppo-software.png)

### Enfoque
 🧪 CI se enfoca en **probar**; CD se enfoca en **entregar/desplegar**.

**Ventajas del uso de CI/CD con GitHub Actions:**

* Reducción de errores humanos
* Feedback inmediato
* Ahorro de tiempo en tareas repetitivas
* Facilita equipos distribuidos

![](https://www.testingdocs.com/wp-content/uploads/CiCD-pipeline.png)

---


## 📦 Ejemplos de automatización

### ✅ Integración continua (CI)

```
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

### 🌐 Despliegue automático a GitHub Pages

```yaml
uses: peaceiris/actions-gh-pages@v3
with:
  github_token: ${{ secrets.GITHUB_TOKEN }}
  publish_dir: ./dist
```

## 🔔 Notificaciones y tareas externas

Envía avisos a Slack, Discord o cualquier webhook:

* `8398a7/action-slack`
* `Ilshidur/action-discord`

---

## 10.4 🔁 Reutilización con Workflows Reusables

Puedes definir **workflows reutilizables** para compartir lógica entre repositorios o jobs.

```yaml
uses: usuario/repo/.github/workflows/workflow.yml@main
with:
  parametro: valor
```

---

## 10.5 🏪 GitHub Actions Marketplace

Repositorio oficial de **acciones preconstruidas** por la comunidad.

🔍 [marketplace.github.com](https://github.com/marketplace?type=actions)

Ejemplos:

* `actions/checkout`: clona el repo
* `actions/setup-node`: instala Node.js
* `peaceiris/actions-gh-pages`: despliegue a GitHub Pages

---

## 10.6 🔐 Secretos y seguridad

GitHub permite usar **secretos cifrados** para proteger tokens o contraseñas.

Configura desde:

> `Settings → Secrets and variables → Actions`

Y accede en el workflow como:

```yaml
env:
  TOKEN: ${{ secrets.MI_TOKEN }}
```

---

## 10.12 ✨ Avanzado: Matrices y extensiones

### Matrices (paralelizar)

```yaml
strategy:
  matrix:
    node: [14, 16, 18]
steps:
  - uses: actions/setup-node@v4
    with: { node-version: ${{ matrix.node }} }
```

### Extensiones y alias

```bash
gh extension install dlvhdr/gh-dash
gh alias set deploy 'workflow run deploy.yml'
```

---


### 🧠 Buenas prácticas

* Usar nombres claros y comentarios en los pasos
* No subir secretos en texto plano
* Modularizar y reutilizar workflows
* Hacer pruebas en ramas antes de aplicar en `main`

---
