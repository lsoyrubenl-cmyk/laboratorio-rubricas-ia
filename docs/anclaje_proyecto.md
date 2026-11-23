# Anclaje del proyecto: Objeto de Aprendizaje

## Objetivo

Construir un Objeto de Aprendizaje (OA) altamente visual e interactivo, compatible con SCORM 1.2 y Moodle, para que docentes aprendan a crear rúbricas de evaluación con inteligencia artificial y a utilizarlas con agentes que revisen entregas estudiantiles de manera estructurada.

## Enfoque didáctico y visual

- El OA se estructura como un Tutorial Guiado e Interactivo por módulos (Paso 1, Paso 2, Paso 3), con walkthrough tipo “Haz clic y aprende”.
- Módulo 1: creación de rúbricas en interfaz web o Word con asistentes, prompt, criterios, niveles y simulador de prueba.
- Módulo 2: carga de la rúbrica en agentes de Copilot, Gemini y Codex; instrucciones y archivos de conocimiento.
- Módulo 3: simulación de evaluación de una entrega, análisis con evidencia y validación docente.
- Las simulaciones visuales se acercan a patrones reconocibles: Word con cinta, hoja y panel lateral editable; chat web con historial y respuesta-tabla; Copilot/Gemini como configuración de agente y Codex como proyecto con archivos y consola.
- Cada módulo incluye el botón “¿Qué estoy viendo aquí?” que abre un explicador lateral, enumera la lógica técnica/pedagógica y resalta elementos de la simulación.
- Todo el tutorial se simula localmente en HTML/CSS/JavaScript; no depende de servicios externos. Las maquetas son educativas, no reproducciones oficiales exactas.
- Aprendizaje guiado mediante simuladores paso a paso, tarjetas, comparativas y decisiones prácticas.
- Retroalimentación inmediata, indicadores de estado y semáforos para hacer visibles la calidad de una rúbrica y el avance.
- Evitar muros de texto: mostrar instrucciones breves y contenido progresivo.
- Diseñar con navegación clara y estados accesibles, adaptable a escritorio y móvil.

## Herramientas contempladas

- Interfaces web de IA para redactar, revisar y mejorar rúbricas.
- Microsoft Word con complementos o asistentes de IA.
- Copilot, Gemini y Codex como asistentes para crear rúbricas y como plataformas para configurar agentes evaluadores.

## Lógica de evaluación con agentes

El agente recibirá una rúbrica explícita y la entrega del alumno. Deberá evaluar criterio por criterio usando niveles y descriptores observables, justificar cada nivel con evidencia localizada en la entrega, calcular el resultado según ponderaciones y producir retroalimentación accionable. La persona docente revisará y validará el resultado; el agente apoya el juicio profesional y no lo sustituye. Se deberán cuidar privacidad, sesgos, transparencia y consistencia.

## Estructura de trabajo

- `/docs`: anclajes y documentos de cada fase.
- `/src`: HTML, CSS, JavaScript y datos del simulador.
- `/scorm`: recursos del paquete SCORM 1.2, incluido `imsmanifest.xml`.
- `/dist`: destino del ZIP final para Moodle, que se generará después del anclaje de la Fase 1.

## Anclaje de Fase 1

**Estado: ANCLADA · 23 de noviembre de 2026.** La Fase 1 queda documentada en [`fase-01.md`](fase-01.md) y reflejada en `/src`. Se fijó el tutorial de tres módulos: creación de la rúbrica en interfaz web o Word con asistente; carga como conocimiento e instrucciones en agentes; y evaluación simulada de una entrega con evidencia y revisión docente. Se establecieron las maquetas locales para Copilot, Gemini y Codex, un explicador lateral para cada módulo con resaltado de componentes, la regla de no enviar datos a servicios de IA y el adaptador SCORM 1.2 con respaldo local.

## Estado de fases

| Fase | Estado | Anclaje |
|---|---|---|
| Fase 1: tutorial guiado e interactivo | **ANCLADA · 23-11-2026** | Alcance y arquitectura fijados en [`fase-01.md`](fase-01.md); prototipo en `/src` |
| Base técnica y visual | Reestructurada | Walkthrough por pasos, simulaciones y conector SCORM 1.2 en `/src` |
| Fase 2 y fases posteriores | Pendientes | Profundizar contenidos, validar duración y resultados, ampliar pruebas de rúbrica/agente y documentar accesibilidad y privacidad |
| Paquete SCORM/Moodle | Preparado | Manifiesto y recursos autocontenidos en `/scorm`; ZIP generado en `/dist/OA_Rubricas_IA_SCORM12.zip`. Pendiente importar en Moodle para validar seguimiento en LMS real |

## Pendientes para fases siguientes y empaquetado

- Validar perfil, duración estimada (20–30 minutos) y resultados de aprendizaje con personas docentes.
- Completar actividades, criterios de logro y evidencias para cada módulo.
- Revisar accesibilidad, privacidad y tratamiento de entregas antes de ampliar escenarios.
- Importar el paquete en Moodle de prueba y confirmar lanzamiento, guardado de estado, finalización y reanudación con el runtime real.
- Para futuras ediciones, actualizar primero `/src`, luego sincronizar los archivos publicados dentro de `/scorm` y regenerar el ZIP manteniendo `imsmanifest.xml` en la raíz del paquete.

> Este documento registra el anclaje y el estado vigente del proyecto. Actualizarlo al cerrar fases posteriores, conservando decisiones, cambios y pendientes.
