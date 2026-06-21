---
name: "Nueva Funcionalidad (Feature)"
about: "Propuesta para desarrollar una nueva característica o módulo en el sistema."
title: "feat: [Nombre corto y descriptivo del módulo]"
labels: "enhancement, feature"
assignees: ""
---

> **ADVERTENCIA TÉCNICA:** Las funcionalidades no se programan por intuición. Toda nueva característica debe tener un valor de negocio claro y criterios de aceptación definibles. Borra los textos de ejemplo en cursiva antes de enviar.

## 1. Justificación y Valor de Negocio
*¿Por qué necesitamos esto? ¿Qué problema resuelve o qué proceso optimiza?*
**Justificación:** *Ejemplo: Actualmente, los usuarios administradores no tienen forma de saber qué cajero eliminó un producto. Necesitamos una bitácora para garantizar la trazabilidad del inventario.*

## 2. Historia de Usuario (Agile)
*Define quién lo necesita, qué necesita y para qué lo necesita.*
- **Como** *[rol del usuario]*
- **quiero** *[la funcionalidad exacta]*
- **para que** *[el objetivo final y el valor que aporta].*

## 3. Propuesta de Implementación Técnica
*¿Cómo planeas construirlo respetando la separación de responsabilidades?*
**Frontend:**
- *Ejemplo: Crear un nuevo módulo en `src/modules/audit/` con su propia vista.*
- *Ejemplo: Consumir el endpoint mediante el servicio `AuditService`.*

**Backend (Si aplica):**
- *Ejemplo: Crear un middleware que intercepte peticiones `DELETE` y guarde el `user_id`.*

## 4. Dependencias y Bloqueos
*¿Esta funcionalidad requiere que otro equipo termine una tarea primero?*
- [ ] Requiere endpoint del Backend (Issue #___)
- [ ] Requiere diseño UI/UX aprobado
- [ ] Ninguna, se puede iniciar de inmediato.

## 5. Definition of Done (Criterios de Aceptación)
*El Pull Request no será aprobado a menos que cumpla estrictamente con esta lista.*
- [ ] *Ejemplo: La vista solo es accesible para usuarios con el rol `ADMIN`.*
- [ ] *Ejemplo: La tabla incluye paginación en el servidor.*
- [ ] *Ejemplo: El código cumple con las reglas de linting y no tiene console.logs.*