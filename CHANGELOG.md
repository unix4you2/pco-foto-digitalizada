Todos los cambios importantes en este proyecto se documentarán en este archivo.

El formato sigue las convenciones de [Keep a Changelog](https://keepachangelog.com) y utiliza [Semantic Versioning](https://semver.org).

---

## [1.0.2] - 2025-04-18

### 🐛 Correcciones

- Corrección crítica: Mejora del manejo de errores al acceder a la cámara con mensajes específicos por tipo de error (`NotAllowedError`, `NotFoundError`, etc.).
- Solución para dispositivos móviles: Se añadió `facingMode: { ideal: "environment" }` para intentar usar la cámara trasera.
- Corrección en el cálculo del recorte de imagen: Ahora se ajusta correctamente al tamaño del contenedor del video, respetando el aspect ratio.
- Se agregó `muted` al elemento `<video>` para evitar problemas de reproducción automática en algunos navegadores.

### ✨ Mejoras

- Se añadió botón de "Reintentar cámara" visible cuando falla la inicialización.
- Mejor feedback visual: mensajes de permiso, estado de carga y éxito/fracaso más claros.
- Se añadió registro detallado en consola (`console.log`, `console.error`) para facilitar el diagnóstico.
- Se estableció un servidor de prueba por defecto (`https://httpbin.org/post`) si no se proporciona el parámetro `servidor`.
- Mejora en la UX: el botón de captura se deshabilita hasta que la cámara esté lista.
- Manejo de visibilidad de pestaña: pausa/reanuda el video si el usuario cambia de pestaña.

### 🧪 Pruebas

- Probado en Chrome, Firefox y Edge en entorno local.
- Validación de parámetros faltantes con valores por defecto.

---

## [1.0.1] - 2025-04-17

### 🐛 Correcciones

- Se corrigió el cálculo de coordenadas para el recorte de la imagen, que no funcionaba correctamente en todos los tamaños de pantalla.
- Se solucionó el problema de envío de FormData: ahora se envía correctamente el parámetro `documento` junto con el archivo.
- Se añadió manejo de errores en la petición `fetch` para mostrar mensajes amigables.

### ✨ Mejoras

- Se añadió animación de carga durante el envío.
- Mejora en el estilo del marco de captura: ahora incluye indicador visual "Centra el documento aquí".
- Se optimizó la calidad JPEG al 85% para balancear tamaño y calidad.

---

## [1.0.0] - 2025-04-16

### 🎉 Lanzamiento inicial

- Implementación básica de la aplicación web de captura de documento.
- Características principales:
  - Recepción de parámetros `documento` y `servidor` vía URL.
  - Solicitud de acceso a cámara web.
  - Vista de cámara con marco de captura de 135x167px.
  - Botón "Capturar" que recorta y envía la imagen en formato JPG.
  - Envío mediante POST a URL especificada con FormData.
- Interfaz moderna responsive con CSS.
- Validación básica de parámetros.

---

## Próximas versiones (Roadmap)

### 🚀 2.0.0 (planeado)

- Soporte para múltiples intentos de captura con vista previa.
- Compresión configurable de imagen.
- Validación de orientación y nitidez antes de enviar.
- Modo selfie/cámara frontal como alternativa.
- Soporte para PWA (instalable en móvil).
- Internacionalización (i18n).

---

Puedes guardar este contenido como `CHANGELOG.md` en la raíz de tu proyecto. Es un estándar ampliamente adoptado que facilita el seguimiento de cambios para ti y cualquier otro desarrollador que trabaje en el proyecto.

¿Quieres que lo formatee también en otro formato (como JSON, TXT o con emojis diferentes)? ¡Solo dime!
