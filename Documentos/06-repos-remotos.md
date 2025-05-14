# 6. ☁️ Trabajo con repositorios remotos en GitHub

El trabajo con repositorios remotos en GitHub facilita la colaboración, sincronización y actualización de proyectos entre varios desarrolladores y dispositivos. 
Esta sección abarca desde los conceptos básicos hasta configuraciones avanzadas, preparándote para dominar el trabajo local y remoto en proyectos Git.

---
## 6.1 🔄 Conceptos Básicos

Comprenderás qué es un repositorio remoto y cómo se diferencia del local.

### ¿Qué es un repositorio remoto?
  Es una versión del repositorio Git alojada en la nube, generalmente en servicios como GitHub. Permite sincronizar, colaborar y respaldar proyectos.

> 💡 Piensa en el repositorio remoto como una “fuente oficial” del proyecto que está siempre disponible online.


### 🖥️ Repositorio Local vs Repositorio Remoto

| Característica | Repositorio Local                  | Repositorio Remoto                          |
| -------------- | ---------------------------------- | ------------------------------------------- |
| Ubicación      | En tu computadora                  | En la nube (GitHub, GitLab, etc.)           |
| Accesibilidad  | Solo tú puedes acceder localmente  | Accesible por múltiples colaboradores       |
| Velocidad      | Operaciones rápidas y sin conexión | Necesita conexión para sincronizar          |
| Propósito      | Desarrollo individual              | Colaboración, respaldo, despliegue continuo |


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


### 🔧 Comandos Clave para Gestionar Remotos

| Comando                                | Descripción                                    |
| -------------------------------------- | ---------------------------------------------- |
| `git remote add origin <URL>`          | Asocia tu repo local con un repositorio remoto |
| `git remote -v`                        | Muestra los remotos configurados y sus URLs    |
| `git remote set-url origin <nuevaURL>` | Cambia la URL de un remoto existente           |
| `git remote remove origin`             | Elimina la referencia a un remoto              |


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

#### 📤 Subir tu proyecto por primera vez

Usa `git push` para enviar tu proyecto local al repositorio remoto:

```bash
git push -u origin main
```

* `-u`: Establece `origin/main` como la rama remota predeterminada.
* A partir de ahora, puedes usar simplemente `git push` y `git pull`.

> 💡 Asegúrate de que tu rama principal se llame `main` o cambia el nombre con `git branch -M main` si es necesario.

#### 🔁 Cambiar la URL del remoto

Si por alguna razón necesitas cambiar la dirección del remoto (por ejemplo, cambiaste de HTTP a SSH):

```bash
git remote set-url origin git@github.com:usuario/repositorio.git
```


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

### 🔀 Formas de conexión con GitHub
Existen tres formas principales de conexión entre tu repositorio local y GitHub:

| Método          | Ventajas                 | Desventajas                          | Ideal para                          |
| --------------- | ------------------------ | ------------------------------------ | ----------------------------------- |
| **HTTPS + PAT** | Fácil de configurar      | Requiere ingresar o guardar el token | Uso ocasional o entornos simples    |
| **SSH**         | Seguro y sin contraseñas | Necesita configuración inicial       | Desarrollo frecuente y profesional  |
| **GitHub CLI**  | Rápido y automatizado    | Requiere tener instalada la CLI `gh` | Automatización y experiencia fluida |

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


### 🖥️ Almacenamiento de Credenciales

Para no tener que ingresar tu PAT o clave cada vez:

* En HTTPS: Usa el "Credential Helper" de Git:

```bash
git config --global credential.helper cache  # Almacena temporalmente
git config --global credential.helper store  # Almacena indefinidamente
```

> ⚠️ No recomendado almacenar tokens indefinidamente en máquinas compartidas.


### ⚡ Alternativa rápida: GitHub CLI
La herramienta de línea de comandos de GitHub (`gh`) permite iniciar sesión y autenticarse fácilmente.
```bash
gh auth login
```
Te guía para autenticarte y configura Git automáticamente. Ideal para agilizar la configuración inicial.

---

## 6.4 ➡️ Enviar Cambios al Remoto (Push)

Aprenderás a subir tus cambios locales a GitHub configurando correctamente el seguimiento entre ramas.


### 🔁 ¿Qué significa hacer `push`?

Hacer `git push` es **enviar los commits de tu repositorio local al remoto**, como GitHub. Es un paso fundamental para:

* Compartir tu trabajo con otros.
* Respaldar tu código en la nube.
* Activar automatizaciones (como CI/CD).


### 📤 Primer Push (inicial)

Cuando creas un repositorio en GitHub, generalmente está vacío. Para subir tu proyecto local:

```bash
git push -u origin main
```

> `-u` (o `--set-upstream`) establece una relación de seguimiento entre tu rama local y la rama remota. Así podrás usar simplemente `git push` en el futuro.

### 🔁 Comandos de push frecuentes

| Comando                            | Descripción                                                |
| ---------------------------------- | ---------------------------------------------------------- |
| `git push origin main`             | Sube la rama `main` al actual remoto llamado `origin`      |
| `git push origin main`             | Enviar la rama actual al remoto.                           |
| `git push --set-upstream origin <rama>`| Establecer seguimiento.|
| `git push -u origin feature/login` | Sube una nueva rama y configura seguimiento                |
| `git push --force`                 | Fuerza la subida, sobrescribiendo el historial remoto (⚠️) |
| `git push --force-with-lease`      | Fuerza con precaución (mejor práctica si necesitas forzar) |
| `git push`                         | Sube los cambios a la rama remota ya configurada           |
| `git push --tags`                  | Sube todas las etiquetas (tags) locales                    |
| `git push origin v1.0`             | Sube solo la etiqueta `v1.0`                               |
| `git push --all origin`            | Sube todas las ramas locales al remoto                     |

> ⚠️ **Evita usar `--force` en ramas compartidas**
> Puede sobrescribir el trabajo de otros desarrolladores. Solo úsalo cuando **estés seguro de lo que haces**, o en ramas personales.

**Alternativa segura:** `--force-with-lease`
Este comando **verifica primero** que nadie haya subido cambios al remoto antes de sobrescribirlo.

### 👁️ Ver estado de ramas y seguimiento

```bash
git branch -vv
```

Muestra las ramas locales y si están vinculadas a ramas remotas (tracking branches). Muy útil para asegurarte de que estás trabajando con la rama correcta.

---

### 6.4 ⬆️ Subir cambios al repositorio remoto
git push, git push --set-upstream.

Subir ramas nuevas y etiquetas (git push origin nombre-rama).

Ver qué ramas están sincronizadas con git branch -vv.

---

## 6.5 💾 Obtener Cambios del Remoto (Fetch & Pull)

Descargarás y fusionarás actualizaciones desde el repositorio remoto hacia tu copia local usando `git fetch` y `git pull`.

### 🔄 ¿Por qué es importante traer cambios?

Cuando trabajas en equipo (o desde distintos dispositivos), otros pueden estar subiendo cambios. Para evitar conflictos o sobrescribir trabajo ajeno, debes:

* **Consultar el estado remoto** con `fetch`.
* **Fusionar los cambios** con `pull`.


### 🧩 Diferencias entre `fetch` y `pull`

| Comando     | Qué hace                                                             | Cuándo usarlo                        |
| ----------- | ---------------------------------------------------------------------| ------------------------------------ |
| `git fetch` | Descarga cambios del remoto, pero **no los aplica** a tu rama actual.| Para revisar antes de fusionar       |
| `git pull`  | Descarga **y aplica automáticamente** los cambios.                   | Para actualizar tu rama con la remota|

### 📥 Comandos esenciales

`git fetch origin`:🔹 Descarga todas las actualizaciones desde el remoto llamado `origin`, **sin fusionarlas**.

`git pull origin main`:🔹 Descarga y **fusiona** automáticamente la rama `main` desde el remoto `origin`.

`git pull`:🔹 Si ya está configurado el seguimiento (`-u`), fusiona automáticamente con la rama remota correspondiente.


### 🧨 Posibles conflictos al hacer `pull`

Si tú y otra persona modificaron las mismas líneas de código, Git **no podrá fusionar automáticamente** y te pedirá resolver los conflictos manualmente.

**Pasos para resolver un conflicto:**

1. Git marcará los archivos en conflicto con secciones especiales:

   ```plaintext
   <<<<<<< HEAD
   Tu versión
   =======
   Versión del remoto
   >>>>>>> origin/main
   ```

2. Edita el archivo para elegir qué conservar (o combinar partes).

3. Marca como resuelto:

   ```bash
   git add archivo_en_conflicto
   git commit  # Git puede crear uno automáticamente
   ```

4. Continúa tu trabajo normalmente.


### 🛠️ Herramientas para resolución de conflictos

* `git mergetool`: abre herramientas visuales como Meld o VSCode Merge.
* Editores modernos como VS Code o IntelliJ muestran automáticamente los conflictos de forma visual.

---

## 6.6 🔹 Ramas de Seguimiento (Tracking Branches)

Entender cómo Git conecta tus ramas locales con ramas remotas, para sincronizar automáticamente los cambios con `push` y `pull`.

### 🔍 ¿Qué es una *tracking branch*?

Es una rama local que **está vinculada a una rama remota**. Esto permite que Git sepa:

* A qué rama remota subir tus cambios (`push`).
* De qué rama remota bajar actualizaciones (`pull`).

📌 Por ejemplo:
Si tienes una rama local llamada `main`, y la conectas con `origin/main`, entonces `git pull` y `git push` sabrán a qué rama remota referirse sin necesidad de especificarla.


### 🧠 ¿Cuándo se configura automáticamente una *tracking branch*?

Cuando haces:

```bash
git push -u origin main
```

> La opción `-u` (o `--set-upstream`) establece la relación entre `main` local y `origin/main`.


### 🛠️ Comandos útiles

| Comando                                         | Qué hace                                                       |
| ----------------------------------------------- | -------------------------------------------------------------- |
| `git branch -vv`                                | Muestra qué ramas locales están vinculadas a remotas           |
| `git branch --set-upstream-to=origin/otra-rama` | Cambia o define la rama remota vinculada a tu rama actual      |
| `git push -u origin mi-rama`                    | Sube la rama y crea la relación de seguimiento automáticamente |
| `git status`                                    | También muestra si hay una rama remota asociada                |


### 📘 Ejemplo completo

```bash
# Crear y cambiar a una nueva rama
git checkout -b feature/login

# Subirla y establecer relación con la rama remota
git push -u origin feature/login

# Ahora puedes simplemente usar:
git pull
git push
```

### 🔄 Cambiar el seguimiento de una rama existente

```bash
git branch --set-upstream-to=origin/nueva-rama
```

> Esto es útil si renombraste ramas o cambiaste el origen del trabajo.

---

## 6.7 🌐 Gestión de múltiples remotos

En proyectos más avanzados —como forks, colaboraciones con múltiples copias del mismo repositorio o espejos de backup— puede que necesites trabajar con **más de un repositorio remoto**. En este subapartado aprenderás a agregar, renombrar y sincronizar múltiples remotos, sin entrar aún en la gestión de tareas, automatización o estrategias colaborativas complejas.

### 📌 ¿Qué es tener múltiples remotos?

Un repositorio puede estar conectado a **más de una URL remota**. Cada conexión tiene un nombre, como `origin`, `upstream`, `github`, etc.

Ejemplos comunes:

* `origin`: el repositorio principal (ej. tu fork en GitHub).
* `upstream`: el repositorio original desde el que hiciste el fork.
* `mirror`: una copia espejo para respaldo o despliegue.


### 🔧 Comandos clave para gestionar remotos adicionales

#### ➕ Añadir un segundo remoto

```bash
git remote add upstream https://github.com/usuario-original/repositorio.git
```

#### 🔁 Verificar todos los remotos configurados

```bash
git remote -v
```

#### ✏️ Renombrar un remoto existente

```bash
git remote rename origin github
```

#### ❌ Eliminar un remoto

```bash
git remote remove upstream
```


### 🔄 Sincronizar cambios desde otro remoto

Aunque `origin` sea tu repositorio principal, puedes obtener cambios del remoto `upstream` sin hacer un `merge` automáticamente.

```bash
git fetch upstream
```

Luego puedes revisar ramas, comparar o integrarlas manualmente si lo deseas.


### 🧭 Buenas prácticas

* Usa nombres descriptivos (`origin`, `upstream`, `backup`).
* Documenta en el `README` de tu proyecto la estructura de remotos si es compartido.
* Sincroniza frecuentemente para mantenerte actualizado.
* No hagas `push` a remotos que no controles directamente sin revisión previa.


### ✅ Mini resumen visual

| Acción              | Comando básico                    |
| ------------------- | --------------------------------- |
| Añadir otro remoto  | `git remote add upstream <URL>`   |
| Ver remotos         | `git remote -v`                   |
| Obtener cambios     | `git fetch upstream`              |
| Subir a otro remoto | `git push origin nombre-rama`     |
| Renombrar remoto    | `git remote rename origin github` |

---

## 6.8 📖 Clonación de Repositorios

**Clonar** un repositorio es el primer paso para trabajar con un proyecto que ya existe en GitHub. Al hacerlo, obtienes una copia completa del historial, archivos y configuración del proyecto en tu máquina local.


### 🔍 ¿Qué hace `git clone`?

El comando `git clone` copia:

* Todo el historial del proyecto (commits, ramas, etiquetas).
* La última versión de los archivos.
* La configuración remota (`origin`) para sincronizar con GitHub.

```bash
git clone https://github.com/usuario/repositorio.git
```

> Esto crea una carpeta con el contenido del repositorio y un control de versiones listo para usar.


### 🔄 Variantes útiles de clonación

#### 🔸 Clonar una rama específica

Por defecto, `git clone` trae **todas las ramas**, pero puedes traer solo una si lo necesitas:

```bash
git clone -b nombre-rama --single-branch https://github.com/usuario/repositorio.git
```

#### 🔹 Clonación superficial (shallow clone)

Ideal si solo te interesa el estado actual del proyecto y quieres ahorrar espacio:

```bash
git clone --depth 1 https://github.com/usuario/repositorio.git
```

> Solo trae el último commit y ahorra tiempo de descarga.

#### 🔍 Clonar sin historial completo + solo una rama:

```bash
git clone --depth 1 --single-branch -b main https://github.com/usuario/repositorio.git
```

### 📁 Sparse Checkout: Clonar solo partes del proyecto

Ideal para monorepos o proyectos grandes donde solo trabajas con una carpeta específica:

```bash
git clone --no-checkout https://github.com/usuario/repositorio.git
cd repositorio
git sparse-checkout init --cone
git sparse-checkout set ruta/a/carpeta
```

> Solo se descarga el contenido de esa carpeta, no todo el repositorio.

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
### ❗ Buenas prácticas

✅ Siempre verifica las ramas vinculadas con:

```bash
git branch -vv
```

✅ Usa nombres claros y coherentes para tus ramas locales y remotas.

✅ Evita usar `--force` en ramas con seguimiento sin estar seguro, ya que puedes sobrescribir trabajo remoto.


### 🧪 Ejercicio práctico sugerido

1. Crea una nueva rama:

   ```bash
   git checkout -b feature/contact-form
   ```

2. Sube y configura la relación remota:

   ```bash
   git push -u origin feature/contact-form
   ```

3. Confirma con:

   ```bash
   git branch -vv
   ```

---

### 6.16 📚 Recursos recomendados

* [Guía oficial de GitHub: "Hello World"](https://guides.github.com/activities/hello-world/)
* [Documentación de git-scm sobre remotos](https://git-scm.com/book/en/v2/Git-Basics-Working-with-Remotes)
* Video: ["Git Remotes Simplified"](https://www.youtube.com/watch?v=9D1x7-2FmTA)
* GitHub CLI (`gh repo clone`, `gh repo create`, etc.)

---
