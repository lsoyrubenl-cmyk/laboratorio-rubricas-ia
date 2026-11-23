# Staging SCORM 1.2

Esta carpeta contiene la copia autocontenida de publicación. La fuente editable se mantiene en `../src`.

`imsmanifest.xml` está en la raíz del paquete y declara el SCO con `index.html` como punto de inicio. Las hojas de estilo y el JavaScript están declarados como recursos del SCO y se empaquetan al mismo nivel.

Para futuras ediciones, modifica primero `/src`, sincroniza sus archivos a `/scorm`, revisa que cada ruta del manifiesto exista y vuelve a generar el ZIP con el manifiesto y sus recursos en la raíz del archivo.
