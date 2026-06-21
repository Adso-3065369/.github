> **DETENTE Y LEE ANTES DE ABRIR ESTE PR:** > Todo código enviado a integración debe cumplir estrictamente con el *Definition of Done* de la tarea asignada. Como desarrollador, tu responsabilidad es garantizar que el código compila, está limpio y fue probado. **Tienes estrictamente prohibido aprobar o fusionar (Merge) tu propio Pull Request.** Borra las instrucciones en cursiva antes de guardar.

## 1. Descripción del Cambio
*Resumen técnico de qué hace este código, cómo lo hace y por qué es necesario.*

## 2. Tipo de Cambio (Conventional Commits)
- [ ] **feat:** Nueva funcionalidad o módulo.
- [ ] **fix:** Corrección de un error o vulnerabilidad.
- [ ] **refactor:** Reestructuración de código (optimización sin cambios visuales o funcionales).
- [ ] **docs/style:** Cambios en documentación o formato de código (Linting/Prettier).

## 3. Trazabilidad del Tablero (Obligatorio)
**Vínculo al Issue:** Closes # [Inserta aquí el número de tu Issue, ej: Closes #15]

---

## 4. Checklist del Desarrollador (Definition of Done)
*Debes marcar TODAS las casillas de la sección Universal y de tu área (Frontend o Backend) para que el Tech Lead inicie la revisión.*

### 🌐 Calidad Universal
- [ ] **Sincronización:** He actualizado mi rama local con `origin/develop` (git pull origin develop) y he resuelto cualquier conflicto de integración.
- [ ] **Seguridad:** El código NO contiene credenciales quemadas, tokens, contraseñas ni archivos `.env`.
- [ ] **Limpieza:** He eliminado todos los `console.log`, `print()`, `dd()` y código comentado muerto.
- [ ] **Estándares:** Todas las funciones y métodos complejos están documentados usando JSDoc u otro estándar aplicable.

### 🖥️ Validación FRONTEND (Si aplica)
- [ ] **Responsive (Mobile-First):** La interfaz no se desborda y es 100% usable en resoluciones móviles y de escritorio.
- [ ] **UX/UI Segura:** No hay alertas nativas del navegador (`alert`, `confirm`). Todo se maneja mediante componentes (Modales/Toasts).
- [ ] **Componentización:** El código no está en un solo archivo masivo; se separó lógicamente en componentes reutilizables.

### ⚙️ Validación BACKEND (Si aplica)
- [ ] **Seguridad de Rutas (RBAC):** Se han validado explícitamente los roles requeridos para acceder a los endpoints modificados.
- [ ] **Manejo de Errores:** Se implementaron bloques `try/catch` y el servidor nunca devuelve un error 500 por mala validación de datos.
- [ ] **Pruebas de API:** He probado las rutas localmente (Postman/Thunder Client) y retornan los códigos HTTP y payloads correctos.

---

## 5. Evidencia de Trabajo (Auditoría)
*La evidencia es obligatoria. Arrastra directamente tus capturas de pantalla o videos cortos aquí.*

* **Frontend:** *Capturas del antes y el después, o GIF de la funcionalidad operando.*
* **Backend:** *Captura de la terminal corriendo las pruebas, o screenshot de Postman mostrando el Status 200 OK y el JSON de respuesta.*

## 6. Análisis de Impacto (Dependencias)
*¿Este cambio requiere que tus compañeros o los Tech Leads ejecuten alguna acción adicional al descargar esta rama?*
- [ ] Requiere instalar nuevas dependencias (`npm install` / `composer install`).
- [ ] Requiere agregar nuevas variables al archivo `.env`.
- [ ] Requiere ejecutar nuevas migraciones o seeders en la Base de Datos.
- [ ] No requiere acciones adicionales.

---

## 🛡️ ZONA EXCLUSIVA PARA TECH LEADS (Code Review)
*El Líder Técnico asignado debe verificar lo siguiente antes de aprobar el Merge.*
- [ ] El código cumple con la arquitectura estipulada y no rompe principios SOLID básicos.
- [ ] La evidencia técnica coincide con los Criterios de Aceptación del Issue.
- [ ] (Aprobación Final) El código está listo para integrarse a `develop`.