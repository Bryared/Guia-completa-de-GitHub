# 14. 🔧 Herramientas Avanzadas y Extensibilidad en GitHub

GitHub no solo es una plataforma para alojar y colaborar en código; también es un ecosistema altamente extensible que permite automatizar procesos, integrar herramientas externas, y personalizar completamente el flujo de desarrollo. En esta sección aprenderás a usar herramientas avanzadas que te permiten interactuar con GitHub más allá de la interfaz web, integrarlo con otros servicios y ampliar sus funcionalidades.

---

## 14.1 🧰 GitHub CLI (`gh`): Potencia GitHub desde tu terminal

La **GitHub CLI** es una herramienta de línea de comandos oficial que permite interactuar con GitHub directamente desde tu terminal.

### 🔹 ¿Qué puedes hacer con `gh`?

* Crear y revisar *Pull Requests* (`gh pr create`, `gh pr review`)
* Gestionar *issues* (`gh issue list`, `gh issue create`)
* Clonar repositorios (`gh repo clone`)
* Ver notificaciones (`gh notifications`)
* Administrar proyectos, releases y más

### 🔹 Ejemplo básico

```bash
gh repo clone usuario/repositorio
gh pr create --base main --head feature-rama --title "Añadir funcionalidad"
```

📘 Más información: [GitHub CLI Docs](https://cli.github.com/)

---

## 14.2 🔌 GitHub REST API y GraphQL API

Si necesitas acceder a GitHub desde tus propias aplicaciones o scripts, puedes usar sus potentes APIs.

### 🔹 REST API

Es la API más tradicional y ampliamente utilizada. Permite realizar operaciones sobre:

* Repositorios
* Commits
* Pull requests
* Issues
* Usuarios y organizaciones

### 🔹 GraphQL API

Permite consultar exactamente los datos que necesitas con mayor eficiencia, ideal para integraciones más complejas o personalizadas.

### 🧪 Ejemplo de llamada REST usando `curl`

```bash
curl -H "Authorization: token TU_TOKEN" https://api.github.com/user/repos
```

📘 Docs: [REST](https://docs.github.com/en/rest) | [GraphQL](https://docs.github.com/en/graphql)

---

## 14.3 🧩 GitHub Apps y OAuth Apps

Estas aplicaciones permiten extender GitHub, automatizar tareas, o conectar con servicios externos.

### 🔹 GitHub Apps

* Se instalan en repositorios u organizaciones.
* Tienen permisos específicos y tokens propios.
* Se usan para bots, integraciones de CI/CD, y automatizaciones seguras.

### 🔹 OAuth Apps

* Se usan cuando un usuario otorga acceso a su cuenta GitHub desde otra aplicación.
* Son comunes en dashboards, IDEs o apps web externas.

📘 Documentación: [GitHub Apps](https://docs.github.com/en/apps)

---

## 14.4 🌐 Webhooks

Los **Webhooks** permiten que GitHub envíe notificaciones automáticas a otros sistemas cuando ocurren eventos como *push*, *pull request* o *issue*.

### 🔹 Casos de uso:

* Activar un pipeline de CI/CD en Jenkins o CircleCI
* Notificar a Slack cuando alguien hace un push
* Desplegar automáticamente un sitio web

### 🔹 Ejemplo:

Cuando alguien hace `git push`, GitHub puede llamar a una URL como:

```http
POST https://tuservidor.com/deploy
Payload: {
  "event": "push",
  "repository": "tu-repo",
  ...
}
```

📘 [Configurar Webhooks](https://docs.github.com/en/webhooks)

---

## 14.5 🛒 GitHub Marketplace

El **GitHub Marketplace** es una tienda de aplicaciones y *Actions* listas para usar en tus proyectos.

### 🔹 Tipos de herramientas disponibles:

* Integraciones CI/CD (Travis CI, CircleCI)
* Análisis de código (CodeQL, SonarCloud)
* Notificaciones y reportes (Slack, Sentry)
* Deploys (Netlify, Vercel)

📘 Explora: [GitHub Marketplace](https://github.com/marketplace)

---

## 14.6 ♻️ GitHub Actions: Reusable Workflows

Además de crear flujos de trabajo únicos, GitHub Actions permite reutilizar flujos (`reusable workflows`) entre distintos repositorios.

### 🔹 ¿Para qué sirve?

* Compartir lógica de CI/CD entre múltiples proyectos.
* Crear acciones estándar para tu equipo u organización.

### 🔹 Estructura básica

```yaml
jobs:
  call-workflow:
    uses: usuario/repo/.github/workflows/flujo.yml@main
    with:
      nombre: "Ejemplo"
```

📘 [Reusable Workflows](https://docs.github.com/en/actions/using-workflows/reusing-workflows)

---

## 14.7 🔗 Integración con herramientas externas (Slack, Jira, etc.)

GitHub puede integrarse con múltiples herramientas de terceros para sincronizar tareas, notificaciones y código.

### 🔹 Ejemplos comunes:

* Enviar mensajes automáticos a **Slack** cuando se abre un PR.
* Sincronizar issues con **Jira** para gestión ágil.
* Integración con **Notion**, **Discord**, **Asana**, etc.

📘 En la mayoría de los casos, se configuran mediante:

* Webhooks
* GitHub Apps
* GitHub Actions + APIs externas

---

## 14.8 🧠 Scripts avanzados: combinando Actions + API

Puedes crear **automatizaciones personalizadas** combinando GitHub Actions con la REST API (o GraphQL API) para lograr flujos avanzados.

### 🔹 Ejemplo:

* Al cerrar un Pull Request:

  * Ejecutar tests
  * Comentar automáticamente los resultados
  * Notificar a un canal de Slack
  * Actualizar el estado de una tarjeta en GitHub Projects

```yaml
steps:
  - name: Llamar API para mover Issue
    run: |
      curl -X POST -H "Authorization: token ${{ secrets.TOKEN }}" \
        -d '{"column_id": "123456"}' \
        https://api.github.com/projects/columns/cards/789/moves
```

---
