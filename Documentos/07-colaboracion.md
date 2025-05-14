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

¡Buena observación! Sí, sería **muy útil incluir un ejemplo práctico usando `git clone` desde Visual Studio Code (VS Code)**, ya que es una herramienta muy popular, especialmente para quienes recién comienzan y prefieren trabajar con interfaz gráfica. Aquí tienes una **sección ampliada para agregar al punto 7.1 🍴 Fork vs. Clone**, que incluye un ejemplo con `clone` en VS Code:

---

### 🖥️ Ejemplo práctico: Clonar un repositorio con VS Code

#### 👉 ¿Cuándo usar `git clone`?

Cuando tienes **acceso directo** al repositorio o no necesitas hacer un *fork*. Es ideal para trabajar en tus propios proyectos o en repos colaborativos donde tienes permiso.

---

#### 🔧 Pasos para clonar un repositorio en VS Code:

1. **Copia la URL del repositorio** desde GitHub:

   * Ejemplo: `https://github.com/usuario/repositorio-ejemplo.git`

2. **Abre VS Code** y presiona:

   * `Ctrl + Shift + P` (Windows/Linux)
   * `Cmd + Shift + P` (Mac)
   * Se abrirá la paleta de comandos.

3. Escribe `Git: Clone` y selecciona la opción.

4. Pega la URL del repositorio.

5. Elige una carpeta local donde guardar el proyecto.

6. VS Code te preguntará si quieres **abrir el repositorio clonado**. Haz clic en `Open`.

> Ahora tienes el repositorio descargado en tu maquina, listo para hacer nuevas ramas, hacer commits, push, pulls, y cualquier cambio que creas que pueda aportar al trabajo

---

### 📸 Vista en VS Code:

Puedes añadir una captura como esta para hacerlo más visual:

```
[ VS Code abriendo un repo clonado desde GitHub ]
```
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
