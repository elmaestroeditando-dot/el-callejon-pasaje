# Product

<!-- impeccable:product-schema 1 -->

## Platform

web

## Stack

static HTML/CSS/JS (matches sibling projects in this repo; no framework requested, single-page marketing site does not need a build step). Fonts via Google Fonts `<link>` (Archivo Black + Manrope), icons via Phosphor web CDN.

## Users

Gente local de Pasaje (El Oro, Ecuador), familias y grupos de amigos que buscan comida rápida informal para compartir. Deciden desde el celular, guiados por fotos apetitosas del producto y la facilidad de pedir por WhatsApp.

## Deployment

Publicado en Netlify: https://el-callejon-pasaje.netlify.app (proyecto `el-callejon-pasaje`, site id `4b2968ff-bad0-4f2d-add3-41e814572db5`). Nota: Netlify crea los proyectos nuevos con "Team protection" (SSO login) activado por defecto, lo cual bloquea el acceso público; se desactivó explícitamente (`requireSSOTeamLogin:false`) para que los clientes del negocio puedan ver la página sin iniciar sesión. Cada redeploy futuro debe correr desde la carpeta `el-callejon/` (no desde la raíz del repo de "LANDING PAGES", que contiene otros proyectos no relacionados).

## Product Purpose

Landing page de una sola página para "El Callejón", un Bar & Grill de comida rápida. Objetivo: mostrar la comida (alitas, costillas, hamburguesas) como protagonista visual, transmitir el ambiente de barrio/terraza, dar a conocer el menú parcial con precios, mostrar reputación real (4.5★/88 reseñas), facilitar el pedido por WhatsApp y mostrar la ubicación en Pasaje.

## Positioning

Lema propio de marca: "#Compartefelicidad". Identidad informal, callejera, de barrio, no corporativa. Logo real: texto manuscrito/script en rojo con un tenedor integrado, sobre fondo rojo.

## Operating Context

- Negocio físico en Av. Jubones y Municipalidad, Pasaje, El Oro, Ecuador; sede adicional en Machala (sin dirección exacta proporcionada).
- WhatsApp para pedidos/reservas: 0995024999 (enlace `wa.me/593995024999`).
- Calificación real en Google: 4.5★ con 88 reseñas (confirmado por el cliente en el brief).
- Colores de marca: rojo, amarillo/dorado y negro. Tono informal, no corporativo.

## Capabilities and Constraints

- Fotos reales seleccionadas por el cliente, copiadas a `fotos/`: `logo.jpg` (logo oficial, baja resolución ~150x150, se avisó al usuario que se ve pixelado), `ambiente-terraza.jpg` (foto_1, ahora en el hero; el nombre de archivo quedó así por historial pero **el lugar de la foto no es una terraza**, es El Malecón, un parque de Pasaje — el cliente aclaró esto explícitamente, así que el texto visible del sitio nunca debe decir "terraza"; solo el nombre interno del archivo lo conserva), `amigos-compartiendo.jpg` (foto de grupo de amigos que el cliente subió directamente en el chat, ahora en la sección "El barrio se junta"). El cliente pidió este reordenamiento explícitamente tras ver la primera versión.
- Las 3 tarjetas destacadas de `#menu` (`.menu-featured`) usan fotos de stock gratuitas de Pexels en vez de las fotos reales del negocio, porque las fotos reales disponibles (`alitas-papas.jpg`, `plato-completo.jpg`, `hero-hamburguesa.jpg`) no correspondían bien a las 3 etiquetas necesarias (dos de ellas eran fotos de alitas casi idénticas, ninguna de costillas). El cliente pidió explícitamente reemplazar las tres por fotos en línea que sí coincidan con lo que dice cada tarjeta:
  - `alitas-stock.jpg` → "20 alitas" (pexels.com/photo/37322776)
  - `costilla-stock.jpg` → "Costilla entera" (pexels.com/photo/34495394)
  - `combo-stock.jpg` → "Combo 10 alitas doble" (pexels.com/photo/14773000)
  Todas son fotos de Pexels (licencia gratuita, sin atribución requerida). `alitas-papas.jpg`, `plato-completo.jpg` y `hero-hamburguesa.jpg` quedaron sin usar en la página (se conservan en `fotos/` por si se quieren reutilizar más adelante).
- La ruta original pedida para las alitas era `foto_5.jpg`, que no existe en `google_maps_fotos/` (solo hay foto_1, 2, 3, 6, 7, 8). Se sustituyó por `foto_6.jpg` (alitas BBQ + papas en tabla de madera), que encaja con la descripción pedida. Avisado al usuario.
- Sin generador de imágenes disponible en este entorno; no se creó ni se retocó ninguna foto más allá de copiarlas.
- Mapa embebido con `google.com/maps?q=...&output=embed` (sin API key), georreferenciando la dirección de texto; no se usó un enlace de Google Maps específico del negocio porque el cliente no proporcionó uno.
- Pase de pulido (`/impeccable`, pedido explícito del cliente): se quitaron los dos "eyebrows" (etiquetas pequeñas en mayúsculas sobre "Antojos para compartir" y "Encuéntranos en Pasaje"), el logo se agrandó en nav (56px), hero (104px, con anillo/sombra) y footer (68px), y el hashtag de marca se movió de una píldora separada sobre el H1 a una línea dentro del párrafo del hero. Para romper la monotonía de dorado-en-todas-partes sobre fondo carbón plano: los íconos de "Nosotros" y "Ubicación" alternan dorado/rojo por posición, los avatares de reseñas alternan rojo/dorado, y las secciones "Nosotros" (rojo), "Reseñas" (dorado) y "Síguenos en redes" (rojo+dorado combinados) llevan un wash radial sutil de esos colores de marca en vez de carbón liso. También se temáticas los elementos del navegador que antes quedaban por defecto: selección de texto, anillo de foco y scrollbar.
- Segunda vuelta de pulido (mismo día, feedback directo del cliente tras ver la primera): en mobile la página se sentía muy larga y con mucho texto, y el texto secundario se veía apagado. Se recortó el párrafo de "Nosotros" (de ~46 a ~24 palabras) y la intro de "Antojos para compartir" (quitando una frase redundante con `.menu-note`), se quitó una reseña (Diego Ramírez, la única de 4 estrellas) dejando 3 en vez de 4 y se cambió `.reviews-grid` a 3 columnas para que no quede una tarjeta suelta, y se subió `--text-dim` de opacidad .66 a .82 (aplicado también a `.location-info .row span` y al color base de `footer`, que antes tenían valores hardcodeados más tenues). El hero se rediseñó para tener más impacto: nuevo brillo radial rojo/dorado detrás del scrim oscuro, animación de entrada escalonada (logo → título → subtítulo → botones) en vez de aparecer estático, y la palabra "compartir" pasó de solo texto en rojo a un bloque rojo inclinado (highlight tipo marcador) detrás del texto en blanco.
- Tercera vuelta (mismo día): el cliente dijo que el bloque rojo detrás de "compartir" se veía "muy IA" y sugirió algo con cursiva. Se reemplazó por la fuente script real (Google Fonts "Caveat", 700), en dorado, ligeramente rotada (-3°), con sombra sutil — conecta directamente con el logo real de la marca, que ya usa letra manuscrita en rojo. También reportó que la sección "El barrio se junta" se sentía muy vacía tras el recorte de texto anterior: se le devolvió un poco más de sustancia al párrafo, se agregó el badge de calificación (4.5★ · 88 reseñas) arriba del título, un botón "Pedir por WhatsApp" (`.btn-outline`, estilo nuevo) al final de la lista de features para cerrar la columna, y `.about-grid` pasó de `align-items:center` a `align-items:start` para que la columna de texto y la foto arranquen alineadas arriba en vez de dejar espacio flotando arriba/abajo del texto más corto.
- Quinta vuelta (mismo día): el cliente sintió el fondo de toda la página "apagado, sin vida" y pidió un efecto de blur animado por secciones. Se reemplazaron los washes radiales estáticos (`.section-wash-red/-gold/-finale`, `.section-dark`, fondo de `#menu` y del `footer`) por "blobs" reales: `div.blob` (círculo grande, `filter:blur(90px)`, color rojo o dorado de marca a baja opacidad) dentro de un `div.blob-field` (contenedor `position:absolute;inset:0;overflow:hidden`) al inicio de cada sección, animados con `translate`+`scale` en bucle (`blobFloatA/B/C`, 17-24s, `ease-in-out infinite`, distintos por sección para que no se sientan sincronizados). Cada sección con blobs recibió `position:relative;overflow:hidden` para contenerlos (nunca generan scroll horizontal, verificado en 375px/714px/1440px), y `.wrap` ahora lleva `position:relative;z-index:1` para que el contenido quede siempre por encima. Se apaga con `prefers-reduced-motion`.
- Cuarta vuelta (mismo día): tres correcciones. (1) El ícono de WhatsApp (antes el glifo de Phosphor) se reemplazó en todas partes (botón flotante, botones "Pedir por WhatsApp", íconos de contacto, footer) por el trazo oficial de la marca (path real de Simple Icons, embebido inline como `<svg class="ic-wa">`, `fill:currentColor`), y el botón flotante ahora tiene un anillo de pulso continuo (`waPulse`) y un wiggle periódico del ícono cada 6s (`waWiggle`, en un `span.fab-icon` interno para no pelear con la transición de `hover`), además de un globo de chat (`#waBubble`) que aparece a los 2.6s con "¿Se te antojó algo? Escríbenos y coordinamos tu pedido", cerrable (recordado en `sessionStorage` para no repetirse en la misma visita) y que también es un link directo a WhatsApp. (2) El cliente aclaró que la foto del hero (`ambiente-terraza.jpg`) **no es una terraza**, es El Malecón, un parque de Pasaje — se quitó la palabra "terraza" de todo el copy visible (hero-sub, feature "Terraza de barrio" → "Ambiente de barrio", cita de reseña de Kevin Ochoa) sin mencionar "Malecón" explícitamente, tal como pidió el cliente. Solo el nombre interno del archivo sigue diciendo "terraza" (no afecta al visitante).

## Product Principles

1. La comida es la estrella visual: hero a pantalla completa con foto real, tarjetas de menú con fotos grandes.
2. WhatsApp es la acción principal en toda la página (nav, hero, ubicación, botón flotante), con la misma etiqueta "Pedir por WhatsApp" en todos los sitios.
3. Tono informal y cercano ("el barrio", "compartir"), nunca corporativo.
4. No inventar datos: horario, red social y sede de Machala se dejaron honestos/pendientes en vez de fabricados (ver Evidence Gaps).

## Evidence Gaps (open, do not fabricate)

- **Menú incompleto**: los precios integrados son solo los parciales que el cliente ya tenía (costillas, picaditas, combos, alitas). Están marcados con un comentario `ESPACIO PENDIENTE` en `index.html` (sección `#menu`, cerca de `.menu-lists`) para reemplazar por la carta completa cuando el negocio la entregue.
- **Horario real**: no fue proporcionado. El footer dice "escríbenos por WhatsApp y te confirmamos disponibilidad" en vez de inventar un horario. Reemplazar cuando se confirme.
- **Instagram / Facebook / TikTok**: resuelto. El cliente confirmó los tres perfiles reales (@elcallejonpasaje en los tres). Están enlazados en una sección dedicada `#redes` (tarjetas grandes con colores de marca reales) y en los íconos pequeños del footer.
- **Dirección exacta de la sede de Machala**: solo se menciona que existe, sin dirección (el cliente no la dio).
- **Logo de baja resolución**: `fotos/logo.jpg` es pequeño (~150x150) y se ve algo pixelado ampliado. Se usó tal cual (sin upscaling forzado), como pidió el cliente si esto pasaba.
