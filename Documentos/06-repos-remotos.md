# 6. ☁️ Trabajo con repositorios remotos en GitHub

El trabajo con repositorios remotos en GitHub facilita la colaboración, sincronización y actualización de proyectos entre varios desarrolladores y dispositivos. 
Esta sección abarca desde los conceptos básicos hasta configuraciones avanzadas, preparándote para dominar el trabajo local y remoto en proyectos Git.

---
## 6.1 Conceptos Básicos**

  * Definición de repositorio remoto
  * Diferencias Local vs Remoto
  * Ventajas de usar remotos
  * GitHub como servicio de hosting

## 6.2 Configuración Inicial de Remotos**

  * `git remote add`
  * `git remote -v`
  * `git remote set-url`
  * `git remote remove`

## 6.3 URLs y Autenticación para Git**

  * HTTP vs SSH (sintaxis y pros/contras)
  * Tokens de Acceso Personal (PAT)
  * Claves SSH (`ssh-keygen`, agentes, registro)
  * `gh auth login` (GitHub CLI)

## 6.4 Envío de Cambios (Push)**

  * `git push origin <rama>`
  * `--set-upstream`
  * `--force` / `--force-with-lease`
  * Push de etiquetas (`--tags`)
  * Push de todas las ramas (`--all`)

## 6.5 Obtención de Cambios (Fetch & Pull)**

  * `git fetch origin`
  * `git pull origin <rama>`
  * Diferencias fetch vs pull
  * Resolución de conflictos locales

## 6.6 Ramas de Seguimiento**

  * Qué es una tracking branch
  * `git branch -vv`
  * `git branch --set-upstream-to=origin/<rama>`

## 6.7 Gestión de Múltiples Remotos**

  * `git remote add upstream <URL>`
  * `git fetch upstream` / `git pull upstream <rama>`
  * `git remote rename`
### 6.1 🔄 Clonar y conectar repositorios

#### `git clone`

Copia un repositorio remoto en tu máquina local.

```bash
git clone https://github.com/usuario/repositorio.git
```

> Clona todo el historial, ramas y archivos.

---

#### `git remote`

Conecta tu repositorio local con uno remoto.

```bash
git remote add origin https://github.com/usuario/repositorio.git
git remote -v  # Verifica conexiones remotas
```

---

#### `git push`, `git fetch`, `git pull`

| Comando     | Función                                          |
| ----------- | ------------------------------------------------ |
| `git push`  | Envía cambios locales al repositorio remoto      |
| `git fetch` | Trae actualizaciones del remoto, sin integrarlas |
| `git pull`  | Trae e integra (fetch + merge)                   |

```bash
git push origin main       # Sube cambios
git fetch origin           # Trae últimos cambios sin aplicar
git pull origin main       # Trae y fusiona
```

---

### 6.2 🚚 Migrar un repositorio local a GitHub

#### Caso: Tengo un proyecto local y quiero subirlo a GitHub

```bash
git init
git add .
git commit -m "Primer commit"
git remote add origin https://github.com/usuario/repositorio.git
git push -u origin main
```

> 💡 Usa `-u` para establecer el seguimiento remoto predeterminado.

---

#### Migración avanzada: espejo de repositorio

```bash
git clone --mirror https://github.com/otro/origen.git
cd origen.git
git push --mirror https://github.com/miusuario/nuevo-repo.git
```

> Clona TODO, incluidas todas las ramas y etiquetas.

---

### 6.3 🏢 Organizaciones, equipos y permisos

#### GitHub permite agrupar usuarios y proyectos en **organizaciones**:

* **Repositorios privados o públicos**
* **Equipos** con roles: lectura, escritura, admin
* Control de **permisos por rama y entorno**
* **Protected branches**: solo ciertos usuarios pueden hacer `merge`

> Ideal para proyectos empresariales, educativos o colaborativos.

---

### 6.4 🗃️ Monorepos y gestión de permisos avanzada

Un **monorepo** es un solo repositorio que contiene múltiples módulos o proyectos.

**Ventajas:**

* Gestión unificada del código.
* Facilita refactors entre proyectos.
* Configuración compartida (CI/CD, linting).

**Desafíos:**

* Tamaño y rendimiento.
* Coordinación entre equipos.

---

### 6.5 🛠 Buenas prácticas para trabajo remoto

* Sincroniza con `git pull` frecuentemente.
* Usa ramas con nombres claros.
* No forces `git push --force` en ramas compartidas.
* Protege ramas críticas (`main`, `develop`).
* Usa Pull Requests para revisión y calidad.

---

### 6.6 🧪 Ejercicio práctico sugerido

**Escenario:**
Tienes un proyecto local. Súbelo a GitHub y trabaja con otro compañero simulando una colaboración básica.

**Pasos clave:**

1. Crear repo en GitHub.
2. Subir proyecto con `git remote add` y `push`.
3. Clonar desde otro equipo o usuario.
4. Usar `pull`, `push` y `branch` para colaborar.

---

### 6.7 📚 Recursos recomendados

* [Guía oficial de GitHub: "Hello World"](https://guides.github.com/activities/hello-world/)
* [Documentación de git-scm sobre remotos](https://git-scm.com/book/en/v2/Git-Basics-Working-with-Remotes)
* Video: ["Git Remotes Simplified"](https://www.youtube.com/watch?v=9D1x7-2FmTA)
* GitHub CLI (`gh repo clone`, `gh repo create`, etc.)

---
