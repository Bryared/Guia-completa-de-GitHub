# 12. 🌐 Publicación de sitios web con GitHub Pages

**GitHub Pages** te permite alojar sitios web estáticos directamente desde tu repositorio de GitHub. Ideal para portfolios, blogs, documentación o proyectos personales.

| **Ventaja**                                | **Descripción**                                                               |
| ------------------------------------------ | ----------------------------------------------------------------------------- |
| 🌐 **Hosting gratuito**                    | Publica sitios web sin costo directamente desde tu repositorio.               |
| 🚀 **Despliegue automático**               | Cada vez que haces push a `main` o `gh-pages`, el sitio se actualiza solo.    |
| 🛠️ **Soporte para Jekyll y Markdown**     | Puedes usar Jekyll para blogs o escribir el sitio en Markdown fácilmente.     |
| 🔒 **HTTPS incluido**                      | GitHub Pages proporciona certificados SSL automáticos.                        |
| 🧩 **Integración con GitHub**              | Se conecta directo con tu flujo de trabajo de Git: Issues, Actions, PRs, etc. |
| 💡 **Ideal para documentación**            | Perfecto para wikis, portafolios, currículums, guías técnicas, etc.           |
| 🧑‍💻 **Sin necesidad de servidor propio** | No necesitas configurar o mantener servidores para tu página.                 |
| 📁 **Soporte para sitios estáticos**       | Ideal para HTML, CSS, JS, frameworks como Hugo, Docusaurus o VuePress.        |

---

### 12.1 🧭 ¿Qué es GitHub Pages?

* Un servicio gratuito de GitHub para alojar contenido estático (HTML, CSS, JS).
* Usa el contenido de una rama específica del repositorio.
* Se genera automáticamente con cada push.
* Soporta generadores como **Jekyll**, **Hugo**, **Astro**, **Docusaurus**, etc.

---

### 12.2 🏗️ Métodos de despliegue

| Rama o carpeta | Propósito                                         |
| -------------- | ------------------------------------------------- |
| `gh-pages`     | Rama estándar para publicar                       |
| `/docs`        | Carpeta dentro de `main` para sitios documentales |
| GitHub Actions | Automatización de builds y despliegues            |

---

### 12.3 🧪 Crear un sitio básico con HTML

1. Crea un nuevo repositorio con nombre `usuario.github.io`
2. Sube un archivo `index.html`
3. Ve a **Settings → Pages**
4. Selecciona la rama y carpeta (ej: `main` y `/`)
5. Visita tu sitio: `https://usuario.github.io`

---

### 12.4 💎 Uso de generadores estáticos

#### 🧱 Jekyll (por defecto en GitHub Pages)

1. Crea un repo con estructura Jekyll (`_config.yml`, `_posts/`, etc.)
2. Usa una plantilla o theme de GitHub
3. GitHub Pages lo compilará automáticamente

> Puedes iniciar con: [https://pages.github.com/themes](https://pages.github.com/themes)

---

#### ⚡ Otros generadores (Hugo, Docusaurus, Astro...)

> Estos necesitan un paso de **build** previo y desplegar el contenido resultante (carpeta `dist`, `build`, `public`, etc.)

Ejemplo con Hugo:

```bash
# Instala y genera el sitio
hugo new site mi-sitio
cd mi-sitio
hugo

# Publica la carpeta /public con GitHub Pages
```

Automatiza con GitHub Actions (ver sección 10).

---

### 12.5 🛠️ Configurar un dominio personalizado

1. Compra o gestiona un dominio (ej: desde Namecheap)
2. En la raíz del repo, crea un archivo `CNAME` con el dominio deseado
3. Apunta los DNS (tipo A o CNAME) a GitHub:

| Tipo  | Valor                           |
| ----- | ------------------------------- |
| A     | `185.199.108.153` (y variantes) |
| CNAME | `usuario.github.io`             |

---

### 12.6 🔐 HTTPS y seguridad

* GitHub Pages soporta HTTPS gratuito con Let's Encrypt.
* Se activa automáticamente al configurar un dominio personalizado.
* También puedes forzar HTTPS desde la sección Pages en los **Settings**.

---

### 12.7 🧩 Automatización con GitHub Actions

```yaml
name: Deploy to GitHub Pages

on:
  push:
    branches: [main]

jobs:
  deploy:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - run: npm install && npm run build
      - uses: peaceiris/actions-gh-pages@v3
        with:
          github_token: ${{ secrets.GITHUB_TOKEN }}
          publish_dir: ./dist
```

---

### 12.8 📌 Buenas prácticas

* Usa un generador moderno como Astro o Hugo para mejor rendimiento.
* Documenta el uso del sitio en un README.
* No publiques credenciales o datos sensibles.
* Mantén actualizado el contenido y el diseño responsivo.
* Usa GitHub Actions para automatizar builds.

---

### 12.9 🧠 Recursos adicionales

* [GitHub Pages Docs](https://docs.github.com/en/pages)
* [Jekyll Docs](https://jekyllrb.com/docs/)
* [Astro](https://astro.build)
* [Hugo](https://gohugo.io/)
* [Docusaurus](https://docusaurus.io)

---
