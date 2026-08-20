# ALMA BARBER CO. — Sitio web

Landing page de una sola página para una barbería de autor, con estética dark/leather/gold. Archivo único y autocontenido: `index-4.html`.

## Cómo verlo

Abre `index-4.html` directamente en cualquier navegador (doble clic, o "Abrir con..."). No necesita servidor, build ni instalación — HTML, CSS y JS están en un solo archivo, y las fotos van incrustadas como base64 dentro del propio HTML (por eso el archivo pesa varios cientos de KB: no depende de internet para mostrar las imágenes).

## Estructura de secciones

1. **Nav** — logo, links de ancla, botón "Reservar".
2. **Hero** — tarjeta estilo Orizon: barra de filtros (Servicio/Estilista/Sede/Fecha), sidebar de iconos, titular, tarjetas flotantes ("Reserva tu lugar" y "Corte + Barba"). Fondo: foto de referencia "Goodfellas".
3. **Servicios** (`#servicios`) — 3 tarjetas: Corte clásico, Corte + barba, Ritual completo.
4. **Atelier** (`#atelier`) — galería de 3 fotos con esquinas en arco: Estaciones, Sillón de cuero (foto real), Herramientas (foto de referencia "Мочка").
5. **Agenda** (`#agenda`) — formulario de reserva (vista previa, sin conexión a backend todavía).
6. **Productos** (`#productos`) — 4 productos con precio.
7. **Footer** — horario y contacto.

## Pendientes / temporales

- **Fondo del hero** y **foto de "Herramientas"** en Atelier usan imágenes de referencia de otras barberías (Goodfellas Barbershop y Мочка Barber Room) que traen su propio logo impreso en la foto. Están puestas como marcador de posición temporal — hay que reemplazarlas por fotos reales de tu local antes de publicar el sitio.
- El formulario de "Agenda tu cita" es solo de interfaz; falta conectarlo a un backend (Firebase u otro) para que reserve de verdad.
- Textos de servicios, precios, horario y redes son de ejemplo — revisa que coincidan con los reales.

## Personalización rápida

Los colores principales están centralizados como variables CSS al inicio del archivo (`:root`):

```css
--ink       /* fondo general, casi negro */
--leather   /* marrón oscuro, degradados */
--gold      /* dorado, acentos y botones */
--paper     /* texto claro */
--stone     /* texto secundario/gris */
```

Cambiar cualquiera de estos valores actualiza el color en todo el sitio de forma consistente.

## Tipografías y librerías

- **Oswald** — titulares.
- **Instrument Serif (italic)** — acentos tipo firma (precios, "Reserva tu lugar").
- **Inter** — texto de cuerpo.
- **JetBrains Mono** — etiquetas técnicas (mono, precios de tiempo).
- **Three.js** (`r128`, vía CDN) — partículas doradas animadas y anillo flotante en el fondo del hero. Se desactiva automáticamente si el sistema tiene activado "reducir movimiento".

## Responsive

El diseño se adapta en `max-width: 900px` (grillas de servicios/productos a 1–2 columnas) y `max-width: 680px` (sidebar oculto, tarjetas flotantes pasan a apilarse, barra de filtros compacta mostrando solo Estilista + Fecha).

## Reemplazar una imagen

Cada foto está como `data:image/jpeg;base64,...` directamente en el `src` o `background-image`. Para cambiarla, lo más simple es pedir ayuda para insertar la nueva foto (se vuelve a generar el base64 y se reemplaza en el archivo) en vez de editarlo a mano.
