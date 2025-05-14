# 📌 Introducción a Git y GitHub

## 1.1 🎯 Objetivos

* Entender el propósito de un sistema de control de versiones y por qué son herramientas fundamentales en el desarrollo de software moderno.


## 1.2 🧠 ¿Qué es Git?

**Git** es un **sistema de control de versiones distribuido**, que permite a los desarrolladores realizar un seguimiento de los **cambios** realizados en el código fuente durante el desarrollo del software. 

Git permite trabajar de manera **distribuida**, lo que significa que cada desarrollador tiene una copia completa del repositorio en su máquina local.

Fue creado por **Linus Torvalds** en 2005 para gestionar el desarrollo del kernel de Linux.

#### 🔑 Características principales:

* **Velocidad**: Git está optimizado para ser rápido en operaciones como commits, ramas y fusiones.
* **Integridad**: Cada cambio se identifica mediante un hash SHA-1, garantizando la integridad de los datos.
* **Distribuido**: Cada desarrollador tiene una copia completa del repositorio, lo que permite trabajar sin conexión.

#### 🏗️ Arquitectura:

* **Distribuida**: Cada usuario tiene una copia completa del historial.



## 1.3 🌐 ¿Qué es GitHub?

**GitHub** es una plataforma basada en la web que ofrece **alojamiento, control de las versiones, y colaboración para repositorios Git** . 

Facilitando el trabajo en equipo, la integración continua, la documentación y la automatización de tareas.

#### ⭐️ Funcionalidades clave:

* **Repositorios remotos**: Facilita compartir y colaborar en código fuente.
* **Control de versiones en la nube**.
* **Social coding**: Seguimiento de proyectos, issues, pull requests y más.
* **Integración continua** y **automatización** con GitHub Actions.


## 1.4 🆚 Git vs. GitHub:

| Concepto          | Git                                     | GitHub                               |
| ----------------- | --------------------------------------- | ------------------------------------ |
| Tipo              | Software de control de versiones        | Plataforma web para alojar repos Git |
| Uso               | Local en tu equipo                      | En la nube (remoto)                  |
| Necesita internet | No                                      | Sí                                   |
| Colaboración      | Limitada localmente                     | Avanzada: PRs, revisiones, Issues    |
| Interfaz          | Línea de comandos (CLI)                 | Web + CLI (GitHub CLI)               |
| Propietario       | Open source (creado por Linus Torvalds) | Propiedad de Microsoft               |

> 📝 **Resumen:** Git es la herramienta, GitHub es el servicio que te permite sacarle el mayor provecho.


## 1.5 💡 Ventajas del control de versiones

Un sistema de control de versiones como Git aporta enormes beneficios en cualquier proyecto de desarrollo:

#### 👥 Colaboración efectiva:

* Permite que varios desarrolladores trabajen en paralelo sin pisar el trabajo del otro.
* Se pueden crear ramas para desarrollar funcionalidades de forma aislada.

#### 📜 Trazabilidad completa:

* Cada cambio queda registrado: quién lo hizo, cuándo y por qué.
* Posibilidad de volver a versiones anteriores si algo falla.

#### 🌍 Historias de éxito:

* **Linux**, **React**, **Python**, entre muchos otros proyectos open-source se gestionan con Git y GitHub.
* Empresas como Microsoft, Google y Facebook usan Git internamente.

## 1.6 🔄 Flujo de trabajo general

Una forma simplificada de entender el flujo de trabajo con Git y GitHub es:

```
Trabajo local:
  Editar código ➜ git add ➜ git commit

Trabajo remoto:
  git push ➜ Compartir cambios
  git pull ➜ Traer actualizaciones

Colaboración:
  Fork ➜ Clonar ➜ Crear rama ➜ Pull Request ➜ Merge
```

## 1.7 📝 Ejercicio

> Investigar un proyecto *open-source* y describir su flujo de Git/GitHub.

## 1.8 🔗 Recursos

* [Documentación oficial de Git](https://git-scm.com/doc)
* [Documentación oficial de GitHub](https://docs.github.com/)
