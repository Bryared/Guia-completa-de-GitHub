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

#### 🖥️ Ejemplo práctico: Clonar un repositorio con VS Code

#### 👉 ¿Cuándo usar `git clone`?

Cuando tienes **acceso directo** al repositorio o no necesitas hacer un *fork*. Es ideal para trabajar en tus propios proyectos o en repos colaborativos donde tienes permiso.

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

### 7.2 📤 Crear un Pull Request (PR)

Un **Pull Request (PR)** permite proponer y discutir cambios antes de integrarlos a la rama principal de un repositorio (como `main` o `develop`).
Se usa para colaboración, revisión de código, y mantener un historial limpio.

> ⚠️ Ideal cuando trabajas en una rama o en un fork y quieres que tus cambios se integren al proyecto principal.

#### 🔹 ¿Cuándo usar un PR?

* Cuando desarrollas una nueva funcionalidad en una rama (`feature/login`).
* Al corregir errores desde una rama separada (`fix/typo`).
* Si colaboras en un proyecto externo desde un **fork**.
* Siempre que quieras una **revisión antes de hacer merge**.

---

#### 🔹 Pasos para crear un Pull Request

1. ✅ **Asegúrate de que tu rama esté actualizada**
   *Sincroniza con la rama principal para evitar conflictos.*

   ```bash
   git checkout main
   git pull origin main
   git checkout mi-rama
   git rebase main
   ```

2. 📤 **Sube tus cambios al repositorio remoto**

   ```bash
   git push origin mi-rama
   ```

3. 🟢 **Desde GitHub, haz clic en “Compare & pull request”**
   GitHub detectará automáticamente que tu rama tiene cambios no integrados.
   ![image](https://github.com/user-attachments/assets/a280f588-360e-4705-bda9-bbd4d95c626e)

5. ✍️ **Completa el formulario del PR**

   * **Título claro y descriptivo**.
   * **Descripción detallada** de qué hiciste y por qué.
   * Agrega capturas si es visual.
   * Asigna revisores si es necesario.
   * ![image](https://github.com/user-attachments/assets/f2828e73-6d4e-483f-a4a0-c97134a6bec8)

6. 🔗 **Vincula un Issue automáticamente (opcional)**
   Si el PR resuelve un issue, puedes mencionarlo:

   ```
   Fixes #123
   Closes #45
   ```

   > GitHub cerrará el issue automáticamente al hacer merge del PR.

7. ⏳ **Espera revisión**
   Tus compañeros pueden:

   * ✅ Aprobar
   * 🛠️ Solicitar cambios
   * 💬 Comentar

8. 🔀 **Haz merge cuando esté aprobado**
   Elige entre:

   * **Merge Commit** → Combina con historial completo.
   * **Squash and Merge** → Junta todos los commits en uno.
   * **Rebase and Merge** → Aplica los commits uno a uno sobre la rama base.

> 🧼 **Consejo:** Evita trabajar directamente en `main`. Siempre crea ramas nuevas para tus cambios y usa PR para integrarlos de forma ordenada y segura.

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
