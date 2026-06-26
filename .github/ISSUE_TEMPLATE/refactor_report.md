---
name: "Tarea de Refactorización (Refactor)"
about: "Mejora de calidad interna del código sin alterar el comportamiento externo del sistema."
title: "refactor: [Módulo o archivo a refactorizar]"
labels: "refactor"
assignees: ""
---

> **ADVERTENCIA TÉCNICA — REGLA DE ORO DEL REFACTOR:**
> Un refactor **únicamente mejora la estructura interna del código**. Está **terminantemente prohibido**:
> - Modificar, agregar o eliminar lógica de negocio.
> - Cambiar el comportamiento observable del sistema (inputs, outputs, efectos secundarios).

---

## 1. Contextualización del Refactor

*¿Qué módulo, archivo o componente se va a refactorizar? ¿Por qué el código actual necesita intervención?*

**Archivo(s) o módulo(s) afectados:**
*Ejemplo: `src/controllers/ConfigurationController.js`, `src/components/header.js`*

**Problema técnico identificado:**
*Ejemplo: El controlador concentra lógica de presentación, acceso a datos y manejo de errores en un único método de 120 líneas, violando el principio de responsabilidad única (SRP).*

**Motivación / Deuda técnica:**
*Ejemplo: Durante la revisión del PR #47, el Tech Lead señaló que la función `cargarConfiguracion()` mezcla llamadas fetch con manipulación del DOM. Esto dificulta las pruebas unitarias y el mantenimiento.*

**¿Existe un issue, PR o comentario de revisión que origine esta tarea?**
*Ejemplo: Comentario de Juan David en PR #47 — "Separar la lógica de negocio de la capa de presentación."*

**Confirmación de alcance — marcar antes de continuar:**
- [ ] Confirmo que este refactor **NO modifica la lógica de negocio** del módulo afectado.
- [ ] Si encontré un bug durante el análisis, lo reporté en un issue separado y 

---

## 2. Análisis del Código Actual

*Describe el estado actual del código antes de intervenir. Sé específico: nombres de funciones, patrones problemáticos, métricas si las hay.*

**Fragmento o descripción del código problemático:**
```
// Pega aquí el fragmento actual que se va a refactorizar, o describe la función/clase con su firma.
// Ejemplo:
// function cargarConfiguracion() {
//   fetch('/api/config').then(r => r.json()).then(data => {
//     document.querySelector('#nombre').value = data.nombre; // ← mezcla fetch + DOM
//   });
// }
```

---

## 3. Solución Técnica Propuesta

*Describe cómo quedará el código después del refactor. Incluye el patrón o técnica que se aplicará.*

> **Restricción:** Las técnicas listadas a continuación solo deben mejorar la **estructura, legibilidad y organización** del código. Ninguna debe alterar algoritmos, condiciones, validaciones, cálculos ni flujos de datos existentes.

**Técnica de refactorización a aplicar:**
- [ ] **Extract Function / Extract Method** — separar bloques de código en funciones con nombre claro.
- [ ] **Extract Module / Extract File** — mover responsabilidades a un archivo separado.
- [ ] **Rename Variable / Rename Function** — mejorar la legibilidad con nombres descriptivos.
- [ ] **Replace Magic Numbers/Strings** — usar constantes nombradas.
- [ ] **Introduce Parameter Object** — agrupar parámetros relacionados en un objeto.
- [ ] **Remove Dead Code** — eliminar código que no se ejecuta ni usa.
- [ ] **Invert Dependencies (DI)** — inyectar dependencias en lugar de instanciarlas directamente.
- [ ] **Consolidar lógica duplicada** — crear una función/módulo reutilizable.
- [ ] Otro: *especificar*

**Descripción del estado final esperado:**
*Ejemplo: La función `cargarConfiguracion()` delegará el fetch a `ConfigurationService.js` y la actualización del DOM quedará en `ConfigurationController.js`, respetando la separación de capas definida en la arquitectura del proyecto.*

**¿Qué permanece exactamente igual después del refactor?**
*Ejemplo: Las rutas de la API consumidas, los parámetros aceptados por cada función, los valores retornados, y los eventos disparados al DOM — nada de esto cambia.*

**Archivos nuevos que se crearán (si aplica):**
*Ejemplo: `src/services/ConfigurationService.js` — encapsula todas las llamadas a `/api/config`.*

**Archivos que se eliminarán (si aplica):**
*Ejemplo: `src/utils/helperViejo.js` — su lógica se migra a `src/utils/formatters.js`.*

---

## 4. Alcance y Archivos Involucrados

**¿El refactor impacta la interfaz pública de algún módulo (exports, nombres de funciones llamadas desde otros archivos) imagenes antes y despues?**
- [ ] Sí — se debe notificar al equipo y actualizar todos los puntos de uso antes del PR.
- [ ] No — los cambios son internos al módulo.

## 5. Definition of Done (Criterios de Aceptación)

*El Pull Request **no será aprobado** a menos que se cumplan **todos** los criterios marcados. El Tech Lead verificará cada punto durante la revisión.*

- [ ] **[CRÍTICO]** La lógica de negocio es **idéntica** antes y después del refactor — ningún algoritmo, condición, validación ni cálculo fue modificado.
- [ ] **[CRÍTICO]** El comportamiento externo del sistema es **idéntico** — mismos inputs producen exactamente los mismos outputs y efectos secundarios.
- [ ] **[CRÍTICO]** Los bugs encontrados durante el análisis fueron reportados en issues separados y **no fueron corregidos en este PR**.
- [ ] Se ha abierto un Pull Request con título en formato `refactor: [descripción breve]` apuntando a la rama de integración correcta.
- [ ] El PR incluye una descripción que explica **qué** se cambió y **por qué**, con referencias al código anterior y al nuevo estado.
- [ ] El PR ha sido **revisado y aprobado por el Tech Lead** antes de hacer merge.
- [ ] Este issue ha sido **cerrado y vinculado** al PR mediante `Closes #[número_de_issue]` en la descripción del PR.

