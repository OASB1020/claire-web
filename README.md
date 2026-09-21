# CLAIRE - sitio web

Sitio estático (sin instalación ni build): `index.html` + carpeta `assets/`.

## Estructura
- `index.html`: home (mujer / hombre), catálogo, sobre nosotros, testimonios y contacto de cada línea.
- `assets/claire-hero.jpg`: imagen del home (logo + degradado).
- `assets/logo-label.jpg`: logo recortado que se usa en las etiquetas de los envases.
- `assets/favicon.svg`: ícono de la pestaña.

## Ver el sitio en tu computador
Abre `index.html` con doble clic, o desde esta carpeta ejecuta `python -m http.server 8000` y entra a http://localhost:8000

## Flujo de versiones (para no afectar producción)
- `main` = producción. Todo lo que llegue a `main` se publica solo.
- Para cualquier cambio (fotos nuevas, textos): crea una rama, por ejemplo `git switch -c fotos-productos`, haz los cambios y súbela con `git push -u origin fotos-productos`.
- El hosting (Cloudflare Pages / Netlify / Vercel) genera un enlace de vista previa para esa rama. Revísalo.
- Si todo está bien, une la rama a `main` (Pull Request en GitHub). Ahí sale a producción.
- Si algo falla, revierte el último cambio en `main` y el hosting vuelve a publicar la versión anterior.

## Cuando tengas dominio
1. En el hosting agrega el dominio en "Custom domain".
2. Copia en tu registrador los registros DNS que el hosting te indique.
3. Con el dominio activo, agrega en `<head>` de `index.html` la etiqueta `<meta property="og:image" content="https://TU-DOMINIO/assets/claire-hero.jpg">` para que WhatsApp e Instagram muestren la imagen al compartir el enlace.

## Pendientes conocidos
- Reemplazar los íconos/ilustraciones de los envases por fotos reales cuando estén listas (sección catálogo, dentro de `.product-photo`).
- Validar las afirmaciones de producto (caída, caspa, "origen natural") antes de difundir.
