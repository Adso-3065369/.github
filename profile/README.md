# 🏢 Organización Fábrica de Software: Sistema ERP/POS

> **ESTADO DE OPERACIÓN:** En Desarrollo Activo (Sprints)
> **CONTEXTO CORPORATIVO Y ACADÉMICO:** Esta organización constituye el entorno de trabajo oficial, la evidencia técnica y el registro auditable para la aprobación de la **Etapa Lectiva (SENA)**. Operamos bajo estándares estrictos de la industria.

---

## 1. Visión General de la Organización

Bienvenidos a la Fábrica de Software encargada del desarrollo del **Sistema de Gestión de Inventario y Ventas (ERP/POS)** con Control de Acceso Granular (RBAC). 

Esta organización no es un ejercicio aislado; es un entorno de producción simulado que requiere rigor absoluto. Nuestra arquitectura está desacoplada y se divide en **dos repositorios principales**, los cuales deben operar en perfecta sincronía:

*   📦 **`Backend`**: Contiene la lógica de negocio, el diseño de la base de datos, la API RESTful y la capa de seguridad y autenticación.
*   🖥️ **`Frontend`**: Contiene la interfaz de usuario (SPA), el consumo de la API, el manejo del estado global y el enrutamiento protegido.

## 2. Estructura de Equipos (Squads) y Gobernanza

Para garantizar la calidad y mantener el control sobre ambos repositorios, el talento humano de esta organización está estrictamente dividido en **cuatro equipos de trabajo funcionales**. Cada integrante tiene permisos y responsabilidades limitadas a su rol:

### 2.1. Liderazgo Técnico (Tech Leads)
Estos equipos tienen permisos de escritura/administración sobre las ramas protegidas (`develop`, `main`). Son los garantes de la arquitectura y la gobernanza.
*   🛡️ **Tech Leads - Backend:** Responsables de auditar la lógica del servidor, aprobar migraciones, validar la seguridad de los Endpoints y fusionar (Merge) el código hacia la rama principal del backend.
*   🛡️ **Tech Leads - Frontend:** Responsables de auditar la UX/UI, asegurar la adaptabilidad (Mobile-First), validar el consumo correcto de la API y fusionar (Merge) el código hacia la rama principal del frontend.

### 2.2. Equipos de Desarrollo (Developers)
Estos equipos construyen el software. **Tienen prohibido integrar código directamente.** Su trabajo finaliza al abrir un Pull Request (PR) hacia `develop`.
*   💻 **Desarrolladores - Backend:** Encargados de programar controladores, modelos y rutas en el repositorio del backend basándose en los *Issues* asignados.
*   💻 **Desarrolladores - Frontend:** Encargados de maquetar componentes, vistas y conectar los servicios en el repositorio del frontend basándose en los *Issues* asignados.

## 3. Políticas de Ingeniería y Estándares Operativos

El acceso a esta organización es un privilegio. El incumplimiento de las siguientes directivas resultará en el rechazo del código durante la fase de *Code Review*.

### 3.1. Flujo de Trabajo y Trazabilidad (Issues y PRs)
*   **Cero Código Huérfano:** Queda estrictamente prohibida la "programación fantasma". Todo código subido a cualquier repositorio debe estar justificado por un *Issue* oficial dentro de nuestro tablero Kanban corporativo.
*   **Trazabilidad:** Todo Pull Request debe enlazarse automáticamente a su tarea utilizando palabras clave (ej. `Closes #ID`).

### 3.2. Estrategia de Ramas (GitFlow Simplificado)
El modelo de *Forks* está deshabilitado. Se trabaja clonando directamente los repositorios corporativos utilizando las siguientes nomenclaturas:
*   `main`: Producción. Intocable para los desarrolladores.
*   `develop`: Rama de integración. Destino de todos los Pull Requests.
*   `feature/nombre-de-la-tarea`: Para desarrollo de nuevas características.
*   `fix/nombre-del-error`: Para corrección de bugs o fallos reportados.

### 3.3. Convención de Commits
La historia de ambos repositorios debe ser una línea de tiempo auditable. Es obligatorio el uso de **Conventional Commits**:
*   `feat:` Nueva funcionalidad.
*   `fix:` Solución a un error.
*   `docs:` Cambios en documentación.
*   `refactor:` Mejoras de código sin alterar su comportamiento externo.

## 4. Onboarding: ¿Cómo iniciar tu trabajo?

Si fuiste asignado a uno de los cuatro equipos, sigue este protocolo para iniciar tu primera tarea:

1.  **Tablero Ágil:** Ingresa a la pestaña *Projects* de esta organización. Revisa el *Sprint* activo y asígnate un *Issue* correspondiente a tu área (Backend o Frontend).
2.  **Clonación del Repositorio Correspondiente:** Dependiendo de tu equipo, clona únicamente el repositorio que te corresponde intervenir.
```bash
    git clone [URL_DEL_REPOSITORIO_FRONTEND_O_BACKEND]
    cd [NOMBRE_DEL_REPOSITORIO]
```
3.  **Sincronización y Rama:**
```bash
    git checkout develop
    git pull origin develop
    git checkout -b feature/ID-tu-tarea
```
4.  **Criterios de Aceptación:** Antes de solicitar un *Code Review*, asegúrate de cumplir al 100% con el *Definition of Done* (Criterios de Aceptación) estipulado en tu *Issue*.

---

> ⚖️ **Aviso Oficial de Evaluación:** 
> Esta Fábrica de Software opera con exigencias reales de la industria. Su historial de Commits, la respuesta a las observaciones de sus Tech Leads, la limpieza de su código y la disciplina en los flujos ágiles constituyen la evidencia legal y técnica para la validación de su **Etapa Lectiva**. 
> 
> *El fracaso controlado y la refactorización son parte del aprendizaje; sin embargo, la violación a la gobernanza técnica aquí descrita será penalizada.*
