# Portal SuTurf — Club Gimnasia

Sitio estático (HTML/CSS/JS, sin build) para GitHub Pages, con la identidad visual de SuTurf Tandil y Gimnasia y Esgrima Tandil.

## ⚠️ Si ya tenés el portal anterior subido a GyE

Este paquete reemplaza `index.html`, `cronograma.html`, `facturas.html`, `css/style.css` y suma `assets/` y `data/facturas-pdf/`.

**Antes de subir esta versión nueva**, abrí tu `data/facturas.json` actual en GitHub y copiá/guardá en algún lado el contenido si ya cargaste facturas reales — el `facturas.json` de este paquete trae de nuevo solo la fila de ejemplo, y no querés perder lo que ya cargaste. Después de subir la versión nueva, volvé a pegar tus facturas reales agregando el campo `"pdf": null` (o la ruta del PDF si lo subiste) a cada una.

`plan.json` no cambió de estructura, así que si ya marcaste tareas como realizadas, podés subir la versión nueva sin miedo a perder eso — pero por las dudas, mismo consejo: si le hiciste cambios, guardalos aparte antes de sobreescribir.

## Instalación / actualización

1. Descomprimí el zip.
2. En GitHub, "Add file" → "Upload files", arrastrá todo el contenido (respeta la estructura de carpetas).
3. Commit. Esperá el redeploy (pestaña Actions) y refrescá con Ctrl+Shift+R.

## Cómo actualizar el contenido

- **Cronograma**: `data/plan.json`. Tildá tareas cambiando `"estado"` a `"realizado"`. Agregá tareas nuevas copiando el formato de una fila existente.
- **Facturas**: `data/facturas.json`. Cada factura tiene `estado`, `montoPagado`, `fechaPago`, `medioPago`, y ahora `pdf`.

### Cómo adjuntar el PDF de una factura

1. Subí el archivo PDF a la carpeta `data/facturas-pdf/` (Add file → Upload files, ahí también acepta arrastrar un solo PDF). Nombralo de forma clara, por ejemplo `factura-0002.pdf`.
2. En el bloque de esa factura en `facturas.json`, poné la ruta en el campo `pdf`:

```json
"pdf": "data/facturas-pdf/factura-0002.pdf"
```

3. Si una factura todavía no tiene PDF cargado, dejá `"pdf": null` — en la tabla va a aparecer un guión en vez del botón.

## Estructura

```
index.html              → portada
cronograma.html          → plan de tareas y balance vs. cuota fija
facturas.html             → tabla de facturas, PDFs, cobrado y saldo
css/style.css             → estilos e identidad visual
js/app.js                 → helpers de formato y carga de datos
assets/logo-suturf.png    → isotipo SuTurf Tandil
assets/logo-gimnasia.png  → escudo Gimnasia y Esgrima Tandil
data/plan.json             → datos del cronograma (editar acá)
data/facturas.json         → datos de facturación (editar acá)
data/facturas-pdf/         → PDFs de las facturas subidas
```

## Compartir con la dirigencia

Mandales el link de `index.html` (o la URL de GitHub Pages con la subcarpeta si corresponde). Es de solo lectura.
