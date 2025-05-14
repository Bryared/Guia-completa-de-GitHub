# 📌 Introducción a Git y GitHub

## 1.1 🎯 Objetivos

* Entender el propósito de un sistema de control de versiones.
* Conocer la historia y evolución de **Git** y **GitHub**.

## 1.2 🧠 ¿Qué es Git?

**Git** es un sistema de control de versiones distribuido, creado por **Linus Torvalds** en 2005 para gestionar el desarrollo del kernel de Linux.

#### 🔑 Características principales:

* **Velocidad**: Git está optimizado para ser rápido en operaciones como commits, ramas y fusiones.
* **Integridad**: Cada cambio se identifica mediante un hash SHA-1, garantizando la integridad de los datos.
* **Distribuido**: Cada desarrollador tiene una copia completa del repositorio, lo que permite trabajar sin conexión.

#### 🏗️ Arquitectura:

* **Distribuida**: Cada usuario tiene una copia completa del historial.
* **Centralizada** (como SVN): Hay un único repositorio central del que dependen todos.

## 1.3 🌐 ¿Qué es GitHub?

**GitHub** es una plataforma basada en la web que ofrece alojamiento para repositorios Git y herramientas para la colaboración en equipo.

#### ✨ Funcionalidades clave:

* **Repositorios remotos**: Facilita compartir y colaborar en código fuente.
* **Control de versiones en la nube**.
* **Social coding**: Seguimiento de proyectos, issues, pull requests y más.
* **Integración continua** y **automatización** con GitHub Actions.

## 1.4 🆚 Git vs. GitHub:

| Git (Herramienta)               | GitHub (Plataforma)                 |
| ------------------------------- | ----------------------------------- |
| Sistema de control de versiones | Servicio en la nube basado en Git   |
| Funciona localmente             | Repositorios remotos y colaboración |
| 100% CLI                        | Interfaz gráfica + CLI              |

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

## 1.7 🔗 Recursos

* [Documentación oficial de Git](https://git-scm.com/doc)
* [Documentación oficial de GitHub](https://docs.github.com/)
