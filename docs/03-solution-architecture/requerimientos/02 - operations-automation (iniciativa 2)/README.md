# Iniciativa 2: Automatización Operacional

## Objetivo

Implementar una plataforma de automatización operacional que orqueste los procesos críticos del negocio, reduzca la intervención manual y mejore la eficiencia en la provisión, activación y gestión de los servicios de telecomunicaciones, garantizando trazabilidad, consistencia y cumplimiento de los niveles de servicio (SLA).

---

## Problema que resuelve

Actualmente, Fiberlink ejecuta diversos procesos operacionales mediante actividades manuales entre las aplicaciones CRM, OSS, Inventario, Facturación y ERP, generando retrasos, errores humanos, reprocesos y baja trazabilidad durante el ciclo de vida de atención al cliente.

La ausencia de automatización limita la capacidad de crecimiento del negocio, incrementa los costos operativos y dificulta el cumplimiento de los acuerdos de nivel de servicio.

La Automatización Operacional permitirá orquestar procesos de negocio de extremo a extremo, reduciendo tiempos de ejecución, minimizando errores y mejorando la productividad del personal operativo.

---

## Beneficios esperados

- **Reducir los tiempos de provisión y activación de servicios**, automatizando los flujos operacionales entre las aplicaciones involucradas.

- **Disminuir errores operativos**, eliminando actividades manuales repetitivas mediante procesos orquestados y reglas de negocio automatizadas.

- **Incrementar la productividad del personal operativo**, permitiendo que los equipos se concentren en actividades de mayor valor para el negocio.

- **Mejorar el cumplimiento de los SLA**, reduciendo los tiempos de respuesta y automatizando tareas críticas durante la provisión y soporte de servicios.

- **Incrementar la trazabilidad de los procesos**, registrando cada etapa del flujo operacional para facilitar auditorías y análisis de desempeño.

- **Reducir costos operativos**, disminuyendo el esfuerzo requerido para ejecutar procesos repetitivos y reduciendo reprocesos.

---

## Entidades de negocio involucradas

- Cliente
- Contrato
- Servicio
- Orden de Servicio
- Técnico
- Agenda
- Inventario
- Equipo
- Factura
- Pago
- Incidencia
- Cobertura

---

## Aplicaciones involucradas

### Aplicaciones Core

- CRM SaaS
- OSS
- Inventario Oracle
- Motor de Facturación
- ERP de Equipos
- GIS

### Automatización

- Motor de Workflow
- Motor de Reglas de Negocio
- Plataforma de Integración Empresarial
- Plataforma de Notificaciones

### Canales

- Portal de Clientes
- Aplicación Móvil de Clientes
- Aplicación Móvil de Técnicos
- Aplicación Móvil de Vendedores

---

## Indicadores asociados

| Indicador | Unidad de medida | Descripción |
|-----------|------------------|-------------|
| Tiempo promedio de provisión | Horas | Tiempo promedio requerido para activar un servicio. |
| Procesos automatizados | % de procesos automatizados | Porcentaje de procesos ejecutados automáticamente respecto al total. |
| Errores operativos | % de procesos con error | Porcentaje de procesos que requieren reproceso o intervención manual. |
| Cumplimiento de SLA | % de cumplimiento | Porcentaje de solicitudes atendidas dentro del SLA establecido. |
| Órdenes procesadas automáticamente | % de órdenes | Porcentaje de órdenes ejecutadas sin intervención manual. |
| Productividad operacional | Órdenes por colaborador | Número promedio de órdenes gestionadas por cada colaborador. |
| Tiempo promedio de atención | Minutos | Tiempo promedio requerido para completar un proceso operacional. |
| Reprocesos operativos | % de reprocesos | Porcentaje de procesos que deben ejecutarse nuevamente. |
| Costos operativos | USD por orden | Costo promedio asociado al procesamiento de una orden de servicio. |
| Satisfacción operacional | % de satisfacción | Nivel de satisfacción de las áreas operativas respecto a los procesos automatizados. |

---

## Resultado esperado

La Automatización Operacional permitirá ejecutar procesos de negocio de manera estandarizada, reduciendo tiempos de atención, minimizando errores operativos y mejorando la eficiencia de las operaciones mediante procesos orquestados y automatizados.

---

> **Nota:** Este documento corresponde al *Architecture Brief* de la iniciativa y servirá como insumo para la definición de los RF, RNF y Criterios de Aceptación del Entregable 2.