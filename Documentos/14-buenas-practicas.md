# 14. 🛡️ Buenas prácticas, seguridad y herramientas avanzadas

La gestión responsable de proyectos en GitHub no se trata solo de código funcional, sino también de mantener estándares, seguridad y colaboración efectiva. Aquí verás cómo lograrlo.

---

### 14.1 🧱 Buenas prácticas de repositorio

#### Archivos esenciales

* `README.md`: Presenta el propósito del proyecto, cómo usarlo, instalarlo, y contribuir.
* `LICENSE`: Define los derechos de uso y distribución.
* `CONTRIBUTING.md`: Guía para colaborar correctamente.
* `CODE_OF_CONDUCT.md`: Reglas de convivencia.
* `CHANGELOG.md`: Historial de cambios.

#### Estructura ordenada

* Usa carpetas claras como `/src`, `/docs`, `/tests`, `/examples`
* Evita archivos innecesarios en la raíz
* `.gitignore` bien definido para evitar subir archivos sensibles o temporales

---

### 14.2 🔒 Seguridad y protección

#### Protecciones en ramas (`Branch Protection Rules`)

* Requerir revisiones antes de merge
* Impedir pushes directos a `main`
* Activar verificación de firmas (`signed commits`)
* Prohibir force push o eliminar ramas protegidas

#### Dependabot

* Automatiza actualizaciones de dependencias inseguras
* Notifica y crea PRs con parches sugeridos

#### Code Scanning

* Usa herramientas de análisis estático para detectar errores de seguridad (CodeQL)
* Se configura desde GitHub Actions fácilmente

#### Secret Scanning

* Detecta accidentalmente tokens/API keys subidas al repo
* Funciona automáticamente en repos públicos

---

### 14.3 ⚙️ Automatización con GitHub CLI y API

#### GitHub CLI (`gh`)

Comandos útiles:

```bash
gh repo clone usuario/repositorio
gh pr create --fill
gh issue list
gh codespace create
```

#### GitHub API

* Realiza automatizaciones avanzadas (crear issues, PRs, comentarios)
* Se puede usar desde scripts en Python, JS, Bash
* Requiere token de autenticación

[GitHub REST API docs](https://docs.github.com/en/rest)

---

### 14.4 🧰 GitHub Marketplace y herramientas externas

* Instala Apps para CI/CD, documentación, revisión de código, etc.
* Ejemplos:

  * **Codecov** (cobertura de pruebas)
  * **LGTM** (code quality)
  * **Snyk** (seguridad)
  * **Slack/GitHub integration**

---

### 14.5 🧠 Consejos finales para equipos

* Mantén la documentación actualizada
* Automatiza lo repetitivo con Actions y CLI
* Usa Issues y Projects para planificar en lugar de chats desorganizados
* Revisa y limpia ramas muertas o sin uso
* Fomenta revisiones constructivas de PRs

---
