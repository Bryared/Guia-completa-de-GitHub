# 🧱 Flujo básico de trabajo con Git
---

Esta sección cubre el ciclo más común al usar Git: **verificar el estado del repositorio, añadir cambios, confirmar, visualizar historial y deshacer errores**.

---

## 3.1 🔍 Estado del repositorio

El comando `git status` muestra el estado actual de tu repositorio, incluyendo:

* Archivos **no rastreados** (*untracked*).
* Archivos **modificados pero no añadidos**.
* Archivos **en el área de staging** listos para commit.

```bash
git status
```

> 📸 *\[Aquí podrías mostrar un ejemplo visual de salida del comando `git status`]*

---

## 3.2 🧾 Agregar y confirmar cambios

#### ➕ Agregar cambios:

Antes de confirmar, necesitas añadir archivos al área de staging.

```bash
git add archivo.txt      # Agrega un archivo específico
git add .                # Agrega todos los cambios en el directorio actual
```

#### ✅ Confirmar cambios (commits):

```bash
git commit -m "Mensaje corto y descriptivo"
```

##### Variantes útiles:

* `git commit -v`: muestra los cambios durante el commit.
* `git commit --amend`: permite modificar el último commit (mensaje o contenido).

> 📸 *\[Aquí podrías mostrar una animación del flujo add → commit]*

---

## 3.3 📜 Ver historial

#### Ver historial básico:

```bash
git log
```

#### Opciones útiles:

```bash
git log --oneline         # Muestra los commits resumidos
git log --graph --all     # Muestra ramas y fusiones como gráfico
```

#### Otros comandos:

* `git show`: muestra el detalle de un commit.
* `git diff`: compara archivos modificados.

> 📸 *\[Sugerencia: insertar captura de `git log --graph --oneline`]*

---

## 3.4 🔖 Tags y versiones

#### Crear un tag:

```bash
git tag v1.0              # Tag ligero
git tag -a v1.0 -m "Versión 1.0"   # Tag anotado con mensaje
```

#### Ver tags:

```bash
git tag
```

#### Usos comunes:

* Marcar versiones estables o lanzamientos (siguiendo semver: v1.0.0, v2.1.3, etc).

---

## 3.5 🧯 Recuperación rápida

A veces se cometen errores. Aquí algunas herramientas de rescate:

#### 🔁 `git reset`:

* `--soft`: vuelve a un commit anterior, conserva cambios en staging.
* `--mixed`: vuelve atrás y deshace el staging.
* `--hard`: ⚠️ elimina cambios en staging y en el working directory.

```bash
git reset --soft HEAD~1
```

#### 🔄 `git restore`:

* Restaura archivos individuales desde el último commit.

```bash
git restore archivo.txt
```

> 📸 *\[Aquí puedes agregar un esquema comparativo: reset vs restore]*

---

## 3.6 📝 Ejercicio

> Crea un pequeño proyecto, haz varios cambios, crea varios commits y luego practica lo siguiente:

* Usar `git reset` para volver al estado anterior.
* Usar `git restore` para deshacer modificaciones en archivos individuales.
* Crear y listar tags.

---
