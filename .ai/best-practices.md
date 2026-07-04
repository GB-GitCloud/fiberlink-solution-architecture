# Políticas y Buenas Prácticas para la Colaboración con IA

## Propósito

Este documento reúne las políticas y buenas prácticas adoptadas por el equipo para garantizar una colaboración efectiva entre arquitectos, analistas y asistentes de Inteligencia Artificial (Kiro, ChatGPT o herramientas similares).

Su objetivo es asegurar que los artefactos generados mantengan un alto nivel de calidad, consistencia, trazabilidad y gobernanza durante todo el ciclo de vida del proyecto.

Estas prácticas forman parte de la metodología de trabajo del equipo y deberán aplicarse en todos los entregables del proyecto.

---

# BP-001 – Separar la Documentación en Borrador y Oficial

## Objetivo

Evitar que la IA genere nuevos artefactos utilizando documentación que aún no ha sido revisada o aprobada por el equipo.

## Práctica

Todo documento del proyecto podrá existir en uno de los siguientes estados:

- Borrador
- Oficial

Los documentos en estado de borrador deberán utilizar el sufijo `-draft`.

### Ejemplo

```
functional-requirements-draft.md
```

Los documentos oficiales no deberán incluir dicho sufijo.

### Ejemplo

```
functional-requirements.md
```

## Reglas

- Salvo indicación expresa, la IA siempre deberá utilizar la versión oficial de cada documento.
- Los borradores constituyen insumos de trabajo y no deberán utilizarse como fuente para generar artefactos oficiales.
- La aprobación de un documento deberá realizarse antes de utilizarlo como entrada de la siguiente fase del proyecto.

## Beneficios

- Evita inconsistencias entre documentos.
- Preserva la trazabilidad de los cambios.
- Favorece el trabajo colaborativo.
- Garantiza que la arquitectura se construya sobre información validada.

---

# BP-002 – Realizar Commits por Hitos

## Objetivo

Mantener un historial de Git claro, organizado y fácilmente recuperable.

## Práctica

Realizar un commit cada vez que se complete un hito relevante del proyecto, evitando acumular múltiples cambios no relacionados en un mismo commit.

### Ejemplos

- Inicialización del repositorio.
- Creación de la Base de Conocimiento para la IA.
- Requisitos Funcionales de una iniciativa.
- Requisitos No Funcionales de una iniciativa.
- Criterios de Aceptación.
- Diagramas C4.
- Architecture Decision Records (ADR).

## Reglas

- Cada commit deberá representar un cambio coherente y autocontenido.
- El mensaje del commit deberá describir claramente el objetivo alcanzado.
- Evitar commits que mezclen cambios de diferentes entregables o iniciativas.

## Beneficios

- Facilita la recuperación de versiones anteriores.
- Mejora la trazabilidad.
- Favorece el trabajo colaborativo.
- Mantiene un historial limpio y comprensible.

---

# BP-003 – Verificar el Estado del Repositorio Antes de Generar Artefactos

## Objetivo

Asegurar que el repositorio se encuentra en un estado consistente antes de generar documentación relevante.

## Práctica

Antes de iniciar un nuevo entregable o un artefacto de arquitectura significativo, ejecutar el proceso de inicialización del proyecto mediante el prompt correspondiente.

Durante esta revisión deberán verificarse, como mínimo:

- Organización del repositorio.
- Documentación faltante.
- Inconsistencias detectadas.
- Ambigüedades.
- Dependencias entre documentos.

## Reglas

- No iniciar la generación de un nuevo artefacto si existen inconsistencias críticas sin resolver.
- Registrar las observaciones relevantes antes de continuar con el siguiente paso del workflow.

## Beneficios

- Detecta vacíos de documentación.
- Identifica dependencias arquitectónicas.
- Mejora la calidad del repositorio.
- Evita propagar inconsistencias a los siguientes entregables.

---

# BP-004 – Validar las Observaciones de la IA

## Objetivo

Confirmar las observaciones realizadas por la IA antes de modificar el repositorio o tomar decisiones de arquitectura.

## Práctica

Toda observación realizada por la IA deberá tratarse inicialmente como una recomendación y no como un hecho confirmado.

Cuando la IA informe sobre archivos faltantes, inconsistencias, conflictos o dependencias:

- Verificar manualmente la información.
- Confirmar la situación reportada.
- Ajustar los prompts cuando corresponda.
- Modificar el repositorio únicamente después de la validación del equipo.

## Reglas

- La IA no sustituye el juicio del equipo de arquitectura.
- Ningún cambio estructural deberá realizarse únicamente por recomendación de la IA sin una revisión previa.

## Beneficios

- Reduce cambios innecesarios.
- Incrementa la confiabilidad de los resultados.
- Mejora progresivamente la calidad de los prompts.
- Refuerza la gobernanza del proyecto.

---

# BP-005 – Generar un Artefacto a la Vez

## Objetivo

Mejorar la calidad de la documentación y facilitar su revisión mediante la generación incremental de artefactos.

## Práctica

Cada interacción con la IA deberá enfocarse en la generación de un único artefacto arquitectónico.

### Ejemplos

- Requisitos Funcionales.
- Requisitos No Funcionales.
- Criterios de Aceptación.
- Architecture Decision Record (ADR).
- Diagrama C4 – Nivel 1.
- Diagrama C4 – Nivel 2.
- Diagrama C4 – Nivel 3.

Evitar solicitar la generación de un entregable completo en una única interacción.

## Reglas

- Cada artefacto deberá ser revisado y aprobado antes de generar el siguiente.
- No mezclar diferentes tipos de documentos en una misma generación.
- Mantener una relación clara de entrada y salida entre los artefactos del workflow.

## Beneficios

- Facilita la revisión.
- Reduce el retrabajo.
- Incrementa la consistencia entre documentos.
- Mejora la trazabilidad del proyecto.

---

# BP-006 – Comprensión Antes que Generación

## Objetivo

Garantizar que la IA comprenda el contexto del proyecto antes de generar cualquier artefacto.

## Práctica

Toda nueva sesión de trabajo deberá comenzar con el proceso de inicialización del proyecto.

Antes de generar documentación, la IA deberá comprender como mínimo:

- El contexto del proyecto.
- La política de arquitectura.
- La organización del repositorio.
- El glosario del proyecto.
- La fase actual del workflow.
- Las decisiones de proyecto previamente registradas.

## Reglas

- No generar documentación sin haber inicializado previamente el contexto.
- Si la IA identifica inconsistencias relevantes durante la inicialización, deberá informarlas antes de continuar.

## Beneficios

- Reduce alucinaciones.
- Mejora la calidad de los resultados.
- Incrementa la coherencia entre documentos.
- Disminuye la necesidad de correcciones posteriores.

---

# BP-007 – El Repositorio es la Fuente Única de Verdad

## Objetivo

Asegurar que todos los artefactos generados se fundamenten en la información oficial del proyecto.

## Práctica

El repositorio constituye la fuente oficial de conocimiento del proyecto.

La IA deberá:

- Leer la documentación existente.
- Reutilizar la terminología definida.
- Mantener la trazabilidad entre artefactos.
- Evitar introducir información no documentada.

## Reglas

- Toda decisión deberá basarse en documentación existente o en supuestos explícitamente identificados.
- La conversación con la IA no reemplaza la documentación almacenada en el repositorio.
- Los documentos aprobados prevalecen sobre cualquier información intercambiada durante el chat.

## Beneficios

- Mantiene la consistencia documental.
- Favorece la reutilización del conocimiento.
- Facilita el trabajo colaborativo.
- Reduce la dependencia del contexto conversacional.

---

# BP-008 – Documentar los Supuestos Mediante ADR

## Objetivo

Evitar que los supuestos utilizados durante el análisis se conviertan en decisiones arquitectónicas implícitas.

## Práctica

Cuando sea necesario formular un supuesto para completar un análisis:

- Identificarlo explícitamente.
- Justificar su necesidad.
- Evaluar su impacto potencial.
- Validarlo con el equipo cuando corresponda.

Si dicho supuesto afecta el diseño de la solución, deberá documentarse posteriormente mediante un Architecture Decision Record (ADR).

## Reglas

Los supuestos nunca deberán presentarse como hechos confirmados.

Todo supuesto deberá indicar, cuando sea posible:

- Justificación.
- Impacto.
- Nivel de confianza.
- Estado de validación.

## Beneficios

- Incrementa la gobernanza arquitectónica.
- Mejora la trazabilidad de las decisiones.
- Hace visible la incertidumbre del proyecto.
- Facilita la validación futura.

---

# BP-009 – La IA Debe Comprender el Proyecto Antes de Resolverlo

## Objetivo

Tratar a la IA como un integrante más del equipo de proyecto, capaz de comprender el contexto antes de generar documentación o proponer soluciones.

## Práctica

Antes de generar cualquier artefacto, la IA deberá:

- Leer la Base de Conocimiento de la IA (`.ai`).
- Inspeccionar el repositorio.
- Comprender la fase actual del proyecto.
- Identificar dependencias entre documentos.
- Verificar la consistencia del repositorio.

La generación de documentación solo deberá comenzar una vez que la comprensión del proyecto haya sido confirmada.

## Reglas

- La IA no deberá asumir que conoce el proyecto por conversaciones anteriores.
- El conocimiento deberá obtenerse del repositorio y de la Base de Conocimiento.
- Si la información disponible es insuficiente, la IA deberá indicarlo antes de continuar.

## Beneficios

- Mejora la calidad de los resultados.
- Incrementa el razonamiento arquitectónico.
- Reduce la complejidad de los prompts.
- Produce resultados más consistentes y predecibles.

---

# BP-010 – Mantener una Jerarquía de Decisiones

## Objetivo

Separar las decisiones de gobierno del proyecto de las decisiones de arquitectura y de implementación, preservando la trazabilidad y evitando mezclar responsabilidades.

## Práctica

Las decisiones deberán registrarse de acuerdo con su alcance.

### Decisiones del Proyecto

Se documentarán en:

```
.ai/decisions.md
```

Incluyen aspectos como:

- Organización del repositorio.
- Idioma de la documentación.
- Metodología de trabajo.
- Proveedor de nube seleccionado.
- Estándares de documentación.
- Políticas de colaboración con IA.

### Decisiones de Arquitectura

Se documentarán mediante Architecture Decision Records (ADR).

Ubicación:

```
docs/03-solution-architecture/adr/
```

Ejemplos:

- Estilo de integración.
- Plataforma de APIs.
- Broker de eventos.
- Mecanismo de autenticación.
- Plataforma de observabilidad.

### Decisiones de Implementación

Las decisiones propias de la implementación deberán documentarse en los artefactos técnicos correspondientes y no en las decisiones del proyecto.

## Reglas

- Cada decisión deberá documentarse una sola vez.
- Ninguna decisión deberá registrarse en más de un nivel.
- Las decisiones de implementación no deberán condicionar las decisiones de arquitectura.

## Beneficios

- Claridad en la gobernanza.
- Mejor trazabilidad arquitectónica.
- Separación de responsabilidades.
- Mayor facilidad de mantenimiento.

---

# BP-011 – Un Objetivo por Conversación

## Objetivo

Mantener el foco durante las sesiones de trabajo con la IA y evitar iteraciones innecesarias.

## Práctica

Antes de iniciar una conversación, definir explícitamente un único objetivo.

### Ejemplos

- Completar el repositorio.
- Diseñar el contexto para Kiro.
- Generar los Requisitos Funcionales de una iniciativa.
- Revisar un diagrama C4.
- Elaborar un ADR.

No mezclar diferentes entregables o problemas en una misma conversación.

Cuando el objetivo haya sido alcanzado, iniciar una nueva conversación para abordar el siguiente.

## Reglas

- Cada conversación deberá tener un objetivo claramente definido.
- Si durante la conversación aparece un nuevo problema, deberá registrarse y tratarse en una sesión posterior.
- Evitar cambiar de contexto durante una misma interacción.

## Beneficios

- Reduce cambios de contexto.
- Disminuye la probabilidad de entrar en bucles.
- Facilita la validación de los resultados.
- Produce artefactos más consistentes.

---

# BP-012 – Establecer un Punto de Control Antes de la Ingeniería de Requerimientos

## Objetivo

Asegurar que existe una comprensión suficiente del negocio antes de comenzar la definición de los requisitos.

## Práctica

Todo **Business Understanding Report** deberá finalizar con una evaluación de preparación (*Readiness Assessment*).

Esta evaluación deberá determinar si la iniciativa cuenta con la información necesaria para iniciar la Ingeniería de Requerimientos.

Como mínimo deberá evaluarse:

- Comprensión del problema de negocio.
- Objetivos claramente definidos.
- Alcance identificado.
- Actores involucrados.
- Aplicaciones involucradas.
- Riesgos documentados.
- Supuestos registrados.
- Información faltante.

## Reglas

Los Requisitos Funcionales no deberán generarse hasta que el Business Understanding Report concluya con una recomendación explícita de una de las siguientes opciones:

- **APROBADO**: la iniciativa cuenta con la información suficiente para comenzar la Ingeniería de Requerimientos.
- **REQUIERE ACLARACIONES**: es necesario completar la información antes de continuar.

La decisión deberá quedar documentada como parte del Business Understanding Report.

## Beneficios

- Evita generar requisitos sobre información incompleta.
- Reduce retrabajos.
- Incrementa la calidad de los requisitos.
- Mejora la trazabilidad entre el negocio y la solución.

---

# BP-013 – Respetar la Estructura del Repositorio

## Objetivo

Mantener una estructura única y consistente del repositorio para preservar la trazabilidad y evitar la fragmentación de la documentación.

## Práctica

Al generar o almacenar nuevos artefactos, la IA deberá reutilizar la estructura de carpetas existente.

Los documentos deberán guardarse en la carpeta correspondiente a la iniciativa a la que pertenecen.

La IA no deberá crear nuevas estructuras de directorios salvo que exista una instrucción explícita del equipo.

## Reglas

- Utilizar siempre la estructura oficial del repositorio.
- No crear carpetas paralelas con nombres diferentes para el mismo propósito.
- Cuando exista ambigüedad respecto a la ubicación de un documento, solicitar confirmación antes de crear nuevas carpetas.
- Los nuevos artefactos deberán almacenarse junto a la documentación relacionada de la misma iniciativa.

## Beneficios

- Mantiene una única fuente de verdad.
- Preserva la organización del repositorio.
- Evita documentación duplicada.
- Facilita la navegación y el mantenimiento del proyecto.

---

# BP-014 – Separar el Idioma de los Prompts del Idioma de los Entregables

## Objetivo

Diferenciar el idioma utilizado para interactuar con la IA del idioma utilizado en la documentación oficial del proyecto.

## Práctica

Los prompts podrán redactarse en inglés para optimizar la comprensión de la IA.

Toda la documentación oficial del proyecto deberá redactarse en español.

Los términos técnicos podrán mantenerse en inglés únicamente cuando constituyan un estándar ampliamente aceptado en la industria.

Ejemplos:

- API
- Architecture Decision Record (ADR)
- Event Driven Architecture
- REST
- OAuth
- SLA
- KPI

## Reglas

- No mezclar idiomas dentro de un mismo documento.
- El idioma del prompt y el idioma del artefacto generado son decisiones independientes.
- La política de idioma del proyecto prevalece sobre el idioma utilizado para interactuar con la IA.

## Beneficios

- Mejora la comprensión de la IA.
- Mantiene la consistencia documental.
- Facilita la revisión por parte del equipo.
- Refuerza la gobernanza de la documentación.

---

# BP-015 – Preservar los Borradores Generados por IA

## Objetivo

Conservar los documentos generados por la IA como insumos de trabajo hasta que el equipo apruebe la versión oficial.

## Práctica

Los artefactos generados por la IA deberán mantenerse como borradores mientras dure el proceso de revisión.

La documentación oficial deberá generarse únicamente después de la revisión y aprobación del equipo.

## Flujo

Borrador generado por IA

↓

Revisión del Equipo

↓

Comparación

↓

Integración de observaciones

↓

Documento Oficial

## Reglas

- Los borradores nunca deberán reemplazar automáticamente la documentación oficial.
- Antes de integrar un borrador deberá realizarse una comparación con la versión del equipo.
- La aprobación del equipo constituye el punto de control para convertir un borrador en documento oficial.

## Beneficios

- Favorece el trabajo colaborativo.
- Mantiene la trazabilidad de las modificaciones.
- Reduce el riesgo de pérdida de información.
- Facilita la comparación entre diferentes propuestas.

---

# BP-016 – Documentar Explícitamente los Supuestos

## Objetivo

Permitir el avance del análisis cuando la información disponible sea insuficiente, haciendo visibles todas las hipótesis utilizadas durante el proceso de diseño.

## Práctica

Los supuestos están permitidos siempre que sean necesarios para completar el análisis arquitectónico o de negocio.

Todo supuesto deberá:

- Identificarse explícitamente.
- Justificarse.
- Indicar el impacto esperado.
- Indicar el nivel de confianza.
- Registrarse para su posterior validación.

Cuando un supuesto influya en una decisión arquitectónica, deberá documentarse además mediante un Architecture Decision Record (ADR).

## Reglas

- Los supuestos nunca deberán presentarse como hechos confirmados.
- Todo supuesto deberá ser fácilmente identificable por el equipo.
- Los supuestos deberán revisarse durante las actividades de validación del proyecto.
- Una vez validados, los supuestos deberán convertirse en información oficial o eliminarse si dejan de ser válidos.

## Beneficios

- Permite avanzar aun cuando la información es incompleta.
- Hace visible la incertidumbre del proyecto.
- Mejora la transparencia del proceso de diseño.
- Incrementa la trazabilidad de las decisiones arquitectónicas.

---

# Mejora Continua

Estas políticas y buenas prácticas constituyen un documento vivo.

El equipo deberá revisarlas periódicamente e incorporar nuevas prácticas cada vez que identifique una mejora repetible que incremente la calidad de la colaboración entre los arquitectos y los asistentes de Inteligencia Artificial.

Toda nueva buena práctica deberá:

- Resolver un problema recurrente identificado durante el proyecto.
- Aportar un beneficio medible al proceso de trabajo.
- Ser aplicable de manera consistente por todo el equipo.
- Mantener coherencia con la metodología y el workflow definidos para el proyecto.

La evolución de este documento forma parte del proceso de mejora continua del equipo y constituye un activo de conocimiento reutilizable para futuros proyectos.