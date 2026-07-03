# Iniciativa 1: Plataforma de Integración Empresarial

## Objetivo

Implementar una Plataforma de Integración Empresarial que centralice la interoperabilidad entre las aplicaciones corporativas mediante APIs y eventos, eliminando las integraciones punto a punto y habilitando una arquitectura escalable, desacoplada, segura y gobernada que facilite la transformación digital de Fiberlink.

---

## Problema que resuelve

Actualmente Fiberlink cuenta con múltiples aplicaciones de negocio que intercambian información mediante integraciones punto a punto, generando una alta dependencia entre sistemas, duplicidad de lógica de negocio, dificultades para incorporar nuevas aplicaciones y elevados costos de mantenimiento.

Esta situación incrementa los tiempos de implementación de nuevos proyectos, dificulta la trazabilidad de las transacciones y limita la evolución tecnológica de la organización.

La Plataforma de Integración Empresarial permitirá desacoplar las aplicaciones, estandarizar los mecanismos de integración y establecer un modelo de gobierno basado en APIs y eventos.

---

## Beneficios esperados

- **Reducir el tiempo de integración de nuevas aplicaciones**, mediante la implementación de un Hub de Integración basado en APIs reutilizables y contratos de integración estandarizados.

- **Disminuir la complejidad operativa**, reemplazando las integraciones punto a punto por una plataforma centralizada que facilite la administración, monitoreo y mantenimiento de las integraciones.

- **Incrementar la reutilización de servicios**, publicando APIs de negocio reutilizables que puedan ser consumidas por múltiples aplicaciones y canales digitales.

- **Mejorar la trazabilidad de las integraciones**, incorporando capacidades de monitoreo, auditoría y seguimiento de extremo a extremo para facilitar la identificación y resolución de incidentes.

- **Facilitar la evolución tecnológica**, desacoplando las aplicaciones mediante contratos de integración estables que permitan incorporar, reemplazar o modernizar sistemas sin afectar el resto del ecosistema.

- **Incrementar la agilidad del negocio**, reduciendo el esfuerzo requerido para habilitar nuevos productos, canales digitales y servicios.

---

## Entidades de negocio involucradas

Las principales entidades de negocio que intercambian información a través de la plataforma son:

- Cliente
- Contrato
- Servicio
- Producto
- Orden de Servicio
- Inventario de Red
- Equipo
- Dirección
- Factura
- Pago
- Incidencia
- Técnico
- Cobertura

---

## Aplicaciones involucradas

### Aplicaciones Core

- CRM SaaS
- OSS
- Motor de Facturación
- Inventario Oracle
- ERP de Equipos
- GIS
- NMS

### Canales Digitales

- Portal de Clientes
- Aplicación Móvil de Clientes
- Aplicación Móvil de Vendedores

### Plataforma de Integración

- API Gateway
- Hub de Integración Empresarial
- Catálogo de APIs
- Bus de Eventos (cuando aplique)

---

## Indicadores asociados

| Indicador | Unidad de medida | Descripción |
|-----------|------------------|-------------|
| Tiempo promedio de integración de nuevas aplicaciones | Días | Tiempo requerido para incorporar una nueva aplicación a la plataforma. |
| Integraciones punto a punto eliminadas | Cantidad | Número de integraciones reemplazadas por servicios centralizados. |
| APIs reutilizadas | % de APIs reutilizadas | Porcentaje de APIs consumidas por más de una aplicación. |
| Disponibilidad de la Plataforma de Integración | % de disponibilidad | Porcentaje de tiempo en que la plataforma permanece operativa. |
| Integraciones exitosas | % de transacciones exitosas | Porcentaje de integraciones ejecutadas correctamente respecto al total de transacciones. |
| Tiempo promedio de respuesta de APIs | Milisegundos (ms) | Tiempo promedio de respuesta de las APIs publicadas. |
| Incidentes asociados a integraciones | Cantidad | Número de incidentes relacionados con procesos de integración. |
| Tiempo promedio de resolución de incidentes (MTTR) | Minutos | Tiempo promedio requerido para restaurar un servicio de integración. |
| Nuevos servicios habilitados | Cantidad por período | Número de nuevos servicios o capacidades incorporadas mediante la plataforma de integración. |
| Reutilización de servicios de negocio | % de reutilización | Porcentaje de servicios de negocio utilizados por múltiples consumidores. |

---

## Resultado esperado

La Plataforma de Integración Empresarial constituirá el mecanismo oficial para el intercambio de información entre las aplicaciones corporativas y los canales digitales de Fiberlink, habilitando una arquitectura basada en APIs y eventos que permita mejorar la interoperabilidad, reducir la complejidad tecnológica y acelerar la incorporación de nuevas capacidades de negocio.

---

> **Nota:** Este documento corresponde al *Architecture Brief* de la iniciativa y servirá como insumo para la definición de los Requerimientos Funcionales (RF), Requerimientos No Funcionales (RNF) y Criterios de Aceptación del Entregable 2.