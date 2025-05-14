# 🌿 Ramas y flujos de trabajo colaborativo

Este módulo te enseña cómo usar **ramas (branches)**, **fusionar cambios (merge, rebase)**, **resolver conflictos**, y **colaborar con otros usando GitHub**. Estas habilidades te permiten trabajar en paralelo, experimentar sin riesgos, y contribuir de forma efectiva a proyectos de cualquier tamaño.

---

## 5.1 🌱 ¿Qué es una rama (branch)?

Una **rama** es una línea de desarrollo independiente que permite trabajar en nuevas funcionalidades sin afectar el código principal (generalmente `main` o `master`).

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

## 5.7 📚 Recursos adicionales

* [Visualizing Branches (Git-SCM)](https://git-scm.com/book/en/v2/Git-Branching-Branches-in-a-Nutshell)
* [Guía oficial de Pull Requests (GitHub)](https://docs.github.com/en/pull-requests)
* [Learn Git Branching (interactivo)](https://learngitbranching.js.org/)
