# 🌿 Ramas y flujos de trabajo colaborativo

Este módulo te enseña cómo usar **ramas (branches)**, **fusionar cambios (merge, rebase)**, **resolver conflictos**, y **colaborar con otros usando GitHub**. Estas habilidades te permiten trabajar en paralelo, experimentar sin riesgos, y contribuir de forma efectiva a proyectos de cualquier tamaño.

---

## 5.1 🌿 ¿Qué es una rama en Git?

Una **rama** en Git es un puntero móvil a un commit. Representa una línea de trabajo independiente dentro del proyecto.

Git no guarda cambios como diferencias entre archivos, sino como **instantáneas completas** del proyecto en cada commit. Cada commit incluye:
1. Git calcula un **hash SHA-1** para cada archivo preparado.
2. Crea una copia del archivo (blob) en el repositorio.
3. Guarda las referencias a estos blobs en el área de staging.
4. Finalmente, genera un commit que referencia a estos blobs y a su commit padre.

Cuando creas una rama, estás creando una nueva línea de desarrollo que parte de un commit existente. Git hace esto de forma rápida y eficiente, permitiendo múltiples ramas sin afectar el rendimiento.

Las ramas permiten:
- Desarrollar nuevas funcionalidades de forma aislada,
- Corregir errores sin afectar el trabajo principal,
- Unir cambios fácilmente con `merge` o `rebase`.

---

## 5.2🌿 Crear y gestionar ramas en Git

#### 📌 Crear una rama (`git branch`)
Para crear una nueva rama en Git, simplemente usa:

```bash
git branch nombre-de-la-rama
````

Esto crea un nuevo apuntador que parte desde el commit actual, pero **no cambia** la rama activa.

>💡Importante! HEAD funciona como un apuntador que señala en qué rama estás actualmente. 

#### 🔍 Ver ramas activas (`git log --decorate`)

Puedes visualizar en qué ramas se encuentra cada commit con:

```bash
git log --oneline --decorate
```

Esto añade etiquetas con los nombres de ramas o `HEAD` al lado de los commits.

#### 🔄 Cambiar de rama con `git switch`

En versiones recientes de Git, se recomienda usar `git switch` en lugar del más antiguo `git checkout` para cambiar de rama:

```bash
git switch nombre-de-la-rama
```

Esto es más claro y seguro, ya que `checkout` tenía múltiples funciones (cambiar de rama, restaurar archivos, etc.) lo que causaba confusión.

##### ⚙️ ¿Qué hace `git switch`?

* **Mueve el `HEAD`** a la rama seleccionada.
* **Actualiza los archivos** del directorio de trabajo al estado del último commit en esa rama.

> 📝 Nota: Si hay cambios sin guardar, Git puede impedir el cambio de rama para evitar conflictos o pérdida de datos.

---

## 5.3 🌿 Procedimientos Básicos: Ramificar y Fusionar

#### 🔧 Flujo de trabajo típico

1. Estás trabajando en la rama `master`.
2. Creas una nueva rama para una tarea o problema:

```bash
git checkout -b nombre-de-la-rama
````

3. Haces commits en esta rama.
4. Si surge un problema urgente:

   * Cambias de vuelta a `master`: `git checkout master`
   * Creas una rama `hotfix` y haces la corrección.
   * Fusionas `hotfix` en `master`: `git merge hotfix`
   * Borras `hotfix`: `git branch -d hotfix`
5. Vuelves a tu rama de trabajo y continúas.

#### 🔀 Fusionar cambios

* Para integrar tu trabajo en `master`:

```bash
git checkout master
git merge nombre-de-la-rama
```

* Si no hay conflictos, se fusiona automáticamente (fast-forward o merge commit).

#### ⚠️ ¿Y si hay conflictos?

* Git marcará los archivos conflictivos.
* Edita los archivos, resuelve los conflictos y guarda.
* Marca como resueltos:

```bash
git add archivo
git commit
```

* También puedes usar una herramienta visual:

```bash
git mergetool
```
> ⚠️RECOMENDACION PARA LOS CONFLICTOS⚠️ Usa VS Code u otros editores para resolver conflictos más cómodamente.

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
