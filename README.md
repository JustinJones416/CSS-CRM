# CSS Nexus AI

CRM sanitario conceptual para la Caja de Seguro Social de Panamá (CSS). Prototipo funcional de un CRM centrado en el paciente, construido como aplicación de página única en un solo archivo `index.html`, sin frameworks ni backend, pensado para demostrar cómo un CRM puede centralizar y mejorar el recorrido del paciente a través de preconsulta, cita, consulta, documentos, medicamentos y seguimiento.

**Entorno de demostración.** Todos los datos son sintéticos y están claramente etiquetados como tal. El prototipo no representa información institucional, médica ni de inventario real de la CSS, y no implementa autenticación, cifrado ni RBAC real en esta fase.

## Tecnología

- HTML5, CSS3 y JavaScript vanilla, sin frameworks ni bundlers.
- Persistencia local mediante `localStorage`, encapsulada en una capa `StorageService` propia.
- Tipografía DM Sans y DM Mono empaquetadas en base64 dentro del propio archivo, sin dependencias externas de red.

## Cómo probarlo

1. Descarga o clona el repositorio.
2. Abre `index.html` directamente en el navegador. No requiere instalación ni servidor.
3. Selecciona un rol de demostración para ingresar al CRM.

## Roles de demostración

Paciente, Médico, Especialista, Recepción, Farmacia y Administrador. El selector de rol sustituye temporalmente la autenticación real y determina qué módulos y acciones quedan visibles.

## Arquitectura

El archivo mantiene separación lógica interna aunque sea un único documento:

```
index.html
├── <head>      metadata y fuentes embebidas
├── <style>     variables, reset, layout, componentes, formularios, tablas, modales, responsive
└── <script>
    ├── StorageService     capa única de acceso a localStorage
    ├── PatientService     lógica de pacientes
    ├── TimelineService    eventos del historial de cada paciente
    ├── AppointmentService lógica de agenda y citas
    ├── AppState           estado central de la sesión
    ├── Router              navegación entre vistas sin recarga
    └── UI / Modal / Toast  componentes reutilizables
```

La arquitectura queda preparada para, en fases posteriores, separar `frontend/`, `backend/`, `database/` y `ai-services/` como proyectos independientes.

## Licencia y alcance

Proyecto académico y conceptual. No apto para uso clínico real. Cualquier funcionalidad de inteligencia artificial incluida en fases posteriores actuará únicamente como apoyo informativo, nunca como sustituto del criterio profesional.
