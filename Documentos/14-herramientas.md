# 14. 🔧 Herramientas Avanzadas y Extensibilidad en GitHub

GitHub no solo es una plataforma para alojar y colaborar en código; también es un ecosistema altamente extensible que permite automatizar procesos, integrar herramientas externas, y personalizar completamente el flujo de desarrollo. En esta sección aprenderás a usar herramientas avanzadas que te permiten interactuar con GitHub más allá de la interfaz web, integrarlo con otros servicios y ampliar sus funcionalidades.

---

## 14.1 🧰 GitHub CLI (`gh`): Potencia GitHub desde tu terminal

La **GitHub CLI (`gh`)** (Command Line Interface) es una herramienta oficial de línea de comandos que te permite interactuar con GitHub sin salir de la terminal. 

Es ideal para automatizar tareas, flujos, gestionar issues, revisiones, proyectos, trabajar más rápido, integrar scripts en flujos de desarrollo, y mantener un enfoque productivo sin depender de la interfaz web.

> 🚀 Ideal para desarrolladores, DevOps, contributors open source y equipos que usan GitHub como centro de desarrollo.

---

### 🛠️ Instalación

Instala desde: [https://cli.github.com/](https://cli.github.com/)


---
### 🔹 ¿Qué puedes hacer con `gh`?

| Categoría         | Comando base               | Qué permite hacer                                  |
| ----------------- | -------------------------- | -------------------------------------------------- |
| Pull Requests     | `gh pr`                    | Crear, revisar, ver, cerrar, hacer checkout de PRs |
| Issues            | `gh issue`                 | Crear, asignar, listar, cerrar issues              |
| Repositorios      | `gh repo`                  | Clonar, crear, forkear, ver repos                  |
| Releases          | `gh release`               | Crear, ver, subir assets a releases                |
| Gists             | `gh gist`                  | Crear, listar y ver gists desde la terminal        |
|Autenticación	    |`gh auth login`, `gh auth status`| Automatizar autenticación                     |
| Projects          | `gh project`               | Gestionar tableros de proyectos (CLI beta o v2)    |
| Notificaciones    | `gh notifications`         | Ver y gestionar notificaciones                     |
| Alias/Extensiones | `gh alias`, `gh extension` | Personalizar y extender comandos                   |

---
#### Ejemplos rápidos:

```bash
# macOS (Homebrew)
brew install gh

# Windows (scoop)
scoop install gh

# Ubuntu/Debian
sudo apt install gh
```

### 🔐 Autenticación

Antes de usar `gh`, necesitas autenticarte:

```bash
gh auth login
```

> Puedes elegir entre autenticación por navegador o token personal (PAT). Es segura y solo necesitas hacerlo una vez.

### 🔹 Ejemplo básico

```bash
gh repo clone usuario/repositorio
gh pr create --base main --head feature-rama --title "Añadir funcionalidad"
```
### 🧪 Ejemplo práctico: Crear un repositorio y primer issue

```bash
gh repo create mi-repo --public --source=. --remote=origin
gh issue create --title "Mejora el README" --body "Agrega badges y enlaces útiles"
```

### 📦 Comandos avanzados útiles

```bash
gh repo clone org/proyecto       # Clonar un repo desde GitHub
gh pr status                     # Ver PRs abiertos y asignados
gh issue list --assignee @me     # Ver issues asignadas
gh release create v1.0.0         # Crear una release
gh alias set ci 'gh pr checks'   # Crear un alias personalizado
```

### ✨ Alias personalizados

Puedes crear tus propios comandos abreviados:

```bash
gh alias set mi-pr 'pr create --fill'
gh alias set m 'pr merge --merge'
```


### 🧩 Extensiones de GitHub CLI

La comunidad y GitHub han creado **extensiones** para `gh`. Puedes explorarlas y agregarlas:

```bash
gh extension install dlvhdr/gh-dash     # Dashboard visual para PRs e issues
gh extension install github/gh-copilot  # Usar GitHub Copilot desde la terminal
```

> Consulta más en: [https://github.com/topics/gh-extension](https://github.com/topics/gh-extension)


### 🧠 Integración con scripts

Puedes usar `gh` dentro de scripts Bash, CI/CD o workflows personalizados:

```bash
#!/bin/bash
gh issue list --label "bug" --state open > bugs.txt
```

> 🔁 Combina `gh` con **GitHub Actions** o tareas en tu terminal para automatizar procesos.


### 🧼 Buenas prácticas

* Usa `gh` para integrarte más rápidamente en proyectos colaborativos.
* Crea alias para comandos frecuentes.
* Automatiza flujos repetitivos con scripts y `gh`.
* Usa `gh pr view` o `gh pr diff` para revisar código en contexto.
* Mantén actualizada la CLI con `gh version` y `gh upgrade`.

###📘 Más información: 
* [Documentación oficial de GitHub CLI](https://cli.github.com/manual/)
* [GitHub CLI en GitHub](https://github.com/cli/cli)
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
