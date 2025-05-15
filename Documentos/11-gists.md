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
Los **Gists** son mini-repositorios para compartir fragmentos de código o notas, públicos o secretos. Útiles para snippets reutilizables, configuraciones rápidas o documentación pequeña.


#### 1. 🖥️ Crear un Gist desde la web

1. Ve a [gist.github.com](https://gist.github.com/).  
2. Inicia sesión en tu cuenta de GitHub.
3. Nos vamos a Create new...
![Vamos a Create new...](https://media.discordapp.net/attachments/724308790098395236/1372477809548726342/image.png?ex=6826eb11&is=68259991&hm=3eab504d33fe7ced09f708cb52ae71853765a668d5d37a672caf0af567628794&=&format=webp&quality=lossless&width=286&height=242)
4. Rellena los campos:  
   * **Filename**: nombre del archivo (p. ej. `snippet.py`).  
   * **Content**: pega tu código o texto.  
   * **Description** (opcional, recomendado): explica el propósito.  
   * **Public / Secret**: selecciona visibilidad.
  
![Rellenamos](https://media.discordapp.net/attachments/724308790098395236/1372481737896235098/image.png?ex=6826eeb9&is=68259d39&hm=0f4d457dd2078885f6a926017f35a1c1d54e7883f2a61cd511214da0460625ac&=&format=webp&quality=lossless&width=738&height=540)

5. Haz clic en **Create public gist** o **Create secret gist**.  

> 🔗 Cada Gist tiene su propia URL y un pequeño historial de versiones.

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
