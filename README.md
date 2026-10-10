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

## Dominio propio (full-growth.com.ar)

El dominio se compra en **NIC Argentina** y el DNS se maneja en **Cloudflare** (plan gratis). NIC no permite cargar registros DNS: solo deja "delegar" el dominio a los servidores de otro servicio, en este caso Cloudflare.

1. **Comprar en NIC:** en [nic.ar](https://nic.ar) buscá `full-growth.com.ar` → **Quiero registrarlo** → entrá con CUIT y Clave Fiscal (nivel 2 o superior) → **Registrar** → **Confirmar Trámite** → pagá con tarjeta, PagoMisCuentas o Rapipago.
2. **Sumar el dominio a Cloudflare:** creá una cuenta gratis en [cloudflare.com](https://dash.cloudflare.com/sign-up), agregá `full-growth.com.ar`, elegí el plan **Free** y anotá los **dos nameservers** que te asigna (algo como `xxx.ns.cloudflare.com`).
3. **Delegar en NIC:** en NIC Argentina, en tus dominios, entrá a **Delegar** y cargá los dos nameservers de Cloudflare. El cambio tarda de minutos a 24 horas; Cloudflare te avisa por email cuando el dominio queda **Active**.
4. **Registros DNS en Cloudflare** (DNS → Records), todos con la nube en gris (**DNS only**):
   - Cuatro registros **A** con nombre `@`: `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
   - Un registro **CNAME** con nombre `www` que apunte a `alxrconluna06.github.io`
5. **Verificar el dominio en GitHub** (evita que otra cuenta lo use): foto de perfil → **Settings → Pages → Add a domain**, escribí `full-growth.com.ar` y cargá en Cloudflare el registro **TXT** que te muestra. Después tocá **Verify**.
6. **Conectar el sitio:** en el repositorio, **Settings → Pages → Custom domain**, escribí `full-growth.com.ar` y **Save**. Cuando el chequeo dé OK, activá **Enforce HTTPS** (el certificado puede tardar hasta un día).
7. Volvé a correr **Publicar sitio** en la pestaña **Actions** para que la dirección nueva quede en Google y en las vistas previas de redes.

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
- Email: info@full-growth.com.ar

Para cambiarlos, buscá esos datos en `index.html` y reemplazalos en todos los lugares donde aparecen.
