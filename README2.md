# Ejemplo de Diagrama de Flujo con Mermaid

```mermaid
graph TD
    A[ATP/EMTP Simulation] -->|Monitor interruptor| B[Función Foreign en ATP/EMTP]
    B -->|Enviar estado (1/0) vía UDP| C[Socket UDP (127.0.0.1:12345)]
    C -->|Recibir datos de UDP| D[Hilo de Recepción en C]
    D -->|Actualizar variable global atómica| E[Variable Global Atómica]
    E -->|Leer estado del interruptor| F[Hilo Principal en C]
    F -->|Transformar a trama GOOSE| G[Trama de datos GOOSE]
    G -->|Enviar mensaje GOOSE| H[Publicación en Protocolo GOOSE]

    subgraph ATP/EMTP
        A
        B
    end

    subgraph Aplicación C
        D
        E
        F
        G
        H
    end
