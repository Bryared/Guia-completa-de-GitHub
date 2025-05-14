## 🧾 Resumen de comandos esenciales en Git y terminal

A continuación se presenta un resumen de comandos útiles en Git y la terminal, con una descripción clara de su propósito. Este listado incluye comandos básicos, operaciones de commits, navegación entre versiones y gestión de ramas.

##### 📂 Terminal y estructura de archivos

- `ls` → Muestra los archivos del directorio actual.  
- `ls -a` → Muestra todos los archivos, incluidos los ocultos (como `.git`).  
- `cd ..` → Retrocede al directorio padre.  
- `rm "archivo"` → Elimina un archivo del sistema de archivos.

##### 🧱 Inicialización y área de preparación

- `git init` → Inicializa un repositorio Git en el directorio actual, creando `.git`.  
- `git add "archivo"` → Agrega un archivo al área de preparación (staging).  
- `git add .` → Agrega todos los archivos modificados al staging.  
- `git rm --cached "archivo"` → Elimina un archivo del staging, pero no del sistema.  
- `git restore "archivo"` → Restaura un archivo desde el último commit confirmado.  
- `git status` → Muestra el estado de los archivos en el directorio de trabajo y el staging.  
- `git status -s` → Muestra un resumen compacto del estado del repositorio.  

##### 📸 Commits y flujo de cambios

- `git commit -m "mensaje"` → Crea un commit con los archivos en staging.  
- `git commit -am "mensaje"` → Agrega y hace commit de archivos modificados (no nuevos).  
- **Un commit es como una “foto” del estado actual del proyecto.**

##### 🔁 Navegación entre versiones y ramas

- `git checkout "rama"` → Cambia a otra rama o commit existente.  
- `git checkout <ID-del-commit>` → Navega temporalmente a un commit específico.  
- `git reset --soft <ID>` → Vuelve a un commit y mantiene staging y archivos intactos.  
- `git reset --mixed <ID>` → Vuelve a un commit y borra el staging (modo por defecto).  
- `git reset --hard <ID>` → Vuelve al estado exacto de un commit (elimina cambios locales).  
- `git diff --staged` → Muestra las diferencias entre el staging y el último commit.  

##### 📚 Historial de commits

- `git log` → Muestra el historial completo de commits.  
- `git log --oneline` → Muestra el historial en una sola línea por commit.  
- `git log "hash1" "hash2"` → Muestra diferencias entre dos versiones.  
- `git config --global core.abbrev "n"` → Ajusta la longitud de los hashes en `git log`.

###### 🌿 Gestión de ramas

- `git branch` → Muestra todas las ramas locales.  
- `git branch <nombre>` → Crea una nueva rama.  
- `git switch <nombre>` → Cambia a una rama existente.  
- `git switch -c <nombre>` → Crea y cambia a una nueva rama.  
- `git branch -d <nombre>` → Elimina una rama local.  
- `git branch -m <antiguo> <nuevo>` → Cambia el nombre de una rama (desde otra rama).  
- `git branch -m <nuevo>` → Cambia el nombre de la rama actual.

---
##### 🔄 Sincronización con repositorios remotos

- `git remote add origin <url>` → Vincula el repositorio local con uno remoto (como GitHub o GitLab).  
- `git push -u origin main` → Sube la rama actual al remoto y la configura como rama por defecto.  
- `git push` → Envía commits locales a su rama remota correspondiente.  
- `git pull` → Descarga y fusiona los cambios desde el repositorio remoto.  
- `git fetch` → Descarga los cambios remotos sin aplicarlos aún.

##### 🛠️ Trabajo temporal con `stash`

- `git stash` → Guarda temporalmente los cambios sin necesidad de hacer commit.  
- `git stash list` → Muestra la lista de cambios guardados (stashes).  
- `git stash apply` → Aplica el stash más reciente sin eliminarlo de la lista.  
- `git stash pop` → Aplica y elimina el último stash guardado.  

##### 🔖 Etiquetas (Tags)

- `git tag <nombre>` → Crea una etiqueta simple, útil para marcar versiones.  
- `git tag -a <nombre> -m "mensaje"` → Crea una etiqueta anotada con mensaje.  
- `git show <tag>` → Muestra información del commit etiquetado.  
- `git push origin <tag>` → Envía una etiqueta al repositorio remoto.  

##### 🔁 Reversión segura con `revert`

- `git revert <ID>` → Crea un nuevo commit que revierte un commit específico, sin alterar el historial.  

##### 🧽 Limpieza del repositorio

- `git clean -fd` → Elimina archivos y carpetas no rastreadas (⚠️ irreversible).  

##### 👤 Auditoría y análisis

- `git blame <archivo>` → Muestra línea por línea quién hizo cada cambio y cuándo.  

##### 📈 Visualización avanzada del historial

- `git log --graph --oneline --decorate --all` → Muestra un historial gráfico de ramas y commits.  
- `git diff` → Compara cambios entre el directorio de trabajo y el área de preparación (staging).  

---
