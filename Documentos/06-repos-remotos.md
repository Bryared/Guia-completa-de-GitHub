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

## 6.9 🚚 Migrar un repositorio local a GitHub

### 🎯 Objetivo

Aprenderás cómo subir un proyecto que ya tienes en tu máquina a un repositorio remoto en GitHub, desde lo más básico hasta migraciones avanzadas como espejos.


### 🧱 Caso básico: subir un proyecto local a GitHub

Pasos típicos:

```bash
git init                           # Inicializar repositorio local
git add .                          # Agregar todos los archivos
git commit -m "Primer commit"      # Crear un commit inicial
git remote add origin https://github.com/usuario/repositorio.git
git push -u origin main            # Subir la rama principal
```

🔹 Usa `-u` para establecer una relación de seguimiento entre `main` local y remoto.


### 🪞 Caso avanzado: migrar un repositorio como espejo

Ideal para copiar absolutamente todo (ramas, etiquetas, hooks, etc.)

```bash
git clone --mirror https://github.com/original/repo.git
cd repo.git
git push --mirror https://github.com/usuario/nuevo-repo.git
```

✔️ Esto clona y replica absolutamente todos los datos del repositorio original.

---

## 6.10 🏢 Organizaciones, Equipos y Permisos en GitHub

Entender cómo GitHub permite colaborar a escala con múltiples usuarios y repositorios a través de organizaciones.

### 👥 ¿Qué es una organización en GitHub?

Una **organización** agrupa usuarios y repositorios bajo una sola entidad colaborativa.

**Ventajas:**

* Centralización de configuración, permisos y facturación.
* Control granular por repositorio, rama o entorno.
* Ideal para equipos, instituciones educativas o empresas.

### 🛡️ Gestión de equipos y roles

Roles predefinidos:

| Rol      | Permisos principales                          |
| -------- | --------------------------------------------- |
| Read     | Solo lectura                                  |
| Triage   | Clasifica issues/pull requests                |
| Write    | Lectura + escritura                           |
| Maintain | Administración sin acceso completo            |
| Admin    | Acceso completo, incluido control de permisos |


### 🔐 Permisos avanzados

* **Protected Branches**: solo ciertas personas pueden hacer `push` o `merge`.
* **Required reviews**: obligar revisiones antes de `merge`.
* **Entornos protegidos**: restringir despliegues automatizados.

> Estas configuraciones complementan y refuerzan la seguridad del trabajo con repositorios remotos.

---

## 6.11 🗃️ Monorepos y gestión de permisos avanzada

Dominarás estrategias estructurales avanzadas para manejar múltiples proyectos dentro de un solo repositorio remoto.


### 🧩 ¿Qué es un monorepo?

Un **monorepo** contiene múltiples proyectos, módulos o paquetes dentro de un solo repositorio Git.


### ✅ Ventajas:

* **Gestión centralizada** del código y configuración.
* Refactorizaciones cruzadas más sencillas.
* Configuración común para CI/CD, linters, etc.

### ⚠️ Desafíos:

* Repositorios pesados, especialmente al clonar (`git clone`).
* Requiere herramientas y convenciones de organización.
* Necesidad de configuración eficiente (ej. `sparse-checkout`).


### 🔐 Permisos por carpeta (con GitHub Teams)

Aunque GitHub **no permite permisos por carpeta de forma nativa**, puedes:

* Usar **repositorios separados** y un script para mantener sincronización.
* Aplicar convenciones y herramientas como `CODEOWNERS`.

---

## 6.12 ⚙️ Automatización Local con Git

Automatizar tareas relacionadas con la sincronización con remotos, sin depender de GitHub Actions.


### 🔁 Git Hooks

Permiten ejecutar scripts automáticamente antes o después de comandos Git.

| Hook         | Descripción                                        |
| ------------ | -------------------------------------------------- |
| `pre-push`   | Antes de hacer `git push`                          |
| `post-merge` | Después de integrar cambios (`git merge` o `pull`) |
| `commit-msg` | Validar el mensaje de commit                       |

📁 Ubicación: `.git/hooks/`

> Cada hook es un script ejecutable. Se deben renombrar quitando `.sample`.


### 🧪 Ejemplo: Validar antes de hacer push

Archivo `.git/hooks/pre-push`:

```bash
#!/bin/bash
echo "¿Has corrido los tests? (s/n)"
read respuesta
[ "$respuesta" = "s" ] || exit 1
```


### 🕒 Sincronización automática con `cron`

Archivo `cron` (Linux/macOS):

```cron
0 * * * * cd /ruta/al/repo && git fetch origin >> /tmp/fetch.log
```

> Realiza un `git fetch` cada hora y guarda el log.


### 🔄 Comparación con GitHub Actions

| Automatización | Contexto                     |
| -------------- | ---------------------------- |
| Git Hooks      | Local, orientado a usuario   |
| Cron + Scripts | Local, automatización pasiva |
| GitHub Actions | Remota, automatización CI/CD |

---

## 6.13 ⚠️ Manejo de Errores Comunes en Repos Remotos

Aprenderás a diagnosticar y resolver los errores más frecuentes al trabajar con repositorios remotos:

### 🚫 Permisos denegados (`403`, `401`)

* Verifica tus credenciales (token expirado o sin permisos).
* Asegúrate de usar HTTPS o SSH correctamente.
* Usa `git remote -v` para confirmar la URL del repositorio.

### 🔀 Historia divergente

* Ocurre cuando tu historial local y remoto han cambiado por separado.
* Solución:

  ```bash
  git push --force-with-lease
  ```

  ⚠️ Úsalo con precaución y solo si sabes lo que haces.

### 📭 Repositorio no encontrado

* Verifica que la URL esté bien escrita.
* Confirma que tienes acceso (el repositorio puede ser privado o eliminado).

### 🧹 Limpiar referencias obsoletas

* Para eliminar ramas remotas que ya no existen:

  ```bash
  git remote prune origin
  ```

> 🔒 Nota: El manejo de escaneo de vulnerabilidades y políticas de seguridad se detalla en la sección 14.

---

## 6.14 💡 Buenas Prácticas Fundamentales con Repos Remotos

### 📌 Organización y nombres

* Usa nombres claros para tus remotos: `origin`, `upstream`, `mirror`.
* Verifica remotos con `git remote -v`.
* Documenta en el `README` los remotos y su función.

### 🔁 Flujo de trabajo profesional

* Sincroniza con `git fetch` regularmente.
* Usa ramas con nombres descriptivos: `feature/`, `bugfix/`, `hotfix/`.
* No uses `--force` en ramas compartidas. Si es necesario, usa `--force-with-lease`.

### 🔐 Seguridad básica

* Usa conexión SSH con passphrase.
* Protege ramas importantes (`main`, `develop`) desde GitHub.
* Rota tus tokens de acceso periódicamente.

### 🛠 Diagnóstico mínimo

* Verifica el seguimiento de ramas con:

  ```bash
  git branch -vv
  ```

* Ante errores de permisos o URLs, revisa `git remote -v` y tus credenciales.

---
## 6.14 💡 Buenas Prácticas con Repos Remotos

Asegura un flujo de trabajo limpio, seguro y profesional al interactuar con remotos.

### 📌 Convenciones recomendadas

* Usa nombres claros para tus remotos: `origin`, `upstream`, `github`, `mirror`, etc.
* Documenta en el `README` qué remotos existen y su propósito.
* Usa `git remote -v` frecuentemente para verificar URLs.
* Protege ramas críticas (`main`, `develop`) con reglas en GitHub.

### 🔐 Seguridad

* Rota tus tokens de acceso periódicamente.
* Usa `SSH` con passphrase siempre que sea posible.
* Evita usar `--force`, especialmente en ramas compartidas.
* Configura `branch protection` en GitHub para evitar sobrescribir trabajo.

### 🔁 Sincronización eficiente

* Ejecuta `git fetch` regularmente para mantener tu repositorio actualizado.
* Trabaja con ramas propias (`feature/login-page`, `hotfix/api-crash`).
* Verifica el seguimiento de ramas con:

  ```bash
  git branch -vv
  ```

---

### 6.15 🧪 Actividad

Demostrar dominio práctico sobre creación, clonación, configuración, sincronización y colaboración con repositorios remotos, incluyendo manejo de errores y buenas prácticas.

#### ✅ Pasos:

1. **Crea y sube un repositorio local** a GitHub (`git init`, `add`, `commit`, `remote add`, `push -u`).
2. **Clónalo superficialmente** desde otra cuenta con `--depth 1`.
3. **Activa `sparse-checkout`** para trabajar con una sola carpeta.
4. **Agrega múltiples remotos** (`origin`, `upstream`, `mirror`) y realiza un `push --mirror`.
5. **Protege la rama `main`** desde GitHub (revisiones requeridas, restricciones de `push`).
6. **Automatiza un `git fetch` diario** con `cron` o hooks.
7. **Simula un conflicto** en dos ramas y resuélvelo tras un `pull`.
8. **Limpia ramas remotas** con `git remote prune origin`.
9. **Verifica ramas conectadas** con `git branch -vv`.
10. **Simula y resuelve errores comunes** (permisos, URLs, upstream).
11. **Documenta todo en un `README.md`**: flujos, remotos, conflictos, seguridad.

---

### 6.16 📚 Recursos recomendados

* [Guía oficial de GitHub: "Hello World"](https://guides.github.com/activities/hello-world/)
* [Documentación de git-scm sobre remotos](https://git-scm.com/book/en/v2/Git-Basics-Working-with-Remotes)
* Video: ["Git Remotes Simplified"](https://www.youtube.com/watch?v=9D1x7-2FmTA)
* GitHub CLI (`gh repo clone`, `gh repo create`, etc.)

---
