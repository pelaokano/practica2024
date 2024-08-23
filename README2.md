# Ejemplo de Diagrama de Flujo con Mermaid

```mermaid
flowchart TD
    A[Inicio] --> B[Analizar Requisitos]
    B --> C{Requisitos Aprobados?}
    C -->|Sí| D[Diseñar Solución]
    C -->|No| E[Revisar Requisitos]
    D --> F[Implementar Solución]
    F --> G[Testear Solución]
    G --> H{Tests Exitosos?}
    H -->|Sí| I[Desplegar en Producción]
    H -->|No| J[Corregir Errores]
    J --> F
    I --> K[Fin]
