# 6. ☁️ Trabajo con repositorios remotos en GitHub

El trabajo con repositorios remotos en GitHub facilita la colaboración, sincronización y actualización de proyectos entre varios desarrolladores y dispositivos. 
Esta sección abarca desde los conceptos básicos hasta configuraciones avanzadas, preparándote para dominar el trabajo local y remoto en proyectos Git.

---
## 6.1 🔄 Conceptos Básicos

Comprenderás qué es un repositorio remoto y cómo se diferencia del local.

### ¿Qué es un repositorio remoto?**
  Es una versión del repositorio Git alojada en la nube, generalmente en servicios como GitHub. Permite sincronizar, colaborar y respaldar proyectos.

### Diferencias entre repositorio local y remoto**

  * *Local:* Está en tu computadora.
  * *Remoto:* Está en servidores como GitHub.

### Ventajas de usar repositorios remotos**

  * Copia de seguridad
  * Colaboración
  * Automatización y despliegue

### GitHub como servicio de hosting Git**
  Es el proveedor más popular para alojar repos y colaborar.

### 🏗️ Crear un repositorio remoto en GitHub
Desde la interfaz web de GitHub.

Desde la terminal con gh repo create.

Inicialización con README, .gitignore, licencia.

---

## 6.2 ⚖️ Configuración Inicial de Remotos

Aprenderás a asociar, cambiar o eliminar remotos en tu repositorio local.

* `git remote add origin <URL>`: Asocia el repositorio local con un remoto.
* `git remote -v`: Lista los remotos configurados.
* `git remote set-url origin <nueva-URL>`: Cambia la URL del remoto.
* `git remote remove origin`: Elimina la asociación con un remoto.

### 🔗 Vincular un repositorio local a uno remoto
git remote add origin <URL>

Confirmar con git remote -v.

Subir por primera vez con git push -u origin main

---

## 6.3 🔑 URLs y Autenticación

Aprenderás a autenticarte correctamente para trabajar con repos remotos vía HTTPS o SSH.

### HTTP vs SSH:

  * HTTP: Simple pero requiere autenticarse cada vez o usar tokens.
  * SSH: Requiere configurar claves, pero evita pedir contraseñas.

### Tokens de Acceso Personal (PAT):

  * Generar desde GitHub > Settings > Developer Settings
  * Se usan como contraseña al usar HTTP

### Claves SSH:

  * Crear: `ssh-keygen -t ed25519 -C "tu@email.com"`
  * Agregar al agente y a GitHub

### GitHub CLI (gh):

  * Autenticación rápida: `gh auth login`

### 🔐 Autenticación con GitHub
Configurar Personal Access Tokens (HTTPS).

Uso de claves SSH para conexión segura.

Almacenamiento de credenciales (credential helper).

---

## 6.4 ➡️ Enviar Cambios al Remoto (Push)

Enviarás tus cambios locales a GitHub con diferentes estrategias.

* `git push origin main`: Enviar la rama actual al remoto.
* `git push --set-upstream origin <rama>`: Establecer seguimiento.
* `git push --force` y `--force-with-lease`: Para sobrescribir historial remoto (usarlo con precaución).
* `git push origin v1.0`: Subir etiquetas.
* `git push --tags`: Subir todas las etiquetas.
* `git push --all origin`: Subir todas las ramas locales.

### 6.4 ⬆️ Subir cambios al repositorio remoto
git push, git push --set-upstream.

Subir ramas nuevas y etiquetas (git push origin nombre-rama).

Ver qué ramas están sincronizadas con git branch -vv.

---

## 6.5 💾 Obtener Cambios del Remoto (Fetch & Pull)

Descargarás y fusionarás cambios del repositorio remoto en tu copia local.

* `git fetch origin`: Trae cambios sin fusionar.
* `git pull origin main`: Trae y fusiona cambios.

### **Diferencias:**

  * `fetch`: Solo descarga.
  * `pull`: Descarga y aplica.
  * fetch vs pull

### **Resolución de conflictos locales:**
  * Usar `git mergetool` o resolución manual.

## 6.5 ⬇️ Descargar cambios desde GitHub
git fetch: traer sin mezclar.

git pull: traer y fusionar automáticamente.

Detectar y resolver conflictos en pull.

---

## 6.6 🔹 Ramas de Seguimiento (Tracking Branches)

Establecerás y administrarás relaciones entre ramas locales y remotas.

  * Qué es una tracking branch

* Permiten a una rama local rastrear su equivalente remoto.
* `git branch -vv`: Muestra información de seguimiento.
* `git branch --set-upstream-to=origin/<rama>`: Establece seguimient

##6.6 🧭 Configurar ramas de seguimiento (tracking)
Entender upstream y cómo Git sabe qué rama remota seguir.

Cambiar o definir upstream con git branch --set-upstream-to.

---
## 6.7 🪜 Gestión de Múltiples Remotos

Trabajarás con más de un repositorio remoto (ej. origin y upstream).

* Casos comunes: fork, espejo, upstream.
* `git remote add upstream <URL>`: Añadir otro remoto.
* `git fetch upstream` y `git pull upstream main`: Obtener cambios del repo original.
* `git push origin <rama>`: Subir cambios a tu fork.
* `git remote rename origin github`: Renombrar remoto.

## 6.7 🌐 Trabajar con múltiples remotos
origin vs. upstream: escenarios típicos con forks.

Añadir y gestionar múltiples remotos (git remote add, remove, rename).

Obtener y comparar ramas de remotos distintos.

---

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
