# 🌿 Ramas y flujos de trabajo colaborativo

Este módulo te enseña cómo usar **ramas (branches)**, **fusionar cambios (merge, rebase)**, **resolver conflictos**, y **colaborar con otros usando GitHub**. Estas habilidades te permiten trabajar en paralelo, experimentar sin riesgos, y contribuir de forma efectiva a proyectos de cualquier tamaño.

---

## 5.1 🌱 ¿Qué es una rama (branch)?

Una **rama** es una versión paralela del proyecto, una línea de desarrollo independiente que permite trabajar en nuevas funcionalidades sin afectar el código principal (generalmente `main` o `master`).

```bash
git branch nueva-rama     # Crear una rama
git switch nueva-rama     # Cambiarse a esa rama
```

> 💡 Puedes usar también:

```bash
git checkout -b nueva-rama  # Crear y cambiar en un solo paso
```

> 📸 *\[Sugerencia: insertar un diagrama con ramas paralelas (main vs feature)]*

---

## 5.2 🔀 Fusionar ramas (merge)

Cuando terminas de trabajar en una rama, puedes integrarla de nuevo a `main`:

```bash
git switch main
git merge nueva-rama
```

#### Tipos de merge:

* **Fast-forward**: cuando no hay cambios paralelos, Git “avanza” la rama.
* **Merge commit**: cuando hay divergencia, Git crea un commit de fusión.

> 📸 *\[Sugerencia: diagrama comparando fast-forward vs. merge commit]*

---

#### Comandos básicos:

```bash
git branch                # Ver todas las ramas locales
git branch nombre-rama    # Crear una nueva rama
git switch nombre-rama    # Cambiar a una rama
git checkout -b nueva     # Crear y cambiar en un solo paso
git branch -d nombre      # Eliminar una rama (solo si fue fusionada)
git branch -D nombre      # Forzar eliminación
```

> ✅ Las ramas son ideales para mantener el desarrollo limpio, organizado y libre de errores.

---

### 5.2 🔀 Fusiones y estrategias

#### `git merge` (fusión):

Combina dos ramas preservando el historial.

```bash
git switch main
git merge feature
```

#### `git rebase` (reorganización):

Aplica los commits de una rama sobre otra para obtener un historial lineal.

```bash
git switch feature
git rebase main
```

> ⚠️ No uses `rebase` en ramas compartidas públicamente (reescribe historia).

#### `git cherry-pick`:

Toma un commit específico de otra rama y lo aplica donde estés.

```bash
git cherry-pick <hash>
```

---

## 5.3 🧨 Conflictos de fusión

Un **conflicto** ocurre cuando Git no puede decidir cómo fusionar cambios.

1. Git marcará el archivo en conflicto así:

   ```txt
   <<<<<<< HEAD
   Línea en main
   =======
   Línea en rama
   >>>>>>> nueva-rama
   ```

2. Debes **editar manualmente**, eliminar los indicadores `<<<<<<<`, y confirmar la resolución:

```bash
git add archivo.txt
git commit
```

> ⚠️ Usa VS Code u otros editores para resolver conflictos más cómodamente.

---
### 5.3 🧨 Resolución de conflictos

Cuando Git no puede fusionar automáticamente, genera un **conflicto**.

Pasos:

1. Ver archivos en conflicto:

   ```bash
   git status
   ```
2. Editar archivos afectados y resolver manualmente:

   ```txt
   <<<<<<< HEAD
   Versión actual
   =======
   Versión de la otra rama
   >>>>>>> rama-feature
   ```
3. Confirmar la resolución:

   ```bash
   git add archivo
   git commit
   ```

> 💡 Usa editores como VS Code para resolverlos más fácilmente.

---

## 5.4 🧬 Rebase vs Merge

#### 🌀 `git rebase` (reescribe el historial):

```bash
git switch feature
git rebase main
```

Esto **aplica los commits de `feature` sobre el final de `main`**, creando un historial más limpio y lineal.

#### Comparación:

| Acción    | `merge`      | `rebase`                              |
| --------- | ------------ | ------------------------------------- |
| Historial | Ramificado   | Lineal                                |
| Seguridad | Seguro       | Peligroso si compartido               |
| Uso ideal | Colaboración | Historial limpio antes de merge final |

> 💡 *Usa `merge` cuando colaboras, y `rebase` en tu rama local para mantener un historial ordenado.*

---

## 5.5 🤝 Trabajo colaborativo en GitHub

#### Clonar un repositorio remoto

```bash
git clone https://github.com/usuario/repositorio.git
```

#### Crear tu propia rama de trabajo

```bash
git switch -c mi-feature
```

#### Subir una rama a GitHub

```bash
git push origin mi-feature
```

#### Crear un Pull Request (PR)

* Ve a GitHub y selecciona **"Compare & Pull Request"**.
* Describe tus cambios y solicita revisión.

#### Revisar y aceptar PRs

* Puedes ver los commits y archivos modificados.
* El dueño del repositorio puede **mergear** o **pedir cambios**.

> 📸 *\[Sugerencia: imagen de la interfaz de GitHub para un Pull Request]*

---

## 5.6 🧪 Ejercicio colaborativo simulado

**Objetivo**: Practicar un flujo completo de colaboración con ramas y Pull Requests.

1. Clona un repositorio propio o de prueba:

   ```bash
   git clone https://github.com/tu-usuario/mi-repo.git
   cd mi-repo
   ```

2. Crea una nueva rama:

   ```bash
   git switch -c feature-cambio-titulo
   ```

3. Haz un cambio y confírmalo:

   ```bash
   echo "Nuevo título" > titulo.txt
   git add .
   git commit -m "Agrega nuevo título"
   ```

4. Sube la rama:

   ```bash
   git push -u origin feature-cambio-titulo
   ```

5. Abre un Pull Request en GitHub y pídete a ti mismo una revisión ✨

---

### 5.4 🔁 Estrategias de branching en equipo

#### ✅ Git Flow (ideal para proyectos grandes)

* `main`: versión estable en producción
* `develop`: integración de features
* `feature/`: nuevas funcionalidades
* `release/`: versiones candidatas
* `hotfix/`: arreglos urgentes en producción

> 📌 Requiere mucha coordinación, ideal para ciclos de lanzamiento estructurados.

---

#### 🌐 GitHub Flow (proyectos con despliegue continuo)

* `main` siempre está desplegado.
* Cada cambio va en una nueva rama → PR → revisión → merge.

> ✅ Sencillo y ágil. Ideal para equipos que hacen deploy frecuente.

---

#### 🌳 Trunk Based Development (TBD)

* Todos trabajan directamente o mediante pequeñas ramas sobre `main`.
* Se promueve el uso de **feature toggles** y **testing automatizado**.

> 💥 Muy utilizado en DevOps y CI/CD. Requiere pruebas automatizadas sólidas.

---

### 5.5 📈 Comparación de estrategias

| Estrategia      | Complejidad | Escalabilidad | Frecuencia de Deploy | Uso ideal                     |
| --------------- | ----------- | ------------- | -------------------- | ----------------------------- |
| Git Flow        | Alta        | Alta          | Moderada             | Equipos grandes y controlados |
| GitHub Flow     | Media       | Media         | Alta                 | Equipos ágiles                |
| Trunk Based Dev | Baja        | Alta          | Muy Alta             | DevOps / Continuous Delivery  |

---

### 5.6 🧪 Buenas prácticas con ramas

* Usa nombres descriptivos: `feature/login-ui`, `bugfix/typo-footer`
* Haz commits pequeños y frecuentes
* Revisa conflictos antes de `merge` o `rebase`
* Borra ramas una vez fusionadas

---

### 5.7 📌 Alias útiles

```bash
git config --global alias.br "branch"
git config --global alias.co "checkout"
git config --global alias.cm "commit -m"
git config --global alias.st "status"
```

---

### 5.8 📸 Imágenes y diagramas sugeridos

* Diagrama de ramas paralelas (`main`, `feature`, `release`)
* Comparación visual entre `merge` vs `rebase`
* Flujo visual de Git Flow vs GitHub Flow vs Trunk Based


---

### 5.4 🔁 Estrategias de branching en equipo (continuación)

#### 🌳 **Trunk Based Development (TBD)**

* Todos trabajan sobre una única rama: `main` o `trunk`.
* Las ramas son **muy cortas** (de pocas horas o días).
* Se realiza **integración continua** (CI) para evitar conflictos grandes.

> ✅ Ideal para equipos DevOps, startups, y proyectos que despliegan muchas veces al día.

**Ventajas:**

* Menos conflictos acumulados.
* Historial más simple.
* Compatible con prácticas de entrega continua (CD).

**Buenas prácticas:**

* Feature flags (habilitar/deshabilitar funcionalidades sin hacer merge).
* Commits frecuentes con pruebas automatizadas.

---

### 5.5 💡 Recomendaciones generales de trabajo con ramas

| Buenas Prácticas                | Descripción                                                 |
| ------------------------------- | ----------------------------------------------------------- |
| ✅ Nombrar ramas de forma clara  | `feature/login`, `bugfix/header`, `hotfix/api-error`        |
| 🧪 Probar antes de hacer merge  | Usa CI (GitHub Actions, Travis, etc.)                       |
| 🔍 Crear Pull Requests pequeñas | Facilita la revisión de código                              |
| 🚫 Evitar ramas muy largas      | Ramas antiguas generan conflictos y duplicación de esfuerzo |

---

### 5.6 🧠 Casos prácticos para dominar el flujo de ramas

#### 🛠 Caso 1: Crear nueva funcionalidad

```bash
git switch -c feature/contact-form
# hacer cambios
git add .
git commit -m "Formulario de contacto agregado"
git push -u origin feature/contact-form
```

Crear un **Pull Request** desde GitHub para revisión.

---

#### 🔥 Caso 2: Arreglar error en producción (hotfix)

```bash
git switch -c hotfix/crash-home
# corregir error
git commit -am "Corrige crash en la home"
git push -u origin hotfix/crash-home
# luego hacer merge rápido a main
```

---

#### 🔄 Caso 3: Rebase de una rama antigua

```bash
git switch feature/login
git fetch origin
git rebase origin/main
```

Resuelve conflictos y actualiza la rama antes de hacer merge.

---

#### 🍒 Caso 4: Aplicar solo un commit de otra rama

```bash
git cherry-pick abc1234  # hash del commit útil
```

Muy útil cuando quieres reutilizar un cambio específico sin hacer merge total.

---

### 5.7 🧰 Recursos y herramientas útiles

* [Git Branching Models](https://nvie.com/posts/a-successful-git-branching-model/)
* Visual Studio Code (extensión GitLens)
* GitKraken / Sourcetree (clientes visuales de Git)
* GitHub Desktop (GUI oficial)
* Comando `git log --oneline --graph --all` para visualizar ramas gráficamente

---

## 5.7 📚 Recursos adicionales

* [Visualizing Branches (Git-SCM)](https://git-scm.com/book/en/v2/Git-Branching-Branches-in-a-Nutshell)
* [Guía oficial de Pull Requests (GitHub)](https://docs.github.com/en/pull-requests)
* [Learn Git Branching (interactivo)](https://learngitbranching.js.org/)
