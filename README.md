# Dashboard Programa de Juventudes · Parche Zipa

Dashboard interactivo y autocontenido para visualizar y monitorear las estadísticas del **Programa de Juventudes** de Zipaquirá, Cundinamarca.

## 🚀 Publicar en GitHub Pages

1. Crea un repositorio nuevo en GitHub (puede ser público o privado).
2. Sube el archivo `index.html` a la raíz del repositorio (puedes arrastrarlo directamente desde la interfaz web de GitHub, "Add file" → "Upload files").
3. Ve a **Settings → Pages**.
4. En "Build and deployment", selecciona **Deploy from a branch**.
5. Elige la rama `main` (o `master`) y la carpeta `/ (root)`.
6. Guarda. En 1-2 minutos tu dashboard estará disponible en una URL como:
   `https://tu-usuario.github.io/tu-repositorio/`

No se necesita ningún paso de compilación (build): es un solo archivo HTML autocontenido.

## 📊 Cómo actualizar los datos

El dashboard funciona 100% en el navegador, sin servidor ni base de datos:

- Ve a la pestaña **"Actualizar Datos"** dentro del dashboard.
- Arrastra o selecciona el nuevo archivo Excel (`.xlsx`) con las hojas `PLANILLAS`, `EMPRENDEDORES` y `ATENCIONES PSICOSOCIALES`.
- Todos los indicadores, gráficos y tablas se recalculan automáticamente en el navegador del usuario.
- **Importante:** esta actualización es temporal mientras el navegador esté abierto. Si quieres que el cambio sea permanente para todos los usuarios, debes regenerar el archivo `index.html` con los nuevos datos ya incrustados (puedes pedirle a Claude que lo haga de nuevo con el Excel actualizado) y volver a subirlo a GitHub.

## 🔒 Políticas de datos aplicadas

- **Rango de edad:** solo se contabilizan jóvenes de **14 a 28 años**. Los rangos "12 a 17 Años" y "18 a 28 Años" del Excel se incluyen porque contienen edades dentro de esa franja.
- **No duplicación de población:** cada joven (identificado por su número de documento) se cuenta **una sola vez por mes**, incluso si participó en varias actividades. Los "jóvenes nuevos" mensuales se calculan comparando contra todos los meses anteriores, para que un joven que ya apareció en febrero no se vuelva a contar como "nuevo" en marzo.
- **Casa de la Juventud:** las atenciones psicosociales realizadas en sede se integran como una actividad más dentro del listado de actividades de la Casa de la Juventud, sin duplicar jóvenes que ya estén contados en otras actividades del mismo mes.
- **Semilleros:** se agrupan automáticamente por responsable — Marketing Digital (Nicolás), Liderazgo (Valentina) y Psicosocial (Alexis) — sumando todas las personas y temas de cada responsable. Los semilleros de Programación e Inteligencia Artificial aparecen marcados como pendientes por activar mientras no tengan registros en el Excel.
- **Ganadores de Jóvenes Tiburones:** el Excel actual no incluye esta información, así que cada hoja de vida de emprendedor tiene un control editable (Sí/No + año) para que el equipo del programa marque manualmente a los ganadores directamente en el dashboard.

## 🎨 Identidad visual

Colores tomados de las marcas Parche Zipa (azul eléctrico, amarillo, verde) y Jóvenes Tiburones (morado, verde, blanco), aplicados de forma armónica en toda la interfaz.

## 🛠️ Tecnologías

- HTML + CSS + JavaScript puro (sin frameworks)
- [Chart.js](https://www.chartjs.org/) para las visualizaciones
- [SheetJS (xlsx)](https://sheetjs.com/) para leer archivos Excel directamente en el navegador

Todo el código, los logos y los datos están incrustados en el único archivo `index.html`, por lo que el dashboard funciona sin conexión a internet una vez cargado (excepto por las dos librerías cargadas vía CDN al abrir la página).
