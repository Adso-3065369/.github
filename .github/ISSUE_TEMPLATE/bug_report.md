---
name: "Reporte de Bug"
about: Documenta un fallo en el sistema con evidencia técnica y pasos exactos.
title: "fix: [Descripción corta del error en el módulo X]"
labels: "bug, triage"
assignees: ''
---

> **ADVERTENCIA TÉCNICA:** Un bug sin pasos de reproducción exactos, datos de prueba y evidencia visual será cerrado inmediatamente. No asumas la causa ni programes por intuición, describe el comportamiento real con datos. Borra los textos en cursiva antes de enviar.

## 1. Contexto de Ejecución (Entorno)
* **Rama / Versión:** *Ejemplo: develop (commit a1b2c3d) o feature/POS-carrito*
* **Sistema Operativo:** *Ejemplo: Windows 11 / Ubuntu 22.04*
* **Navegador y Versión:** *Ejemplo: Chrome 120 / Firefox 115*
* **Resolución de Pantalla:** *Ejemplo: 1920x1080 (Desktop) / 390x844 (Mobile)*

## 2. Severidad e Impacto
*Marca con una 'x' el nivel de criticidad de este fallo para el negocio.*
- [ ] **Crítica (Blocker):** El sistema colapsa completamente o impide el flujo principal de ventas/seguridad.
- [ ] **Alta:** Una funcionalidad importante está rota, no hay forma alternativa de hacerlo.
- [ ] **Media:** Falla una funcionalidad secundaria, pero el usuario puede rodear el problema.
- [ ] **Baja (UI/UX):** Errores visuales, textos desalineados o problemas menores de interfaz.

## 3. Flujo de Reproducción (Anatomía del Fallo)
*Enumera los pasos exactos y milimétricos para detonar el error. Si el revisor no puede replicarlo en 2 minutos, el reporte es inválido.*

**Datos de Prueba Utilizados:** *Ejemplo: Usuario ID 5 (Rol: Cajero), Producto "Teclado Mecánico" (Stock: 0).*

**Pasos:**
1. *Ejemplo: Iniciar sesión con el rol 'Cajero'.*
2. *Ejemplo: Navegar hacia la ruta `/inventario/crear`.*
3. *Ejemplo: Dejar el campo 'Precio' vacío y escribir 'ABC' en 'Cantidad'.*
4. *Ejemplo: Hacer clic en el botón 'Guardar Producto'.*

## 4. Contraste de Expectativas
**Comportamiento Actual (El Error):**
* *Ejemplo: El botón permite múltiples clics, la interfaz se congela sin dar feedback al usuario y la consola arroja un error 500.*

**Comportamiento Esperado (El Contrato Lógico):**
* *Ejemplo: El formulario debería bloquear el botón, validar que 'Cantidad' sea un número, y mostrar un texto en rojo debajo del input indicando el error sin hacer la petición al servidor.*

## 5. Evidencia Técnica Estricta
*Adjunta la información cruda. Arrastra las imágenes o videos directamente aquí.*

- [ ] **Captura de Pantalla o Video:** [Inserta aquí]
- [ ] **Log de Consola Frontend:** *Ejemplo: `Uncaught TypeError: Cannot read properties of undefined (reading 'map') at ProductList.vue:45`*
- [ ] **Respuesta de Red (Network Tab):** *Ejemplo: Petición POST a `/api/products` devolvió código `422 Unprocessable Entity` con payload `{ message: "Validation failed" }`.*

## 6. Definition of Done (Criterios de Aceptación)
*El Pull Request no será aprobado a menos que cumpla estrictamente con esta lista.*
- [ ] *Ejemplo: El botón 'Guardar' se deshabilita tras el primer clic y permanece inactivo mientras la petición está en curso.*
- [ ] *Ejemplo: El campo 'Cantidad' muestra un mensaje de error en rojo si el valor ingresado no es numérico.*
- [ ] *Ejemplo: El flujo completo se puede ejecutar sin que la consola del navegador registre errores.*