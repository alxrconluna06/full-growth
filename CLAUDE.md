# Full Growth · sitio web

Sitio de una sola página de **Full Growth**, consultora de crecimiento digital y E-commerce para marcas argentinas (Mercado Libre, tienda propia, recompra y tecnología). Publicado en GitHub Pages con dominio propio: https://full-growth.com.ar (comprado en NIC Argentina, DNS en Cloudflare, vence el 10/10/2027; la dirección vieja alxrconluna06.github.io/full-growth/ redirige sola)

Dueño del proyecto: Luna (alxrconluna@gmail.com). Habla en español rioplatense; respondé siempre en español, con voseo.

## Cómo está armado

- Todo el sitio vive en **`index.html`**: HTML, CSS y JS en un solo archivo, sin build ni dependencias locales.
- Librerías por CDN, cargadas al final del `<body>`: Lenis (scroll suave), GSAP + ScrollTrigger (animaciones al bajar). Si no cargan, el sitio funciona igual, sin esas animaciones.
- Tipografías de Google Fonts: **Stack Sans Headline** (títulos) y **Google Sans Flex** (texto, botones y logo).
- `404.html`, `robots.txt`, `sitemap.xml`, `site.webmanifest` y `assets/` (íconos e imagen para compartir `og-image.jpg` de 1200×630). Los íconos y la imagen se generan con `.claude/gen-icons.html` en la raíz de PROYECTO LUNA (doble barra M4).
- Los marcadores `__SITE_URL__` y `__LASTMOD__` NO se tocan: el workflow los reemplaza al publicar con la URL real de Pages (o del dominio propio).

## Publicar

- Cada push a `main` publica solo vía `.github/workflows/deploy.yml` (GitHub Actions → Pages). Tarda 1–2 minutos.
- El workflow copia todo a `_site/` excepto `.git`, `.github`, `README.md`, `CLAUDE.md` y `.claude`, y falla si quedan marcadores sin reemplazar.
- Commits en español, cortos y descriptivos (por ejemplo "Cambiar texto de la tarjeta de Recompra").

## Probar antes de subir

```bash
python3 -m http.server 8000
# abrir http://localhost:8000/
```

Checklist mínimo después de cada cambio:
1. Sin errores en la consola.
2. A 390 px de ancho no hay scroll horizontal y el menú del celular abre y cierra.
3. Las animaciones al bajar funcionan (la clase `gsap-on` queda en `<html>`); con "reducir movimiento" activado todo se ve estático y completo.
4. El formulario arma el mensaje y los enlaces de WhatsApp y email se completan.

## Sistema visual

- Paleta violeta. Acento `--accent: #7c2cff`. Fondos oscuros `--night: #0d0d0f`. Lila suave `#ebdfff → #cdb1ff`. Verde `#12a70a` solo para subas y reputación.
- Todos los colores salen de los tokens en `:root`; hay modo oscuro por `prefers-color-scheme` y `data-theme`.
- Radios: 10/16/24/32 px. Botones píldora con texto que "rueda" al pasar el mouse.
- **Logo (M4, elegido el 10/10/2026):** "FULL // GROWTH" en mayúsculas espaciadas (`.lg-a`, Stack Sans Headline 600, `letter-spacing:.22em`) con doble barra: la primera lila `#a77bff` y la segunda violeta intenso `#5a1fc7` (markup `FULL<b><i>/</i><i>/</i></b>GROWTH`). Va sobre recuadro blanco en el menú, al mismo tamaño que el botón "Pedir diagnóstico"; en el pie toma el color del texto (`--ink`) para verse en modo oscuro. Las variantes descartadas están en `Logo Full Growth.html` y `Logo Full Growth - Mayusculas.html`, en la raíz de PROYECTO LUNA.
- **Menú:** logo, menú y botón miden lo mismo (56 px). Al bajar los tres se juntan en el centro (`.nav.compact`, ancho calculado en JS). "Pedir diagnóstico" es un degradé violeta con borde suave y desenfoque.
- Colores de las tarjetas de "Qué hacemos": Diagnóstico violeta, Marketplaces negro, Tienda propia blanco, Recompra negro, Tecnología lila.
- Pestañas de "Para quién": cada una con un degradé violeta distinto, nunca negro.
- Bloque de contacto: fondo violeta muy oscuro con brillo violeta arriba a la izquierda. Botón "Preparar mi pedido" con degradé violeta.

## Contenido y tono

- Textos en español rioplatense, cercanos y concretos, hablando desde el lado del cliente. Nada de jerga (ROAS, ACOS, ERP, onboarding) en títulos.
- **No mostrar precios** de ningún servicio.
- Se escribe **"E-commerce"** con E mayúscula y guion.
- **Títulos y botones con mayúscula en cada palabra** (estilo título): "Hacé Crecer Tu Marca Dentro y Fuera de Mercado Libre.", "Todo Lo Que Tu Canal Digital Necesita, En Un Mismo Equipo", "Pedir Diagnóstico". Solo van en minúscula "y" (e, o, u) y "de", salvo al empezar una frase; todas las demás palabras llevan mayúscula. Aplica a h1–h4, eyebrows, pestañas, botones, menú, preguntas frecuentes, títulos de paneles y frases grandes de "Para quién". En "Qué hacemos", "Para quién" y "Soluciones" también va en viñetas, etiquetas, chips y textos cortos de las tarjetas. Los párrafos y el mensaje de ejemplo de WhatsApp siguen en minúscula normal.
- Primero promociones y herramientas sin costo; la publicidad paga es un complemento, nunca la base.
- "Precios iguales en todos los canales" no se promete (las comisiones de Mercado Libre lo impiden).
- No usar nombres o marcas de Mercado Libre como propios (por ejemplo, "Vendedor líder · Nivel platino" en lugar de "MercadoLíder Platinum"). El pie aclara que Full Growth es independiente.
- Todos los números de los paneles son de ejemplo y deben decir "Ejemplo".
- Cifras del mercado: CACE 2025 vía Revista Mercado (con link a la fuente).
- Antes de cambiar textos, ofrecé 3 o 4 opciones con enfoques distintos y una recomendada; Luna suele combinar opciones.

## Estructura de la página (en orden)

1. Menú fijo + inicio a pantalla completa con título y tres paneles: Métricas, Reputación de la cuenta, Origen de tus ventas (misma altura).
2. "Por qué ahora": cifras del E-commerce argentino 2025.
3. "Qué hacemos" (`#servicios`): Diagnóstico 360 primero ("Por dónde empezar"), Marketplaces (Gestión Integral, sin publicidad como base), Tienda propia, Postventa y Fidelización, Panel de Datos (próximamente).
4. "Para quién" (`#para-quien`): 5 pestañas (Quiero vender más, Fabrico o importo, Tengo una marca conocida, Tengo locales, Vendo en varios canales).
5. "Soluciones" (`#planes`): pestañas sin precios (Marketplaces · Tienda Propia · Postventa y Tecnología) + combo "Canal Doble" en lila (Gestión Integral + Tienda Online + Postventa y Fidelización). Los servicios salen de `Full Growth - Servicios desglosados` (raíz de PROYECTO LUNA): sin Landing, Integraciones ni App Propia; Full oculto por ahora; Esencial y Crecimiento unidos en "Gestión Integral".
6. Contacto (`#contacto`): formulario que arma el mensaje y lo manda por WhatsApp o email.
7. Pie de página: "Pensamos tu E-commerce como si fuera nuestro."
- Las Preguntas frecuentes (`#preguntas`) NO están en la página: se abren como ventana desde el menú y el pie.
- Secciones que se quitaron a pedido (no volver a agregarlas sin consultar): frase principal y bandas en movimiento debajo del inicio, "Por qué elegirnos", "Cómo trabajamos", "Reportes", "Marcas fundadoras", etiqueta "Abrimos cupos…" y subtítulo del inicio.

## Contacto configurado

- WhatsApp: +54 9 11 5122-7198 (`https://wa.me/5491151227198`)
- Email: info@full-growth.com.ar

## Cosas a tener en cuenta en el código

- `animate(sel, preset)` acepta el nombre del preset como texto (`'left'`, `'up'`, `'zoom'`, `'tilt'`) o una función (`presets.fan`). Si agregás presets, sumalos al objeto `presets`.
- Toda animación que dependa de un elemento debe chequear que exista (se borraron secciones y el JS quedó con guardas).
- El texto del inicio nunca se desvanece al bajar (`.hero-inner` tiene opacidad fija); no reintroducir ese efecto.
- La página siempre arranca arriba al recargar (`history.scrollRestoration = 'manual'`) salvo que la URL tenga un `#ancla`.

## Pendientes

- Cargar el sitio en Google Search Console y enviar `sitemap.xml`.
