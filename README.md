# MockaBox · sitio web

Tres páginas autocontenidas: cada `.html` lleva dentro sus imágenes, fuentes y scripts. Se suben tal cual a la raíz del repo, sin carpetas de assets.

- `index.html` — landing: juego Angelito o diablito, lo más pedido, combos y contacto
- `pedidos.html` — la carta completa con precios y el carrito; arma el pedido y se abre WhatsApp con todo escrito
- `merch.html` — subpágina de merch (gorras y hoodies), sobre fondo negro

## Cómo navega el cliente

`index.html` → botón **Carta y pedido** o **Pedir** → `pedidos.html`
`index.html` → botón **Merch** → `merch.html`
Las tarjetas de "Lo más pedido" y de combos abren `pedidos.html` con ese producto ya agregado al carrito.

## Publicarlo en GitHub Pages

1. Sube los tres `.html` a la raíz del repo (reemplazando los anteriores).
2. Settings → Pages → Deploy from a branch → `main` / root.
3. El sitio queda en `https://mockabox.github.io/` y el QR apunta ahí.
4. Después de subir, el deploy tarda 1–3 minutos. Si ves la versión vieja, recarga con Cmd+Shift+R o abre en incógnito.

## WhatsApp

Todo escribe al **+593 99 837 3559** con el mensaje ya armado:

- `pedidos.html`: el botón inferior manda el pedido completo — productos, total, modo (para llevar o domicilio), nombre, hora o dirección, nota y forma de pago
- `merch.html`: cada pieza manda su nombre para que solo respondas talla y stock
- `index.html`: el número del pie y el registro de puntaje del juego (nombre, bando y puntos)

## Ranking del juego

Los puntajes se guardan en Supabase (proyecto `mockabox`), así que el Top 5 lo ven todas las personas que abran la página, desde cualquier teléfono.

- Tabla `puntajes` en Supabase → Table Editor. Ahí puedes borrar registros de prueba o tramposos.
- El Top muestra solo los puntajes **del día**; el histórico completo queda en el panel.
- Cada nombre aparece una sola vez, con su mejor puntaje del día.
- Si Supabase no responde, la página cae a la tabla local del teléfono y el juego sigue funcionando.

## Horarios

6:30 am – 7:00 pm. La página de pedidos usa ese rango para mostrar "Abierto ahora" o "Cerrado ahora".

## Qué falta definir

- **Dirección**: en el pie dice "pendiente". Con el enlace de Google Maps se conecta.
- **Costo de envío**: hoy la página dice que se confirma por WhatsApp según el sector.
- **Premio del día**: definir qué se entrega al primer puesto del ranking.

## Para editar

Los archivos `_src-*.dc.html` del proyecto son las fuentes con las que se compilan estas páginas. No hace falta subirlos al repo.
