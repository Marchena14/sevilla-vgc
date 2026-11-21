# Sevilla VGC — calendario de torneos

Web estática responsive para publicar los torneos VGC de Sevilla. Incluye calendario mensual, filtros por tienda/modalidad, tarjetas de próximos eventos y enlaces de inscripción.

## Probar en local
Abre `index.html` en el navegador. No necesita instalar dependencias ni ejecutar un servidor.

## Publicar gratis en GitHub Pages
1. Crea un repositorio público en GitHub, por ejemplo `sevilla-vgc`.
2. Sube todos los archivos de esta carpeta a la raíz del repositorio.
3. En GitHub entra en **Settings → Pages**.
4. En **Build and deployment**, selecciona **Deploy from a branch**.
5. Selecciona la rama `main` y la carpeta `/ (root)`, guarda.
6. GitHub te dará una dirección pública para compartir en WhatsApp.

## Administrar los torneos con Google Sheets
1. Crea una hoja de cálculo de Google Sheets.
2. Importa el archivo `torneos.csv` (Archivo → Importar).
3. Mantén los encabezados y el formato de fecha `AAAA-MM-DD`.
4. En Google Sheets: **Archivo → Compartir → Publicar en la web**.
5. Selecciona la pestaña de torneos y formato **Valores separados por comas (.csv)**. Publica y copia la URL CSV.
6. Abre `config.js` y pega la URL en `SHEET_CSV_URL`.
7. Sube el `config.js` actualizado a GitHub.

Columnas:
- `fecha`: AAAA-MM-DD
- `tienda`: nombre de la tienda
- `modalidad`: Challenge, Cup o Especial
- `hora`: por ejemplo 10:00; puede dejarse vacío
- `precio`: por ejemplo 6 €; puede dejarse vacío
- `inscripcion`: URL de inscripción; puede dejarse vacío
- `nombre`: título del evento, por ejemplo Especial Navidad

Cuando edites la hoja publicada, la web leerá los cambios al cargar. Si la hoja no está disponible, mostrará los datos de ejemplo incluidos en `app.js`.

## Enlaces pendientes
En el listado original solo se facilitaron enlaces de inscripción para Empire Games (21/11/2026) y Jupiter (22/11/2026). Los demás eventos se muestran sin enlace hasta que se añadan.

## Personalización pendiente
- Sustituir el enlace de WhatsApp en `config.js`.
- Confirmar direcciones exactas de las tiendas si se quiere añadir mapa/localización.
- Añadir enlaces y precios/horarios que falten.
