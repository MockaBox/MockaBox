# MockaBox · sitio web

Cuatro páginas autocontenidas (todo va dentro del HTML: imágenes, fuentes y scripts). Solo súbelas al repo tal cual.

- `index.html` — landing: juego Angelito o diablito, lo más pedido, combos, pedidos y merch
- `menu.html` — la carta completa con precios
- `pedidos.html` — carrito: el cliente arma el pedido y se abre WhatsApp con todo escrito
- `merch.html` — subpágina de merch (gorras y hoodies), en negro

Los archivos `_src-*.dc.html` son las fuentes con las que se compilan las páginas. No hace falta subirlas, pero no molestan.

## Publicarlo en GitHub Pages

1. Sube los cuatro `.html` a la raíz del repo.
2. Settings → Pages → Deploy from a branch → `main` / root.
3. La landing queda en `https://usuario.github.io/repo/` y el QR apunta ahí.

## WhatsApp

Todos los botones escriben al **+593 99 837 3559** con el mensaje ya armado:

- Landing: "Pedir", cada tarjeta de "Lo más pedido" y de combos, y el número del pie
- Pedidos: el botón inferior manda el pedido completo con total, modo (para llevar o domicilio), nombre, hora o dirección, nota y forma de pago
- Merch: cada pieza manda su nombre para que solo respondas talla y stock
- Juego: al registrar el puntaje se envía nombre, bando y puntos

Si cambia el número, se edita en un solo lugar por página (el campo WhatsApp en Tweaks) y se vuelve a compilar.

## Ranking del juego

Los puntajes se guardan en Supabase (proyecto `mockabox`), así que el Top 5 lo ven todas las personas que abran la página, desde cualquier teléfono.

- Tabla `puntajes` en Supabase → Table Editor. Ahí puedes borrar registros de prueba o tramposos.
- El Top muestra solo los puntajes **del día de hoy**; el histórico completo queda en el panel.
- Un nombre aparece una sola vez, con su mejor puntaje del día.
- Si Supabase no responde, la página cae a la tabla local del teléfono y sigue funcionando.

## Qué falta definir

- **Dirección**: hoy dice "pendiente" en el pie. Manda el enlace de Google Maps y lo conecto.
- **Horarios**: 6:30 am – 7:00 pm (ya puestos; el estado "Abierto / Cerrado" de la página de pedidos usa ese rango).
- **Costo de envío**: la página dice que se confirma por WhatsApp según el sector.
- **Premio del día**: definir qué se entrega al primer puesto. La tabla muestra los puntajes del día y se reinicia sola a la medianoche.
