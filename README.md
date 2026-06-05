# Paquete de Activos de Lumina (Lumina Online Gallery Manifest Package)

Este paquete contiene la estructura de archivos necesaria para inicializar el catálogo online de **Lumina v1.4.0**.

## Contenido del Paquete
- `wallpapers_manifest.json`: El archivo que contiene la base de datos de fondos disponibles, sus etiquetas, categorías, dimensiones y URLs de descarga.
- `thumbnails/`: Carpeta destinada a guardar las imágenes de vista previa (thumbnails) en formato JPG/PNG.
- `videos/`: Carpeta destinada a guardar los fondos animados en formato MP4.
- `images/`: Carpeta destinada a guardar los fondos de pantalla estáticos en formato JPG/PNG.

---

## Instrucciones para subir a GitHub y Activar la Galería Online

Sigue estos pasos para subir los activos y hacer que Lumina los descargue correctamente:

### Paso 1: Crear el repositorio en GitHub
1. Inicia sesión en tu cuenta de GitHub.
2. Crea un nuevo repositorio público con el nombre exacto: `lumina-assets`.
   * **IMPORTANTE:** El repositorio debe ser **público** para que Lumina pueda descargar los archivos sin requerir autenticación.
   * No agregues un archivo `.gitignore` ni `LICENSE` durante la creación (puedes hacerlo después).

### Paso 2: Subir los archivos del paquete
1. Sube todo el contenido de esta carpeta (`lumina-assets-package`) al repositorio `lumina-assets` que acabas de crear.
2. Asegúrate de mantener la estructura de carpetas:
   ```
   ├── wallpapers_manifest.json
   ├── README.md
   ├── thumbnails/
   │   └── (imágenes de vista previa)
   ├── videos/
   │   └── (archivos de video .mp4)
   └── images/
       └── (imágenes estáticas)
   ```

### Paso 3: Confirmar la URL pública del Manifiesto
1. Una vez subidos los archivos, confirma que puedes acceder al archivo JSON crudo (raw) abriendo la siguiente URL en tu navegador:
   https://raw.githubusercontent.com/nike-ai/lumina-assets/main/wallpapers_manifest.json
   *(Reemplaza `nike-ai` con tu nombre de usuario de GitHub si tu cuenta es diferente).*
2. Verifica que la página devuelve el texto JSON completo con los tres elementos de ejemplo y no un error HTTP 404.

### Paso 4: Reemplazar los archivos multimedia de ejemplo
Los archivos subidos en las carpetas `thumbnails/`, `videos/` e `images/` contienen marcadores `.gitkeep`. Para que las descargas funcionen en Lumina, debes subir archivos de imagen o video reales que coincidan exactamente con los nombres especificados en el manifiesto JSON:
- En `thumbnails/`:
  - `cyberpunk_city.jpg`
  - `nature_lake.jpg`
  - `anime_girl.jpg`
- En `videos/`:
  - `cyberpunk_city.mp4`
  - `anime_girl.mp4`
- En `images/`:
  - `nature_lake.jpg`

*Nota: Si prefieres usar tus propios nombres de archivo, edita `wallpapers_manifest.json` y actualiza las propiedades `"thumbnailUrl"` y `"downloadUrl"` correspondientes antes de subir el manifiesto.*

---

## Cómo Probar en Lumina

1. Abre la aplicación **Lumina**.
2. Ve a la sección **Galería Online** en el panel lateral izquierdo.
3. Si habías abierto la página antes y se mostraba un mensaje de error, presiona el botón **Reintentar** o simplemente reinicia la aplicación.
4. Los fondos configurados en el manifiesto remoto (`Cyberpunk City Lights`, `Tranquil Nature Lake`, `Anime Girl in Rain`) aparecerán en la cuadrícula de forma inmediata.
5. Puedes usar la barra de búsqueda superior y los filtros por categoría (Anime, Naturaleza, Cyberpunk) para comprobar que la lógica de filtrado dinámico responde correctamente.
