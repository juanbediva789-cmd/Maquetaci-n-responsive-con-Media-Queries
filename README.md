# MurciaGram — El Pinterest de la Región de Murcia

Plataforma web de inspiración visual centrada en el patrimonio histórico, natural y gastronómico de los municipios de la Región de Murcia.

## Características principales

- **HTML5 semántico y SEO**: estructura basada en `<header>`, `<nav>`, `<main>`, `<aside>` y `<footer>`, con configuración de `viewport`, meta-etiquetas de indexación (`index, follow`), descripción y Open Graph.
- **Diseño Mobile-First y sintaxis de rangos CSS3**:
  - **Móvil (`< 600px`)**: disposición en una sola columna con Flexbox.
  - **Tableta (`>= 600px` y `<= 800px`)**: cuadrícula de dos columnas.
  - **Escritorio (`> 800px`)**: layout en CSS Grid con cabecera, menú lateral (`<aside>`), galería fluida y pie de página.
- **Estética y microinteracciones**: tarjetas con bordes redondeados, sombras, transiciones suaves, efecto permanente al interactuar con el botón de acción y *overlay* estilo Pinterest con texto descriptivo, botón de «Me gusta» y enlace a la web oficial del municipio.
- **Optimización de imágenes**: uso de `<picture>` con variantes adaptables y `loading="lazy"`.
- **Vista de impresión (`@media print`)**: oculta elementos de navegación e interacción, aplica fondo blanco y optimiza el contenido para papel.
- **Preparación para JavaScript**: tarjetas preparadas mediante variables/propiedades de ordenación (`order`) para su futura reordenación dinámica.

## Preparación de imágenes y automatización

Las imágenes originales se guardan en `assets/raw/` y las versiones optimizadas se generan en `assets/img/` mediante **ImageMagick** (por ejemplo, `400px` de ancho para móvil y `1000px` de ancho para escritorio).

*(Si has configurado `.vscode/tasks.json`, indica aquí cómo ejecutar la tarea desde VS Code, por ejemplo con `Ctrl + Shift + B` o `Terminal > Run Task...`)*:

```bash
magick assets/raw/lorca.jpg -resize 400x -quality 80 assets/img/lorca-mobile.jpg
magick assets/raw/lorca.jpg -resize 1000x -quality 85 assets/img/lorca-desktop.jpg
