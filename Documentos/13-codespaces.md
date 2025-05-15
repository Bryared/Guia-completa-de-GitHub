# 13. 💻 Entornos de desarrollo en la nube

GitHub ofrece soluciones potentes para programar desde cualquier lugar, sin necesidad de instalar herramientas localmente. Dos herramientas clave son **GitHub Codespaces** y **GitHub.dev**.

---

### 13.1 ☁️ ¿Qué es un entorno de desarrollo en la nube?

Un entorno de desarrollo en la nube es una plataforma que permite:

* Escribir, ejecutar y depurar código en un navegador.
* Evitar configuraciones locales complicadas.
* Integrarse con GitHub directamente.

---

### 13.2 🧪 GitHub.dev (editor en el navegador)

> Accede escribiendo `.dev` después de `github` en cualquier repo.

Ejemplo:
`https://github.dev/usuario/repositorio`

🔹 Características:

* Basado en **VS Code Web**
* No ejecuta código ni tiene terminal
* Ideal para navegación rápida, edición de archivos, y creación de PRs

---

### 13.3 🚀 GitHub Codespaces (entorno completo en la nube)

> Un contenedor de desarrollo en la nube, totalmente funcional, con editor, terminal, extensiones, etc.

#### ✅ Características

* Basado en **VS Code en la nube**
* Ejecuta código, instala dependencias, ejecuta pruebas
* Configurable con `devcontainer.json`
* Usa tu propia configuración de VS Code
* Compatible con GitHub Actions
  
### 🧠 ¿Cuándo usar Codespaces?

* Cuando no quieres instalar dependencias en tu máquina local
* Al contribuir rápidamente a un nuevo proyecto
* Para trabajar desde dispositivos sin mucha potencia
* Para garantizar entornos homogéneos entre todos los miembros del equipo
  
### 🛠️ ¿Cómo crear un Codespace?

#### 1. Ve al repositorio deseado en GitHub
   * ![image](https://github.com/user-attachments/assets/25028233-94f5-4cf4-aa7f-430cc52b5a4b)
#### 2. Haz clic en el botón **Code**
   * ![image](https://github.com/user-attachments/assets/6e545e88-b0a1-4f11-81b2-ac768547ce27)
#### 3. Selecciona la pestaña **Codespaces**
   * ![image](https://github.com/user-attachments/assets/2c37a749-6fe3-4746-b58d-dca67c3667a4)
#### 4. Haz clic en **Create codespace on [rama]**
   * ![image](https://github.com/user-attachments/assets/2cfe79e3-45ec-4ed1-a81f-07737eb250f2)
#### 5. Espera a que el entorno se configure automáticamente

> ⏱️ *El entorno estará listo en segundos, sin necesidad de configurar nada localmente.*

---
---

### 13.4 🧩 Configurar con `devcontainer.json`

Dentro de `.devcontainer/` puedes personalizar tu entorno:

```json
{
  "name": "Mi entorno Python",
  "image": "mcr.microsoft.com/devcontainers/python:3.10",
  "features": {
    "ghcr.io/devcontainers/features/github-cli:1": {}
  },
  "postCreateCommand": "pip install -r requirements.txt"
}
```

🔹 Puedes configurar:

* Lenguajes y herramientas
* Extensiones de VS Code
* Comandos a ejecutar al iniciar

---

### 13.5 🧠 Casos de uso recomendados

* Clases o talleres de programación sin instalar nada local
* Entornos reproducibles para equipos grandes
* Contribución rápida a proyectos open-source
* Preparación de pruebas, challenges o entrevistas técnicas

---

### 13.6 📊 Limitaciones y consideraciones

| Elemento        | GitHub.dev | Codespaces                  |
| --------------- | ---------- | --------------------------- |
| Ejecutar código | ❌          | ✅                           |
| Terminal        | ❌          | ✅                           |
| Personalizable  | ❌          | ✅ (devcontainer)            |
| Gratuito        | ✅          | ✅\* (con límites de tiempo) |

---

### 13.7 🛡️ Seguridad y privacidad

* Codespaces corre en contenedores aislados.
* Puedes proteger tus secretos usando GitHub Actions.
* Puedes borrar el codespace cuando termines.

---

### 13.8 🧪 Consejos avanzados

* Usa `dotfiles` personalizados para tu shell/editor.
* Define múltiples configuraciones para proyectos diferentes.
* Automatiza tareas con scripts en el `postCreateCommand`.

---
