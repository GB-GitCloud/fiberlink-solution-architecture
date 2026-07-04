# Business Understanding Report
## Iniciativa 1 – Plataforma de Integración Empresarial

**Documento:** Architecture Brief Analysis
**Fuente:** `docs/03-solution-architecture/requerimientos/01 - integration-platform (iniciativa 1)/README.md`
**Fase:** Deliverable 2 – Requirements Engineering
**Estado:** Análisis previo a generación de requerimientos · Sin modificación de archivos

---

## 1. Business Problem

Fiberlink opera actualmente con múltiples aplicaciones de negocio (CRM, OSS, Facturación, Inventario, ERP, GIS, NMS) que intercambian información mediante **integraciones punto a punto**. Este modelo genera las siguientes consecuencias:

| Síntoma | Impacto |
|---|---|
| Alta dependencia entre sistemas | Un cambio en una aplicación obliga a modificar todos sus consumidores directos |
| Duplicidad de lógica de negocio | La misma regla se implementa en múltiples sistemas, generando inconsistencias |
| Dificultad para incorporar nuevas aplicaciones | Cada nueva integración requiere desarrollo bilateral ad-hoc |
| Elevados costos de mantenimiento | El volumen de integraciones punto a punto escala cuadráticamente con el número de sistemas |
| Baja trazabilidad de transacciones | No existe un punto centralizado desde donde auditar o rastrear los flujos de información |
| Limitada evolución tecnológica | Reemplazar o modernizar un sistema impacta a todos sus integraciones existentes |

El problema es estructural: la ausencia de una capa de integración centralizada hace que el ecosistema tecnológico de Fiberlink sea frágil, costoso y difícil de evolucionar.

---

## 2. Business Objectives

Los objetivos de negocio se derivan directamente de los beneficios esperados declarados en el Architecture Brief:

| ID | Objetivo | Indicador asociado |
|---|---|---|
| OBJ-01 | Reducir el tiempo de integración de nuevas aplicaciones | Tiempo promedio de integración (días) |
| OBJ-02 | Disminuir la complejidad operativa de las integraciones | Integraciones punto a punto eliminadas (cantidad) |
| OBJ-03 | Incrementar la reutilización de servicios de negocio | APIs reutilizadas (%) · Reutilización de servicios (%) |
| OBJ-04 | Mejorar la trazabilidad y auditoría de las integraciones | Incidentes asociados a integraciones (cantidad) · MTTR (min) |
| OBJ-05 | Facilitar la evolución y modernización tecnológica | Nuevos servicios habilitados por período |
| OBJ-06 | Incrementar la agilidad del negocio para habilitar nuevos productos y canales | Integraciones exitosas (%) · Tiempo de respuesta de APIs (ms) |
| OBJ-07 | Garantizar la disponibilidad operativa de la plataforma de integración | Disponibilidad de la plataforma (%) |

---

## 3. Scope

**Dentro del alcance:**

- Diseño e implementación de una Plataforma de Integración Empresarial que actúe como hub central de interoperabilidad.
- Exposición y gobierno de APIs de negocio reutilizables a través de un API Gateway y un Catálogo de APIs.
- Integración de las 7 aplicaciones core: CRM SaaS, OSS, Motor de Facturación, Inventario Oracle, ERP de Equipos, GIS, NMS.
- Integración de los 3 canales digitales: Portal de Clientes, Aplicación Móvil de Clientes, Aplicación Móvil de Vendedores.
- Soporte para comunicación asíncrona mediante un Bus de Eventos (cuando aplique).
- Gobierno del ciclo de vida de APIs: publicación, versionado, seguridad, monitoreo y deprecación.
- Monitoreo y trazabilidad de extremo a extremo de los flujos de integración.

**Fuera del alcance (implícito — no declarado explícitamente en el Architecture Brief):**

- Modificación de la lógica de negocio interna de las aplicaciones core.
- Reemplazo de las aplicaciones core existentes.
- Migración de datos entre sistemas.
- Automatización de procesos operacionales (cubierta por Iniciativa 2).
- Monitoreo de infraestructura y observabilidad centralizada (cubierta por Iniciativa 3).

> **Nota:** Los límites "fuera del alcance" son inferidos del Architecture Brief y de la definición de las otras iniciativas. Deben ser confirmados con el equipo de arquitectura. Se registran como supuestos en la sección 10.

---

## 4. Stakeholders

El Architecture Brief no declara explícitamente los stakeholders. Los siguientes han sido **inferidos** del contexto de negocio y de las aplicaciones y entidades involucradas:

| Stakeholder | Rol | Interés en la iniciativa |
|---|---|---|
| Área de Tecnología / IT | Propietario técnico de la plataforma | Reducir costos de mantenimiento y complejidad operativa |
| Arquitectura Empresarial | Responsable de gobernanza arquitectónica | Estandarizar integraciones y establecer gobierno de APIs |
| Operaciones | Administrador de integraciones en producción | Mejorar monitoreo, trazabilidad y MTTR |
| Desarrollo de Software | Consumidores y productores de APIs | Reducir tiempo de integración de nuevas aplicaciones |
| Negocio / Producto | Habilitadores de nuevos productos y canales | Accelerar el tiempo de lanzamiento de nuevos servicios |
| Clientes finales | Usuarios del Portal y App Móvil | Mejor experiencia derivada de mayor consistencia y disponibilidad |
| Área Comercial | Usuarios de la App Móvil de Vendedores | Acceso confiable y oportuno a información de clientes, productos y contratos |

> **Supuesto [S-01]:** Los stakeholders identificados son inferidos. No existe una declaración explícita en el Architecture Brief. Deben ser validados con el equipo del proyecto.

---

## 5. Business Capabilities

Las capacidades de negocio habilitadas o mejoradas por esta iniciativa, derivadas del Architecture Brief:

| ID | Capacidad | Descripción |
|---|---|---|
| CAP-01 | Integración centralizada de aplicaciones | Capacidad de conectar cualquier aplicación corporativa a través de un hub único |
| CAP-02 | Gobierno de APIs | Capacidad de publicar, versionar, asegurar, monitorear y deprecar APIs de negocio |
| CAP-03 | Comunicación orientada a eventos | Capacidad de publicar y consumir eventos de negocio de forma asíncrona |
| CAP-04 | Trazabilidad de transacciones | Capacidad de rastrear y auditar el flujo de información extremo a extremo |
| CAP-05 | Incorporación ágil de aplicaciones | Capacidad de integrar nuevas aplicaciones sin modificar las existentes |
| CAP-06 | Reutilización de servicios de negocio | Capacidad de exponer servicios consumibles por múltiples aplicaciones y canales |
| CAP-07 | Monitoreo operativo de integraciones | Capacidad de observar el estado, rendimiento y errores de los flujos de integración |

---

## 6. Business Entities

Las 13 entidades de negocio declaradas en el Architecture Brief, con su rol en el contexto de la plataforma:

| Entidad | Descripción funcional |
|---|---|
| Cliente | Persona o empresa que contrata servicios de Fiberlink. Entidad central en CRM y canales digitales |
| Contrato | Acuerdo comercial entre Fiberlink y un cliente. Vincula Cliente, Servicio y Factura |
| Servicio | Servicio de telecomunicaciones contratado por el cliente (fibra, internet, TV, etc.) |
| Producto | Oferta comercial de Fiberlink. Origen de los servicios contratables |
| Orden de Servicio | Solicitud de alta, modificación o baja de un servicio. Activa flujos en OSS, Inventario y ERP |
| Inventario de Red | Registro de los recursos de red disponibles o asignados (nodos, puertos, fibra, etc.) |
| Equipo | Dispositivo físico (ONT, router, switch) asociado a un servicio o cliente |
| Dirección | Ubicación geográfica asociada a un cliente o cobertura de red. Relacionada con GIS |
| Factura | Documento de cobro generado por el Motor de Facturación |
| Pago | Registro de transacción de cobro asociado a una Factura |
| Incidencia | Reporte de falla o solicitud de soporte técnico. Fluye entre CRM, OSS y Técnico |
| Técnico | Personal de campo que ejecuta instalaciones, reparaciones y verificaciones |
| Cobertura | Área geográfica donde Fiberlink puede prestar servicios. Gestionada por GIS |

**Observación:** Las entidades están distribuidas entre múltiples sistemas sin un modelo canónico documentado. La plataforma de integración deberá establecer contratos de datos (canonical data model) para garantizar consistencia en los intercambios.

---

## 7. Applications Involved

### Aplicaciones Core (productores y consumidores de datos)

| Aplicación | Tipo | Rol en la integración |
|---|---|---|
| CRM SaaS | SaaS externo | Gestión de clientes, contratos, incidencias. Consumidor y productor de datos de negocio |
| OSS | Sistema operacional | Gestión de órdenes de servicio, activación y soporte técnico |
| Motor de Facturación | Sistema de facturación | Generación de facturas y gestión de cobros |
| Inventario Oracle | ERP / Base de datos | Gestión de inventario de red y equipos |
| ERP de Equipos | ERP | Gestión del ciclo de vida de equipos físicos |
| GIS | Sistema geoespacial | Gestión de cobertura, direcciones y recursos geográficos |
| NMS | Network Management System | Monitoreo y gestión de la red de telecomunicaciones |

### Canales Digitales (consumidores de APIs)

| Canal | Tipo | Rol |
|---|---|---|
| Portal de Clientes | Web | Autogestión del cliente: consulta de servicios, facturas, incidencias |
| Aplicación Móvil de Clientes | Mobile | Autogestión móvil del cliente |
| Aplicación Móvil de Vendedores | Mobile | Gestión comercial en campo: consulta de productos, clientes, cobertura |

### Componentes de la Plataforma de Integración (nuevos o a implementar)

| Componente | Función |
|---|---|
| API Gateway | Exposición, seguridad, control de acceso y throttling de APIs |
| Hub de Integración Empresarial | Orquestación y mediación de los flujos de integración entre aplicaciones |
| Catálogo de APIs | Publicación, documentación y descubrimiento de APIs disponibles |
| Bus de Eventos | Publicación y consumo de eventos de negocio de forma asíncrona (condicional) |

**Observación:** El Architecture Brief declara el Bus de Eventos como "cuando aplique", lo que implica que su inclusión depende de la identificación de flujos con valor asíncrono real. Esto deberá resolverse mediante un ADR.

---

## 8. Existing Integrations

El Architecture Brief **no documenta las integraciones punto a punto existentes** de forma explícita. Solo describe el estado actual como un modelo P2P genérico. Sin embargo, es posible inferir integraciones probables a partir de las entidades y aplicaciones involucradas:

| Integración probable (AS-IS inferida) | Entidades involucradas |
|---|---|
| CRM ↔ OSS | Cliente, Contrato, Orden de Servicio, Incidencia |
| CRM ↔ Motor de Facturación | Cliente, Contrato, Factura, Pago |
| OSS ↔ Inventario Oracle | Orden de Servicio, Inventario de Red, Equipo |
| OSS ↔ ERP de Equipos | Equipo, Orden de Servicio |
| OSS ↔ GIS | Dirección, Cobertura |
| OSS ↔ NMS | Incidencia, Servicio |
| Portal de Clientes ↔ CRM | Cliente, Contrato, Incidencia |
| Portal de Clientes ↔ Motor de Facturación | Factura, Pago |
| App Móvil de Vendedores ↔ CRM | Cliente, Producto, Cobertura |

> **Supuesto [S-02]:** El mapa de integraciones AS-IS es inferido. El Architecture Brief no incluye un inventario de integraciones existentes. Este inventario es un dato crítico para dimensionar el alcance real de la iniciativa y estimar el esfuerzo de migración desde el modelo P2P. Su ausencia es registrada en la sección 14.

---

## 9. Risks

| ID | Riesgo | Probabilidad | Impacto | Mitigación sugerida |
|---|---|---|---|---|
| RSK-01 | El CRM es SaaS externo — las capacidades de integración (webhooks, APIs, conectores) dependen del proveedor y pueden estar limitadas o tener costos adicionales | Media | Alto | Verificar el catálogo de integración del CRM SaaS antes de diseñar los flujos |
| RSK-02 | Inventario Oracle y ERP de Equipos son sistemas legacy que pueden no exponer APIs REST estándar | Media | Alto | Evaluar necesidad de adaptadores o conectores propietarios |
| RSK-03 | Sin un inventario explícito de integraciones P2P existentes, el esfuerzo de migración puede subestimarse | Alta | Alto | Levantar el inventario AS-IS antes de iniciar el diseño de la plataforma |
| RSK-04 | El Bus de Eventos introduce complejidad operativa si se adopta sin justificación clara | Media | Medio | Definir mediante ADR los flujos que requieren comunicación asíncrona |
| RSK-05 | La adopción del Catálogo de APIs requiere disciplina organizacional — sin gobierno activo, se vuelve obsoleto rápidamente | Media | Medio | Definir un proceso de gobierno del ciclo de vida de APIs desde el inicio |
| RSK-06 | Los canales digitales (Portal, Apps Móviles) pueden tener integraciones directas con sistemas core que deberán migrarse a pasar por el API Gateway | Media | Medio | Incluir canales digitales en el inventario AS-IS |
| RSK-07 | La plataforma de integración se convierte en un punto único de falla si no se diseña con alta disponibilidad | Alta | Crítico | Definir SLA de disponibilidad de la plataforma y requerimientos de resiliencia como NFR prioritario |

---

## 10. Assumptions

| ID | Supuesto | Impacto si es incorrecto | Requiere validación |
|---|---|---|---|
| S-01 | Los stakeholders identificados son inferidos del contexto. No están declarados en el Architecture Brief | Podría haber requisitos de negocio no capturados | Sí — validar con el equipo |
| S-02 | El mapa de integraciones AS-IS es inferido. No existe un inventario oficial de integraciones punto a punto | Podría subestimarse el alcance real de la migración | Sí — crítico para Deliverable 3 |
| S-03 | El Bus de Eventos será incluido en la arquitectura cuando existan flujos con valor asíncrono demostrable | Si todos los flujos son síncronos, el Bus de Eventos no forma parte del alcance | Sí — requiere ADR |
| S-04 | Las aplicaciones core exponen o pueden exponer APIs consumibles por la plataforma de integración | Sistemas legacy pueden requerir adaptadores no contemplados | Sí — afecta el diseño técnico |
| S-05 | La plataforma de integración es nueva (greenfield). No existe una plataforma de integración previa a reemplazar | Si existe una plataforma legada, el esfuerzo de migración aumenta significativamente | Sí — validar con el equipo |
| S-06 | El alcance excluye la modificación de lógica de negocio interna de las aplicaciones core | Si se requieren cambios en los sistemas fuente, el alcance es significativamente mayor | Sí — confirmar límites del alcance |

---

## 11. Constraints

| ID | Restricción | Origen |
|---|---|---|
| CON-01 | El CRM es un sistema SaaS — no es modificable. La integración debe realizarse dentro de los límites de la API del proveedor | Naturaleza del sistema |
| CON-02 | Las aplicaciones core (Inventario Oracle, ERP de Equipos) son sistemas existentes cuya arquitectura de integración está definida por el proveedor | Naturaleza del sistema |
| CON-03 | La plataforma de integración debe ser el mecanismo oficial de intercambio — no se permiten nuevas integraciones punto a punto | Objetivo de la iniciativa |
| CON-04 | La plataforma debe soportar tanto comunicación síncrona (APIs REST) como asíncrona (eventos) | Architecture Brief |
| CON-05 | Las APIs deben ser seguras, gobernadas y publicadas en un catálogo | Architecture Brief |
| CON-06 | La plataforma debe ser escalable, desacoplada y observable | Architecture Brief (atributos explícitos del objetivo) |
| CON-07 | El cloud provider preferido es Microsoft Azure | `.ai/context.md` y `.ai/architecture.md` |

---

## 12. Opportunities

| ID | Oportunidad | Descripción |
|---|---|---|
| OPP-01 | Modelo canónico de datos de negocio | La implementación de la plataforma es una oportunidad para definir un modelo de datos canónico (Canonical Data Model) que estandarice las entidades de negocio entre todos los sistemas |
| OPP-02 | API como producto | Las APIs publicadas pueden convertirse en activos reutilizables que aceleren futuros proyectos y habiliten ecosistemas digitales (partners, canales terceros) |
| OPP-03 | Base para Iniciativas 2 y 3 | La Plataforma de Integración es la infraestructura habilitadora tanto de la Automatización Operacional (Iniciativa 2) como de la Plataforma de Observabilidad (Iniciativa 3), lo que maximiza su valor estratégico |
| OPP-04 | Gobierno de APIs como capacidad organizacional | El Catálogo de APIs y los procesos de gobierno asociados pueden convertirse en una capacidad organizacional duradera, más allá del alcance técnico de esta iniciativa |
| OPP-05 | Reducción de deuda técnica | Eliminar integraciones punto a punto reduce la deuda técnica acumulada y facilita la modernización incremental de los sistemas core |
| OPP-06 | Habilitación de analítica y eventos de negocio | El Bus de Eventos, si se implementa, sienta las bases para capacidades de analítica en tiempo real y procesamiento de eventos de negocio en el futuro |

---

## 13. Quality Attributes Implied by the Architecture Brief

El Architecture Brief no declara NFRs explícitamente, pero los siguientes atributos de calidad están **implícitos** en el objetivo, los beneficios esperados y los indicadores declarados:

| Atributo | Evidencia en el Architecture Brief | Implicación para los NFR |
|---|---|---|
| **Disponibilidad** | Indicador: "Disponibilidad de la Plataforma de Integración (%)" | Se requiere un SLA de disponibilidad medible. La plataforma es crítica para todas las integraciones |
| **Rendimiento** | Indicador: "Tiempo promedio de respuesta de APIs (ms)" | Se requiere un umbral de latencia para las APIs publicadas |
| **Escalabilidad** | Objetivo explícito: "arquitectura escalable" | La plataforma debe soportar crecimiento en volumen de transacciones y número de integraciones |
| **Seguridad** | Objetivo explícito: "segura y gobernada" | Se requieren mecanismos de autenticación, autorización y cifrado (OAuth2, OIDC per policy) |
| **Mantenibilidad** | Beneficio: "facilite la administración, monitoreo y mantenimiento" | Se requiere observabilidad operativa de la plataforma de integración |
| **Trazabilidad** | Beneficio explícito: "monitoreo, auditoría y seguimiento de extremo a extremo" | Logs de auditoría y correlación de transacciones son requeridos |
| **Resiliencia** | RSK-07: punto único de falla | Recuperación ante fallos, reintentos y circuit breakers deben ser NFRs explícitos |
| **Interoperabilidad** | Objetivo completo de la iniciativa | La plataforma debe soportar múltiples protocolos y estilos de integración |
| **Gobernabilidad** | Objetivo explícito: "modelo de gobierno basado en APIs y eventos" | Se requieren capacidades de gestión del ciclo de vida de APIs |

---

## 14. Missing Information for Requirements Engineering

La siguiente información no está disponible en el Architecture Brief y su ausencia representa una limitación para la definición completa de los requerimientos:

| ID | Información faltante | Impacto | Recomendación |
|---|---|---|---|
| GAP-01 | **Inventario de integraciones punto a punto existentes (AS-IS)** | Sin este inventario es imposible determinar el alcance real de la migración ni establecer criterios de aceptación para la eliminación de P2P | Levantar el inventario antes de Deliverable 3 |
| GAP-02 | **Volumetría de transacciones** | Sin datos de volumen (transacciones por segundo, picos de carga, datos por mensaje) no es posible definir NFRs de rendimiento y escalabilidad con valores objetivos | Obtener datos operacionales del equipo técnico |
| GAP-03 | **SLA objetivo de disponibilidad** | El Architecture Brief menciona disponibilidad como indicador pero no declara el valor objetivo (99.9%, 99.99%, etc.) | Definir el SLA objetivo con el negocio |
| GAP-04 | **Capacidades de integración del CRM SaaS** | El CRM es un sistema externo SaaS. Sus mecanismos de integración disponibles (APIs, webhooks, conectores) no están documentados | Revisar la documentación técnica del proveedor del CRM |
| GAP-05 | **Restricciones técnicas de Inventario Oracle y ERP de Equipos** | No se conoce si estos sistemas exponen APIs estándar o requieren conectores especiales (JDBC, adaptadores propietarios, etc.) | Relevamiento técnico de los sistemas legacy |
| GAP-06 | **Criterios de priorización de integraciones** | No se indica qué integraciones deben implementarse primero — si todas tienen la misma prioridad o si existe una secuencia de migración recomendada | Definir prioridades con el negocio y operaciones |
| GAP-07 | **Modelo de seguridad y autenticación requerido** | El Architecture Brief menciona "segura y gobernada" pero no especifica los mecanismos requeridos (OAuth2, API Keys, mTLS, etc.) | Definir política de seguridad de APIs con el área de seguridad |
| GAP-08 | **Stakeholders formales y sus responsabilidades** | No existe una declaración formal de stakeholders ni sus niveles de aprobación | Validar con el equipo del proyecto |
