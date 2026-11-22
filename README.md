# Sevilla VGC — calendario de torneos

Web estática responsive para publicar los torneos VGC de Sevilla. Incluye calendario mensual, filtros, enlaces de inscripción, ganadores y estado automático de torneos realizados.

## Administrar torneos con Google Sheets

La página lee una pestaña de Google Sheets publicada como CSV. Conserva los encabezados y añade una columna `ganador` al final:

`fecha, tienda, modalidad, hora, precio, inscripcion, nombre, ganador`

- `fecha`: fecha del torneo. Admite `AAAA-MM-DD` o `DD/MM/AAAA`.
- `tienda`: tienda organizadora.
- `modalidad`: Challenge, Cup o Especial.
- `hora`: por ejemplo 10:00.
- `precio`: por ejemplo 6 €.
- `inscripcion`: enlace de inscripción o información.
- `nombre`: título del evento, por ejemplo Especial Navidad.
- `ganador`: nombre del ganador. Se puede dejar vacío antes del torneo.

Para publicar la hoja: Google Sheets → Archivo → Compartir → Publicar en la web → selecciona la pestaña → CSV. Copia la URL CSV en `SHEET_CSV_URL` dentro de `config.js`. No reemplaces tu `config.js` actual si ya contiene esa URL.

Los torneos anteriores a la fecha actual se etiquetan automáticamente como **REALIZADO** y dejan de mostrar el enlace de inscripción en el listado. Los próximos aparecen normalmente. Al añadir el ganador en la columna `ganador`, se muestra en el detalle del día y en el listado.

## Publicar en GitHub Pages

Sube los archivos a la raíz del repositorio y activa Settings → Pages → Deploy from a branch → `main` → `/(root)`.

## Actualizaciones de datos

Los cambios de Google Sheets se reflejan cuando se vuelve a cargar la página y Google actualiza la publicación CSV. Puede haber un pequeño retraso.
