# ![](https://github.com/unix4you2/practico/raw/master/img/logo.png) Foto digitalizada

Este es un proyecto derivado de [Práctico Framework](https://www.practico.org) articulable como plugin o complemento

Pruébalo en línea directamente en [Este enlace](https://unix4you2.github.io/pco-foto-digitalizada/). Si se requiere implementación directa desde otro sistema revise la sección de "Uso" más adelante.

Una herramienta simple que permite capturar desde la cámara web un fragmento de un tamaño específico y transportarlo como archivo JPG a un endpoint de servidor especificado.

Ideal para integrarse en flujos de trabajo de documentos digitales, formularios web o sistemas ERP que requieran captura de imágenes.


---

## 🌟 Características

- ✅ Acceso a cámara web con solicitud de permisos
- 🎯 Marco de captura fijo de **135px × 167px** centrado
- 📷 Captura y recorte automático de la región delimitada
- 🖼️ Conversión a formato JPG (calidad 85%)
- 📤 Envío POST a URL personalizada con FormData
- 📎 Parámetros configurables por URL: `documento` y `servidor`
- 🎨 Interfaz moderna, responsive y amigable
- 🔄 Botón de reintento si falla la cámara
- 🧭 Compatibilidad con móviles y escritorio
- 🛡️ Manejo robusto de errores y mensajes claros

---

## 🚀 Requisitos

- Navegador moderno (Chrome, Firefox, Edge, Safari)
- Acceso a cámara web
- **Servidor HTTP local o remoto** (no funciona con `file://`)
- JavaScript habilitado

---

## 🚀 Uso

1. Sube los archivos del proyecto a tu servidor web (o usa GitHub Pages).
2. Accede a la página con los parámetros `documento` y `servidor` en la URL:  https://unix4you2.github.io/pco-foto-digitalizada/?documento=XXXXXXX&servidor=https%3A%2F%2Fnombrehost.tudominio.com%2Ferp%2Fsig%2Fendpoint.php

2.a. Reemplace XXXXXXX por el documento o llave unica que necesita su sistema para guardar finalmente la captura

2.b. Asegurese de codificar su URL de endpoint antes de enviarla como parametro, Ejemplo de encodeURIComponent("https://servidor.tudominio.com/erp/sig/endpoint.php") Sería: servidor=https%3A%2F%2Fnombrehost.tudominio.com%2Ferp%2Fsig%2Fendpoint.php


## IMPORTANTE

Puede requerir que en tu endpoint encargado de almacenar la firma final agregues un  
`header("Access-Control-Allow-Origin: https://unix4you2.github.io");`  ó  `header("Access-Control-Allow-Origin: *"); //Más inseguro`

Así pues, a manera de ejemplu su endpoint podría ser algo como:

``
header("Access-Control-Allow-Origin: https://unix4you2.github.io"); //Posible * en lugar del dominio, aunque mas inseguro
if (move_uploaded_file($_FILES['userfile']['tmp_name'], "archivo.jpg"))
  echo "[OK] Archivo almacenado en el servidor";
else
  echo "[ERROR] En archivo (origen/destino)";
``

## Contribuciones

Las contribuciones son bienvenidas. Para contribuir:

- Hacer fork del proyecto.
- Crear una rama nueva para tus cambios.
- Enviar pull requests con descripciones claras.
- Reportar issues y bugs en el repositorio.

## Licencia

Ver archivo LICENSE para detalles.

---

#### Soporte y donaciones al proyecto

Si encuentra útil este proyecto y deseas contribuir al desarrollo del mismo puede apoyarnos con un valor voluntario.

💵 Usando GitHub Sponsors para tus [Donaciones](https://github.com/sponsors/unix4you2/)
