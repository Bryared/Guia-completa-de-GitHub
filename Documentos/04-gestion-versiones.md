# 🔁 4. Gestión de Versiones y Cambios
Aquí aprenderás a comparar versiones, reescribir el historial de commits, y recuperar información valiosa en situaciones difíciles. Estas habilidades son claves para mantener un repositorio limpio y bien organizado.

---
## 🎯 Objetivo
- Entender cómo deshacer, comparar y rehacer cambios en tu repositiorio  




---

## 4.1 📊 Comparación de revisiones

#### 🔍 Usar `git diff`

Compara el contenido entre dos commits, ramas o archivos:

```bash
git diff               # Muestra diferencias no confirmadas
git diff HEAD          # Compara el working directory con el último commit
git diff <commit1> <commit2>  # Compara dos versiones
```

#### 🛠️ Herramientas visuales: `difftool`

Puedes usar editores externos como VS Code, Meld, Beyond Compare, etc.:

```bash
git difftool           # Abre una vista gráfica de las diferencias
```

> 💡 *Recomendado cuando los cambios son extensos o complejos de leer en la terminal.*

> 📸 *\[Aquí podrías incluir una imagen de una comparación visual entre versiones]*

---

## 4.2 ✍️ Reescritura del historial

Modificar el historial es útil para limpiar commits antes de compartir tu trabajo.

#### 🧩 `git commit --amend`

Edita el último commit:

```bash
git commit --amend -m "Nuevo mensaje para el último commit"
```

También puedes añadir archivos olvidados antes de confirmar.

---

#### 🌀 `git rebase -i`

El rebase interactivo te permite:

* Reordenar commits
* Agrupar (squash) varios commits en uno solo
* Editar mensajes anteriores

```bash
git rebase -i HEAD~3
```

> ✏️ En el editor, puedes elegir:

```
pick   1a2b3c Primer cambio
squash 4d5e6f Cambio relacionado
reword 7g8h9i Mejorar mensaje del commit
```

> 📸 *\[Sugerencia: insertar imagen del proceso de rebase interactivo]*

> ⚠️ *Evita reescribir historial en ramas compartidas con otros colaboradores.*

---

## 4.3 🧭 Reflog y recuperación de commits

#### 📅 ¿Borraste un commit por accidente? Usa `git reflog`

Este comando muestra un historial de los cambios recientes en HEAD, incluso si usaste `reset`, `rebase` o `checkout`.

```bash
git reflog
```

Encuentra el ID del commit perdido y vuelve a él:

```bash
git checkout <commit_id>
```

> 🧠 *Piensa en `reflog` como una “máquina del tiempo” de tus acciones en Git.*

---

#### 🍒 `git cherry-pick`

Permite copiar uno o varios commits específicos de una rama a otra:

```bash
git cherry-pick <commit_id>
```

> Útil para transferir arreglos o mejoras sin hacer un merge completo.

---

## 4.4 🧪 Ejercicio práctico

**Objetivo**: Practicar comparación, rebase y recuperación.

#### Instrucciones:

1. Crea 3 archivos, haz un commit por cada uno.
2. Revisa el historial con `git log` y luego con `git reflog`.
3. Haz un `rebase -i` para combinar los dos primeros commits.
4. Borra el último commit con `git reset --hard HEAD~1`.
5. Usa `git reflog` para recuperarlo con `git cherry-pick`.

---
