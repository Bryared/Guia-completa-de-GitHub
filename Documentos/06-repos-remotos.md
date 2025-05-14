# 6. ☁️ Trabajo con repositorios remotos en GitHub

El trabajo con repositorios remotos en GitHub facilita la colaboración, sincronización y actualización de proyectos entre varios desarrolladores y dispositivos. 
Esta sección abarca desde los conceptos básicos hasta configuraciones avanzadas, preparándote para dominar el trabajo local y remoto en proyectos Git.

---
## 6.1 🔄 Conceptos Básicos

Comprenderás qué es un repositorio remoto y cómo se diferencia del local.

### ¿Qué es un repositorio remoto?**
  Es una versión del repositorio Git alojada en la nube, generalmente en servicios como GitHub. Permite sincronizar, colaborar y respaldar proyectos.

> 💡 Piensa en el repositorio remoto como una “fuente oficial” del proyecto que está siempre disponible online.

---

### 🖥️ Repositorio Local vs Repositorio Remoto

| Característica | Repositorio Local                  | Repositorio Remoto                          |
| -------------- | ---------------------------------- | ------------------------------------------- |
| Ubicación      | En tu computadora                  | En la nube (GitHub, GitLab, etc.)           |
| Accesibilidad  | Solo tú puedes acceder localmente  | Accesible por múltiples colaboradores       |
| Velocidad      | Operaciones rápidas y sin conexión | Necesita conexión para sincronizar          |
| Propósito      | Desarrollo individual              | Colaboración, respaldo, despliegue continuo |

---

### ✅ Ventajas de Usar Repositorios Remotos

1. **Copia de seguridad en la nube**
2. **Colaboración en equipo desde distintos lugares**
3. **Integración con herramientas CI/CD** (automatización, despliegue)
4. **Historial centralizado de cambios**
5. **Control de versiones y revisión vía Pull Requests**


## ☁️ GitHub como servicio de hosting Git

**GitHub** es el proveedor de repositorios Git más utilizado a nivel mundial. Permite:

* Crear y administrar repositorios fácilmente.
* Control de permisos y visibilidad (público o privado).
* Colaborar mediante ramas, issues y pull requests.
* Integración con GitHub Actions, Projects, Pages y más.

> 🏆 Es la plataforma ideal para principiantes y profesionales por su facilidad de uso y potencia.

---

## 🏗️ Crear un repositorio remoto en GitHub
#### 🖱️ Opción 1: Desde la Interfaz Web

1. Ve a [https://github.com](https://github.com).
2. Haz clic en **“New Repository”**.
3. Asigna un **nombre** y una **descripción**.
4. Puedes incluir archivos comunes como:

   * `✔️` **Add a README** → Presentación del proyecto.
   * `✔️` **.gitignore** → Archivos que Git debe ignorar.
   * `✔️` **License** → Tipo de licencia que rige tu proyecto.
5. Haz clic en **Create Repository**.

> 💡 Si eliges agregar README, .gitignore y licencia, tu repositorio ya estará inicializado con contenido.

---

#### 💻 Opción 2: Desde la Terminal con GitHub CLI

```bash
gh repo create nombre-del-repo
```

Se te preguntará si deseas crear el repositorio en GitHub y enlazarlo automáticamente con tu repositorio local.


---

## 6.2 ⚖️ Configuración Inicial de Remotos

Aprenderás cómo vincular tu repositorio local con un repositorio remoto en GitHub, cómo verificar esa conexión y cómo modificarla si es necesario.

### 🔗 ¿Qué es un "remote"?

En Git, un **remote** es simplemente un **alias** que representa la URL de un repositorio remoto (por ejemplo, en GitHub). Esto te permite sincronizar cambios entre tu proyecto local y ese repositorio remoto.

> 📌 El remote más común se llama `origin`, y apunta al repositorio principal de trabajo.

---

### 🔧 Comandos Clave para Gestionar Remotos

| Comando                                | Descripción                                    |
| -------------------------------------- | ---------------------------------------------- |
| `git remote add origin <URL>`          | Asocia tu repo local con un repositorio remoto |
| `git remote -v`                        | Muestra los remotos configurados y sus URLs    |
| `git remote set-url origin <nuevaURL>` | Cambia la URL de un remoto existente           |
| `git remote remove origin`             | Elimina la referencia a un remoto              |

---

### 🔗 Vincular un repositorio local a uno remoto (GitHub)
#### 📁 Caso: Ya tienes un proyecto local iniciado con Git

```bash
git init
git add .
git commit -m "Primer commit"
```

##### 🔗 Paso 1: Añadir el remoto

```bash
git remote add origin https://github.com/usuario/repositorio.git
```

> 💡 Esto no sube nada todavía, solo establece la conexión con GitHub.

##### 🔍 Paso 2: Verificar la conexión

```bash
git remote -v
```

Salida esperada:

```
origin  https://github.com/usuario/repositorio.git (fetch)
origin  https://github.com/usuario/repositorio.git (push)
```

---

#### 📤 Subir tu proyecto por primera vez

Usa `git push` para enviar tu proyecto local al repositorio remoto:

```bash
git push -u origin main
```

* `-u`: Establece `origin/main` como la rama remota predeterminada.
* A partir de ahora, puedes usar simplemente `git push` y `git pull`.

> 💡 Asegúrate de que tu rama principal se llame `main` o cambia el nombre con `git branch -M main` si es necesario.

---

#### 🔁 Cambiar la URL del remoto

Si por alguna razón necesitas cambiar la dirección del remoto (por ejemplo, cambiaste de HTTP a SSH):

```bash
git remote set-url origin git@github.com:usuario/repositorio.git
```

---

#### ❌ Eliminar el remoto

```bash
git remote remove origin
```

Esto **no borra** el repositorio en GitHub, solo elimina la conexión local.

---

## 6.3 🔑 URLs y Autenticación

Aprenderás a autenticarte correctamente para trabajar con repos remotos vía HTTPS o SSH.

### 🔗 ¿Por qué necesitas autenticarte?

Cada vez que intentas **subir (push)** o **bajar (pull/fetch)** cambios desde un repositorio privado (o incluso público si usas comandos con privilegios), Git necesita verificar **quién eres** y si tienes **permiso para hacerlo**.

### HTTP vs SSH:

  * HTTP: Simple pero requiere autenticarse cada vez o usar tokens.
  * SSH: Requiere configurar claves, pero evita pedir contraseñas.

### 🔒 HTTPS con Tokens de Acceso Personal (PAT)
HTTPS: "Hypertext Transfer Protocol Secure"

GitHub **ya no permite usar tu contraseña** en comandos Git vía HTTPS. En su lugar, debes usar un **Token de Acceso Personal** como contraseña.

#### 🛠️ Cómo generar un PAT:
1. Generar desde GitHub: [GitHub > Settings > Tokens](https://github.com/settings/tokens). 
2. Clic en **"Generate new token"**
3. Define:
   * Nombre
   * Caducidad (recomendado)
   * Permisos necesarios (repo, workflow, etc.)
4. Copia y guarda tu token (¡no podrás verlo de nuevo!)
    
>  Usa este token como si fuera tu contraseña cuando Git te lo pida al usar HTTPS.

### 🔐 SSH: Claves Públicas y Privadas
SSH (Secure Shell) es el método más robusto. Una vez configurado, **no tendrás que escribir tu usuario ni contraseña** al interactuar con GitHub.

#### 🧰 Pasos para usar SSH:
#### 1. Crear: una clave SSH (si no tienes una)
```bash
ssh-keygen -t ed25519 -C "tu@email.com"
```
> Presiona Enter en todos los pasos para aceptar los valores por defecto.

#### 2. Agregar la clave al agente SSH

```bash
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_ed25519
```

#### 3. Copiar tu clave pública

```bash
cat ~/.ssh/id_ed25519.pub
```

#### 4. Pegarla en GitHub

* Ve a: `https://github.com/settings/keys`
* Clic en **"New SSH Key"**
* Pega tu clave y guarda.

#### 5. Probar conexión

```bash
ssh -T git@github.com
```

> 💡 Si ves un mensaje que dice “You’ve successfully authenticated…”, ¡todo está listo!

---

### 🖥️ Almacenamiento de Credenciales

Para no tener que ingresar tu PAT o clave cada vez:

* En HTTPS: Usa el "Credential Helper" de Git:

```bash
git config --global credential.helper cache  # Almacena temporalmente
git config --global credential.helper store  # Almacena indefinidamente
```

> ⚠️ No recomendado almacenar tokens indefinidamente en máquinas compartidas.

---

### ⚡ Alternativa rápida: GitHub CLI
La herramienta de línea de comandos de GitHub (`gh`) permite iniciar sesión y autenticarse fácilmente.
```bash
gh auth login
```
Te guía para autenticarte y configura Git automáticamente. Ideal para agilizar la configuración inicial.

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

### 6.8 🔄 Clonar y conectar repositorios
## 6.8 📖 Clonación de Repositorios

**Qué aprenderás a hacer:** Clonar repositorios con configuraciones específicas y eficiencia.

* `git clone <URL>`: Clonar un repo completo.
* `git clone -b rama --single-branch`: Solo una rama.
* `git clone --depth 1`: Clonación superficial.
* **Sparse Checkout:**

  * `git sparse-checkout init`
  * `git sparse-checkout set ruta`

---
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

### 6.9 🚚 Migrar un repositorio local a GitHub

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

### 6.10 🏢 Organizaciones, equipos y permisos

#### GitHub permite agrupar usuarios y proyectos en **organizaciones**:

* **Repositorios privados o públicos**
* **Equipos** con roles: lectura, escritura, admin
* Control de **permisos por rama y entorno**
* **Protected branches**: solo ciertos usuarios pueden hacer `merge`

> Ideal para proyectos empresariales, educativos o colaborativos.

---

### 6.11 🗃️ Monorepos y gestión de permisos avanzada

Un **monorepo** es un solo repositorio que contiene múltiples módulos o proyectos.

**Ventajas:**

* Gestión unificada del código.
* Facilita refactors entre proyectos.
* Configuración compartida (CI/CD, linting).

**Desafíos:**

* Tamaño y rendimiento.
* Coordinación entre equipos.

---

## 6.12 ⚙️ Automatización Local

Automatizarás sincronización y tareas relacionadas con Git usando hooks o scripts.

### **Git Hooks:**

  * `pre-push`, `post-merge`, etc.
  * Automatizar tareas antes/después de eventos Git.

### **Scripts de sincronización:**

  * Usar cron + bash/python para fetch automático.
(La automatización con GitHub Actions y CI/CD estará en Sección 10.)
---

## 6.13 ⚠️ Manejo de Errores Comunes

Diagnosticarás y resolverás problemas frecuentes al interactuar con repositorios remotos.

### **Permisos denegados:**

  * Revisar URL y autenticación (401, 403)
### **Historia divergente:**

  * Solución: `git push --force-with-lease`
### **Limpiar ramas remotas:**

  * `git remote prune origin`
### **Repositorio no encontrado:**

  * Revisar acceso y ortografía de la URL
(La gestión de políticas de seguridad y escaneo de vulnerabilidades en repositorios se ve en Sección 14.)
---

---

## 6.14 💡 Buenas Prácticas con Remotos

Mantendrás un flujo limpio, seguro y profesional al trabajar con repositorios remotos.

* Nombres claros para remotos: `origin`, `upstream`, `mirror`.
* Sincronizar con frecuencia (`git fetch`, `pull`).
* Evitar `--force` en ramas compartidas.
* Rotar tokens y usar passphrase en SSH.
* Documentar remotos en el README del proyecto.

### 6.5 🛠 Buenas prácticas para trabajo remoto

* Sincroniza con `git pull` frecuentemente.
* Usa ramas con nombres claros.
* No forces `git push --force` en ramas compartidas.
* Protege ramas críticas (`main`, `develop`).
* Usa Pull Requests para revisión y calidad.
### 📌 Buenas Prácticas

* Usa nombres claros como `origin`, `upstream`, `github`, etc.
* Revisa siempre tu conexión antes de hacer `push`.
* Usa `git remote -v` frecuentemente para verificar las URLs correctas.
* Si colaboras con forks, puedes agregar múltiples remotos (verás esto en el punto 6.7).

---
---

### 6.15 🧪 Ejercicio práctico sugerido

**Escenario:**
Tienes un proyecto local. Súbelo a GitHub y trabaja con otro compañero simulando una colaboración básica.

**Pasos clave:**

1. Crear repo en GitHub.
2. Subir proyecto con `git remote add` y `push`.
3. Clonar desde otro equipo o usuario.
4. Usar `pull`, `push` y `branch` para colaborar.

## 6.12 ✍️ Ejercicios Prácticos

1. Crea un repositorio local y enlázalo con un remoto.
2. Sube cambios a GitHub usando `push` y `set-upstream`.
3. Clona un repo con `--depth 1` y configura sparse-checkout.
4. Automatiza un fetch diario usando `cron` o un hook.
5. Simula conflicto y resuélvelo tras un `pull`.
6. Usa `origin` y `upstream` en un flujo de sincronización.

---

### 6.16 📚 Recursos recomendados

* [Guía oficial de GitHub: "Hello World"](https://guides.github.com/activities/hello-world/)
* [Documentación de git-scm sobre remotos](https://git-scm.com/book/en/v2/Git-Basics-Working-with-Remotes)
* Video: ["Git Remotes Simplified"](https://www.youtube.com/watch?v=9D1x7-2FmTA)
* GitHub CLI (`gh repo clone`, `gh repo create`, etc.)

---
