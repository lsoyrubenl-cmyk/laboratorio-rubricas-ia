# Fase 1 · Tutorial guiado e interactivo

**Estado:** ANCLADA  
**Fecha de anclaje:** 23 de noviembre de 2026  
**Referencia:** esta especificación fija la arquitectura y el alcance de la Fase 1 para continuar el proyecto sin perder sus decisiones.

## Propósito

Convertir el prototipo del OA en un recorrido práctico de tres módulos. La persona participante aprende haciendo, con una simulación de pantalla por paso, controles que cambian el contenido al instante y avance explícito mediante “Siguiente paso”. El flujo no conecta con servicios de IA: muestra escenarios didácticos autocontenidos.

## Público y enfoque

- Público: docentes que necesitan crear criterios de evaluación y usar asistentes generativos para apoyar la revisión de entregas.
- Enfoque: demostración breve, decisión o manipulación, retroalimentación inmediata y reflexión docente.
- Duración: autoguiada; estimación inicial de 20–30 minutos, pendiente de validar.
- Responsabilidad: el agente produce análisis provisional con evidencia; la persona docente valida la calificación y decide la retroalimentación.

## Resultados de aprendizaje propuestos

Al completar el recorrido, la persona participante podrá:

1. Redactar y revisar una instrucción para generar una rúbrica analítica alineada con una tarea, con criterios y niveles observables.
2. Ubicar una rúbrica como referencia y configurar instrucciones de evaluación para un agente, distinguiendo instrucciones permanentes, archivos de conocimiento y entregas.
3. Revisar un resultado de agente, comprobar citas y puntajes contra la rúbrica, y validar o corregir la salida antes de usarla.

## Estructura del tutorial

### Módulo 1 · Creación de la rúbrica en los entornos

1. **Elige tu entorno:** selección entre interfaz web y Word con asistente; elección de Copilot, Gemini o Codex; la pantalla simulada cambia con la selección.
2. **Escribe el prompt:** explora contexto, tarea, criterios y formato. El ejemplo pide al asistente que pregunte si falta información.
3. **Ajusta criterios y niveles:** edición de criterios, selección de tres o cuatro niveles y actualización de una vista de rúbrica.
4. **Evita errores frecuentes:** criterio ambiguo, niveles repetidos y pesos arbitrarios, con una corrección sugerida para cada caso.
5. **Probar en simulador:** seleccionar una tarea, editar un criterio, nivel y ponderación; observar la asignación provisional. La práctica es necesaria para completar el módulo.

### Módulo 2 · Cómo cargar la rúbrica en un agente

1. **Elige la plataforma:** Copilot, Gemini o Codex en una maqueta seleccionable. Se aclara que nombres y opciones cambian por versión, plan y organización.
2. **Ubica la rúbrica:** separa instrucciones del agente, archivo de conocimiento con la rúbrica y entrega que se adjunta por evaluación.
3. **Instruye contra invenciones:** prompt reutilizable que exige evidencia localizada, impide inventar criterios/pesos, declara falta de evidencia, muestra el cálculo y requiere validación docente.

### Módulo 3 · Uso práctico del agente evaluador

1. **Selecciona la entrega:** dos archivos ficticios, uno con evidencia suficiente y otro incompleto, y selección del agente.
2. **Observa y valida:** animación de lectura de rúbrica, búsqueda de evidencia y asignación de nivel; presenta puntaje provisional y retroalimentación. Lista de revisión docente y acción explícita de validación.

## Interacciones y seguimiento

- Navegación lateral por módulos y botones de paso anterior/siguiente.
- Barra segmentada de progreso del módulo y porcentaje de módulos completados.
- Entorno y plataforma alteran las maquetas visibles; opciones y campos actualizan el ejemplo de rúbrica.
- La práctica del módulo 1 debe ejecutarse para completar el módulo; el módulo 3 requiere validar el resultado.
- El conector registra ubicación, estado y datos de suspensión en SCORM 1.2 (Moodle); sin API SCORM, usa almacenamiento local sin bloquear el tutorial.

## Explicador contextual para participantes

El botón global **“¿Qué estoy viendo aquí?”** está disponible en cada módulo. Abre un panel lateral con explicaciones breves, lista navegable de temas y una acción para resaltar el elemento descrito en la simulación. El panel responde al módulo activo:

- **Módulo 1:** desglosa contexto, tarea, criterios y formato del prompt; explica qué hace observable un descriptor y cómo cambian los flujos web y Word.
- **Módulo 2:** distingue instrucciones del agente, archivo de conocimiento y entrega; explica cómo restringir la evaluación a criterios y evidencias disponibles.
- **Módulo 3:** guía la lectura de la entrega, localización de evidencia, correspondencia con niveles, cálculo provisional y validación docente.

La explicación orienta a la persona participante y resalta componentes locales; no realiza llamadas a IA ni altera el progreso del tutorial.

## Criterios de diseño de las simulaciones

- **Word con asistente:** la simulación presenta barra de título y pestañas de Word (Archivo, Inicio, Insertar, Disposición, Referencias, Revisar y Vista), cinta de herramientas, hoja centrada con borrador de rúbrica y panel lateral acoplado. El panel permite elegir Copilot, Gemini o Codex, escoger una instrucción predefinida o escribir una, y aplicar un cambio local que actualiza y resalta celdas del documento. La maqueta se adapta a pantallas estrechas apilando panel y documento.
- **Interfaz web de IA:** muestra historial de conversaciones, selector de modo, mensaje del usuario, respuesta estructurada con una mini tabla y acciones para copiar, refinar o continuar con el borrador.
- **Copilot y Gemini como agentes:** la maqueta muestra configuración, instrucciones, rúbrica cargada en conocimiento y una conversación de prueba con archivo de entrega.
- **Codex:** la maqueta muestra un espacio de proyecto con explorador de `rubrica.md`, `entrega_alumno.md` y `AGENTS.md`; para evaluar, la salida estructurada aparece en una consola simulada.
- Las pantallas son simulaciones didácticas locales, inspiradas en patrones reconocibles; no son capturas exactas ni prometen nombres o ubicaciones vigentes de controles reales.
- La disponibilidad de complementos y funciones depende de la cuenta, plan, versión y entorno. En particular, Codex o Gemini dentro de Word se representan como flujos con archivos/asistentes y no como complementos universales.
- HTML, CSS y JavaScript simulan todas las respuestas localmente; no llaman a servicios de IA ni requieren APIs externas. El código usa fuentes del sistema para que la presentación no dependa de fuentes remotas.
- El simulador no transmite tareas ni datos a un modelo; usa ejemplos ficticios.
- El agente debe citar evidencia vinculada con criterio y descriptor. Ante ausencia de evidencia, debe abstenerse y solicitar revisión.

## Arquitectura del prototipo

- [`src/index.html`](../src/index.html): estructura de la aplicación, navegación por módulos, regiones de lección y progreso, botón y panel global del explicador.
- [`src/styles.css`](../src/styles.css): sistema visual general, tarjetas, navegación, diseños responsivos y componentes didácticos.
- [`src/mockups.css`](../src/mockups.css): estilos para las pantallas simuladas de Word, chat web y espacios de agente/proyecto.
- [`src/explainer.css`](../src/explainer.css): panel lateral, controles y resaltado guiado de la interfaz.
- [`src/app.js`](../src/app.js): contenido y estados del walkthrough, explicaciones por módulo, interacciones, progreso y conector SCORM 1.2.
- [`scorm/imsmanifest.xml`](../scorm/imsmanifest.xml): manifiesto con punto de inicio y recursos en rutas relativas a la raíz del paquete.

### Regla offline/local y SCORM 1.2

- Las acciones, respuestas, rúbricas de ejemplo y resultados de evaluación se simulan en el navegador con HTML, CSS y JavaScript. No se llama a Copilot, Gemini, Codex ni a APIs de IA externas.
- Los ejemplos son ficticios y no se envían a ningún servicio. El almacenamiento local se usa como respaldo cuando el OA se abre fuera de Moodle.
- En Moodle, el adaptador busca la API SCORM 1.2 y registra ubicación, estado, progreso suspendido y finalización mediante `LMSInitialize`, `LMSSetValue`, `LMSCommit` y `LMSFinish`.
- La compatibilidad funcional del conector está prevista en el diseño; el paquete final y su importación deben validarse en Moodle después de preparar el manifiesto y el ZIP.

## Evidencias de aprendizaje

- Borrador de rúbrica ajustado y aplicado en el simulador.
- Selección de ubicación adecuada para instrucciones y archivo de conocimiento.
- Validación docente del análisis de una entrega de práctica.

## Estado de Fase 1

**ANCLADA.** La estructura de tres módulos, los entornos, las herramientas, el rol de la revisión docente, las simulaciones locales, el explicador contextual y la arquitectura del prototipo quedan establecidos como referencia reutilizable. Cambios posteriores deberán registrarse como decisiones de la fase siguiente o como una revisión explícita de este anclaje.
