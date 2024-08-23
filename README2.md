# Ejemplo de Diagrama de Flujo con Mermaid

```mermaid
flowchart TD
    A[Inicio de la función] --> B[Inicializar Winsock]
    B --> C{¿WSAStartup exitoso?}
    C -->|No| X[Mostrar error de WSAStartup] --> Y[Salir]
    C -->|Sí| D[Crear un socket UDP]
    D --> E{¿Socket creado exitosamente?}
    E -->|No| Z[Mostrar error de creación de socket] --> K[Limpiar Winsock] --> Y
    E -->|Sí| F[Configurar dirección del servidor]
    F --> G[Preparar mensaje con estado del switch]
    G --> H[Enviar mensaje UDP]
    H --> I{¿Envío exitoso?}
    I -->|No| J[Mostrar error de envío] --> L[Cerrar socket] --> K --> Y
    I -->|Sí| L[Cerrar socket]
    L --> K[Limpiar Winsock]
    K --> M[Asignar input a output]
    M --> N[Fin de la función]
