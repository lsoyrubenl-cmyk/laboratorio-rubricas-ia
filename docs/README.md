# Documentación del OA · Rúbricas con IA

## Punto de partida

- [`anclaje_proyecto.md`](anclaje_proyecto.md): estado del proyecto, decisiones y próximos pasos.
- [`fase-01.md`](fase-01.md): especificación anclada del tutorial, módulos, simulaciones, explicador global, comportamiento offline y arquitectura.

## Recorrido del OA

1. **Crear la rúbrica:** interfaz web o Word con asistente; estructurar el prompt, criterios, niveles y ponderaciones; probar el borrador.
2. **Cargarla en un agente:** establecer reglas de evaluación en instrucciones, adjuntar la rúbrica como conocimiento y proporcionar la entrega en el contexto de cada revisión.
3. **Evaluar una entrega:** el agente consulta la rúbrica, localiza evidencia, compara descriptores y genera nivel, puntaje provisional y retroalimentación. La persona docente verifica citas y cálculo, y valida la salida.

El botón **“¿Qué estoy viendo aquí?”** ofrece en cada módulo una explicación paso a paso de la lógica pedagógica/técnica y permite resaltar elementos de la interfaz simulada.

## Offline y SCORM 1.2

Las simulaciones usan HTML, CSS y JavaScript local. No hay solicitudes a servicios de IA ni dependencias de fuentes remotas. Si el OA no encuentra la API de Moodle, conserva la sesión en `localStorage`. En Moodle, el conector busca `window.API` y comunica estado, ubicación y datos de suspensión con la API SCORM 1.2.

La carpeta `/scorm` es una copia de publicación autocontenida; el origen editable se mantiene en `/src`. El manifiesto `scorm/imsmanifest.xml` usa rutas relativas a la raíz del paquete. El ZIP conserva ese manifiesto y todos los archivos indicados en el mismo nivel, sin anidar la carpeta `scorm`.

## Estructura de archivos

```text
docs/
  README.md
  anclaje_proyecto.md
  fase-01.md
src/                         # fuente editable
  index.html
  styles.css
  mockups.css
  explainer.css
  app.js
scorm/                       # staging autocontenido para empaquetar
  imsmanifest.xml
  index.html
  styles.css
  mockups.css
  explainer.css
  app.js
dist/
  OA_Rubricas_IA_SCORM12.zip
```

## Flujo para futuras ediciones

1. Modificar y revisar primero la fuente en `/src`.
2. Sincronizar los cinco recursos de `/src` a `/scorm`; mantener el manifiesto en la raíz de `/scorm`.
3. Confirmar que `href` y todos los elementos `<file>` del manifiesto apunten a archivos existentes en la raíz.
4. Regenerar el ZIP con `imsmanifest.xml` y sus recursos en la raíz del archivo comprimido.
5. Importar en Moodle de prueba y validar lanzamiento, progreso, reanudación y finalización. Esa validación con un LMS real queda pendiente.

## Publicación web en GitHub Pages

El workflow [`.github/workflows/pages.yml`](../.github/workflows/pages.yml) publica únicamente `./src` como raíz del sitio cada vez que se actualiza esa carpeta en `main`, y permite ejecuciones manuales. Para usarlo, configura **Settings → Pages → Build and deployment → Source: GitHub Actions** en el repositorio. Las rutas CSS y JavaScript son relativas al `index.html`, por lo que funcionan cuando `/src` se publica en la raíz del artifact de Pages.

El proyecto necesita inicializarse/enlazarse al remoto de GitHub desde una terminal si no hay una conexión de GitHub disponible en Codex. `gh` no está instalado en el entorno actual. Consulta la documentación oficial de GitHub Pages sobre [workflows personalizados](https://docs.github.com/en/pages/getting-started-with-github-pages/using-custom-workflows-with-github-pages).
