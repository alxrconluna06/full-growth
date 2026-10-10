# Full Growth · Sitio web

Sitio de una sola página de Full Growth, listo para publicarse en **GitHub Pages**.
Cada vez que se sube un cambio a la rama `main`, el sitio se vuelve a publicar solo.

## Qué hay en esta carpeta

| Archivo | Para qué sirve |
| --- | --- |
| `index.html` | El sitio completo |
| `404.html` | Página que aparece si alguien entra a una dirección que no existe |
| `assets/` | Ícono del sitio, íconos para celular e imagen para compartir en redes |
| `robots.txt` y `sitemap.xml` | Ayudan a Google a encontrar e indexar el sitio |
| `site.webmanifest` | Nombre e ícono cuando alguien guarda el sitio en el celular |
| `.github/workflows/deploy.yml` | La publicación automática |

Los textos `__SITE_URL__` y `__LASTMOD__` se completan solos al publicar con la dirección real del sitio. No hace falta tocarlos.

## Publicar por primera vez (una sola vez, unos 10 minutos)

1. Creá una cuenta gratis en [github.com](https://github.com) si todavía no tenés.
2. Creá un repositorio nuevo: botón **New**, nombre `full-growth`, visibilidad **Public**, sin README. Botón **Create repository**.
3. Subí los archivos de esta carpeta al repositorio (ver opciones abajo).
4. En el repositorio, entrá a **Settings → Pages** y en **Source** elegí **GitHub Actions**.
5. Entrá a la pestaña **Actions**, abrí **Publicar sitio** y tocá **Run workflow** (solo la primera vez).
6. En uno o dos minutos el sitio queda online en `https://TU-USUARIO.github.io/full-growth/`.

### Cómo subir los archivos

- **Opción A, la más automática:** decile a Claude el nombre del repositorio (por ejemplo `tu-usuario/full-growth`) y él sube todo. Antes conectá tu cuenta de GitHub en claude.ai → Settings → Connectors.
- **Opción B, desde la web de GitHub:** en el repositorio vacío tocá **uploading an existing file** y arrastrá todos los archivos. Ojo: la carpeta `.github` empieza con punto y algunas computadoras la ocultan. Si no se sube, creala a mano con **Add file → Create new file**, con el nombre `.github/workflows/deploy.yml`, y pegá el contenido del archivo.
- **Opción C, con Git instalado:**
  ```bash
  git init -b main
  git add .
  git commit -m "Sitio Full Growth"
  git remote add origin https://github.com/TU-USUARIO/full-growth.git
  git push -u origin main
  ```

## Actualizar el sitio

Cambiá el archivo (por ejemplo `index.html`) desde la web de GitHub con el ícono del lápiz y guardá con **Commit changes**. En uno o dos minutos el cambio se ve online. El avance se sigue en la pestaña **Actions**.

## Usar un dominio propio (cuando lo tengas)

1. Comprá el dominio, por ejemplo en [nic.ar](https://nic.ar) para `.com.ar`.
2. En GitHub: **Settings → Pages → Custom domain**, escribí el dominio (por ejemplo `fullgrowth.com.ar`) y guardá.
3. En el panel DNS de tu dominio cargá estos registros:
   - Cuatro registros **A** para `@`: `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
   - Un registro **CNAME** para `www` que apunte a `TU-USUARIO.github.io`
4. Cuando GitHub verifique el dominio, activá **Enforce HTTPS**.
5. Volvé a correr **Publicar sitio** en la pestaña **Actions** para que la dirección nueva quede en Google y en las vistas previas de redes.

## Después de publicar

- Cargá el sitio en [Google Search Console](https://search.google.com/search-console) y enviá `sitemap.xml` para que Google lo indexe más rápido.
- Probá cómo se ve al compartirlo en WhatsApp o LinkedIn: tiene que aparecer la imagen violeta con el título.

## Trabajar con Claude Code

El archivo `CLAUDE.md` tiene todo el contexto del proyecto (diseño, tono, decisiones y cómo publicar). Claude Code lo lee solo al empezar cada sesión.

- **En el navegador, sin instalar nada:** entrá a [claude.ai/code](https://claude.ai/code), elegí el repositorio `alxrconluna06/full-growth` y pedí el cambio.
- **En la app de escritorio de Claude:** pestaña **Code**, elegí la carpeta o el repositorio del proyecto.
- **En la terminal:** instalá Claude Code ([guía oficial](https://code.claude.com/docs/en/overview)), cloná el repositorio y corré `claude` dentro de la carpeta:
  ```bash
  git clone https://github.com/alxrconluna06/full-growth.git
  cd full-growth
  claude
  ```

## Contacto configurado en el sitio

- WhatsApp: +54 9 11 5122-7198
- Email: alxrconluna@gmail.com

Para cambiarlos, buscá esos datos en `index.html` y reemplazalos en todos los lugares donde aparecen.
