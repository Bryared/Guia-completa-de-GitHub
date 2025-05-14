# 7. 🤝 Colaboración: Forks, Pull Requests y revisiones

La colaboración es uno de los pilares de GitHub. Los **Forks**, **Pull Requests (PRs)** y las **revisiones** permiten que múltiples desarrolladores trabajen juntos, incluso sin tener acceso directo al repositorio principal.

---

### 7.1 🍴 Fork vs. Clone

| Concepto    | Descripción                                                         |
| ----------- | ------------------------------------------------------------------- |
| `git clone` | Copia un repo para trabajar en tu máquina local.                    |
| **Fork**    | Crea una **copia completa** del repositorio en tu cuenta de GitHub. |

> 🔁 Forks se usan para contribuir a proyectos cuando no tienes permisos de escritura.

#### Ejemplo de flujo con fork:

1. Haces fork de un repo (botón **Fork** en GitHub).
2. Clonas tu fork a tu máquina local.
3. Haces cambios → commit → push.
4. Abres un **Pull Request** hacia el repositorio original.

---

### 7.2 📤 Crear un Pull Request (PR)

Un PR solicita que los cambios en tu rama (local o de fork) se integren al repositorio principal.

1. Asegúrate de que tu rama esté actualizada.
2. Pulsa el botón **“Compare & pull request”**.
3. Describe claramente tus cambios.
4. Espera revisión y aprobación.

> 🧼 Es buena práctica vincular el PR a un Issue usando: `Fixes #123`.

---

### 7.3 🧪 Revisar y fusionar PRs

Revisar un PR implica:

* Verificar el código.
* Comentar o sugerir cambios.
* Ejecutar pruebas si es necesario.

En GitHub puedes:

* Aprobar (✅).
* Solicitar cambios (🛠️).
* Comentar sin bloquear (💬).

Después de la revisión:

* **Merge**: integrar con la rama base.
* **Squash & merge**: combina todos los commits en uno.
* **Rebase & merge**: reescribe la historia para que sea lineal.

---

### 7.4 ✍️ Pull Request Drafts

Los **drafts** (borradores) son PRs en progreso. Útiles para:

* Mostrar intención de cambios sin aún estar listos.
* Pedir feedback temprano.

```text
Estado del PR: “Draft”
```

> ✅ Puedes convertir un draft a PR normal cuando esté listo.

---

### 7.5 📄 Plantillas de Pull Request

Puedes definir un formato predeterminado para todos los PRs en tu proyecto.

📁 `.github/PULL_REQUEST_TEMPLATE.md`

```markdown
## Descripción del cambio
...

## Cambios realizados
- [x] Nuevo componente
- [x] Corrección de bug

## Referencias relacionadas
Fixes #...

## Checklist
- [ ] Código probado
- [ ] Documentación actualizada
```

---

### 7.6 🧑‍💻 GitHub CLI para PRs

#### Instalar GitHub CLI:

[https://cli.github.com/](https://cli.github.com/)

#### Comandos útiles:

```bash
gh pr create       # Crear un PR desde terminal
gh pr view         # Ver detalles del PR actual
gh pr checkout ID  # Cambiar a rama del PR
gh pr review       # Comentar o aprobar PR
```

> 💡 Acelera tu flujo sin salir de la terminal.

---

### 7.7 🧠 Buenas prácticas de colaboración

| Práctica                   | Beneficio                           |
| -------------------------- | ----------------------------------- |
| Commits pequeños y claros  | Más fácil de revisar                |
| PRs de menos de 300 líneas | Menos propensos a errores           |
| Usar Issues y vincularlos  | Facilita el seguimiento             |
| Revisar código de otros    | Mejora el conocimiento del proyecto |
| Evitar merges forzados     | Mantiene historial limpio           |

---
