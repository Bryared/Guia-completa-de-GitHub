# 11. 📄 Compartir código con GitHub Gists

**Gists** son una forma rápida y sencilla de compartir fragmentos de código, scripts, notas o configuraciones directamente desde GitHub. Puedes usarlos como mini-repositorios personales o públicos.

---

### 11.1 🧩 ¿Qué es un Gist?

* Es un fragmento de código versionado.
* Tiene su propio repositorio Git (puedes clonarlo, hacer commit, etc.).
* Ideal para compartir funciones, configuraciones, o ejemplos.

---

### 11.2 🌐 Tipos de Gists

| Tipo        | Acceso                                                                |
| ----------- | --------------------------------------------------------------------- |
| **Público** | Visible para todos. Aparece en búsquedas y en tu perfil.              |
| **Secreto** | Oculto del perfil y buscadores, pero accesible si se tiene el enlace. |

> ❗ Ojo: "secreto" no significa seguro. Cualquiera con el enlace puede verlo.

---

### 11.3 🛠️ Crear un Gist

1. Ir a [gist.github.com](https://gist.github.com)
2. Iniciar sesión con tu cuenta de GitHub.
3. Ingresar:

   * Un título (opcional)
   * Uno o varios archivos con nombre y contenido
   * Descripción (recomendado)
4. Elegir: público o secreto.
5. Hacer clic en **"Create public/secret gist"**.

---

### 11.4 🌀 Versionado y Forks

* Cada cambio queda registrado como una nueva versión (como un commit).
* Puedes ver el historial completo.
* Otros usuarios pueden **"forkear"** tu Gist para hacer sus propias ediciones.

---

### 11.5 💻 Usar Gists desde la terminal

Puedes tratar un Gist como cualquier repositorio Git:

```bash
# Clonar un gist público
git clone https://gist.github.com/usuario/ID_DEL_GIST.git

# Hacer cambios y pushearlos (si eres el autor)
cd ID_DEL_GIST
git add .
git commit -m "Actualización"
git push
```

---

### 11.6 🧪 Usar la GitHub CLI con Gists

GitHub CLI permite interactuar con gists fácilmente:

```bash
# Crear un nuevo gist
gh gist create archivo.txt -d "Descripción" --public

# Listar tus gists
gh gist list

# Ver detalles
gh gist view ID

# Clonar
gh gist clone ID
```

---

### 11.7 🧠 Casos de uso recomendados

* Guardar fragmentos de código útiles para reutilizar.
* Compartir ejemplos de errores o soluciones en foros.
* Compartir configuraciones rápidas (por ejemplo, `.bashrc`, `settings.json`).
* Mostrar pruebas de concepto en entrevistas técnicas.

---

### 11.8 ✅ Buenas prácticas

* Nombra bien tus archivos (con extensión correcta).
* Agrega una descripción clara.
* Usa Gists secretos si no quieres que se indexen.
* Usa markdown (`.md`) para crear documentación o notas legibles.

---
