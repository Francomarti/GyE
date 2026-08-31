# Portal SuTurf — Club Gimnasia

Sitio estático (HTML/CSS/JS, sin build) pensado para vivir en el mismo repo/GitHub Pages que usás para el proyecto de rindes.

## Instalación

1. Copiá toda esta carpeta (`index.html`, `cronograma.html`, `facturas.html`, `css/`, `js/`, `data/`, `.nojekyll`) dentro de tu repositorio.
   - Si querés que conviva con el proyecto de rindes en el mismo repo, ponela en una subcarpeta, por ejemplo `/gimnasia`, y vas a acceder en `tuusuario.github.io/turepo/gimnasia/`.
   - Si preferís un repo aparte, funciona igual poniéndola en la raíz.
2. Hacé commit y push. GitHub Pages la publica sola (como ya te pasa con rindes), no hace falta ningún build step.

## Cómo actualizar el contenido

No hay backend ni base de datos: el sitio lee dos archivos JSON en `/data` y arma las páginas al vuelo con JavaScript. Para actualizar:

- **Cronograma**: editá `data/plan.json`. Cada tarea tiene `estado: "planificado"` o `"realizado"` — cambiá ese valor para tildarla. Podés agregar tareas nuevas copiando el formato de una fila existente (asignale un `id` que no se repita). El campo `meta.mesesTranscurridos` es el que controla el cálculo de balance contra la cuota fija — subilo a mano mes a mes.
- **Facturas**: editá `data/facturas.json`. Cada factura tiene `estado: "pendiente" | "parcial" | "pagada"`, y los campos `montoPagado` / `fechaPago` / `medioPago` para cuando se cobra. Ya viene una fila de ejemplo — reemplazala o borrala.

Podés editar estos JSON directamente desde la web de GitHub (ícono de lápiz sobre el archivo) sin necesidad de clonar el repo ni usar la terminal — hacés el cambio, ponés un mensaje de commit y en menos de un minuto el sitio ya se actualiza solo.

## Estructura

```
index.html          → portada con accesos a cronograma y facturación
cronograma.html      → plan de tareas, resumen y balance vs. cuota fija
facturas.html         → tabla de facturas, cobrado y saldo pendiente
css/style.css         → estilos compartidos
js/app.js             → helpers de formato y carga de datos
data/plan.json        → datos del cronograma (editar acá)
data/facturas.json    → datos de facturación (editar acá)
```

## Compartir con la dirigencia

Una vez publicado, mandales directamente el link de `index.html` (o el de GitHub Pages con la subcarpeta si corresponde). Es de solo lectura — no pueden editar nada desde el navegador, así que no hay riesgo de que alguien te toque un número por accidente.
