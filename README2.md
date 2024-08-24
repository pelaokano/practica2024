# Ejemplo de Diagrama de Flujo con Mermaid

```mermaid
graph TD
    A[ATP/EMTP Simulation] -->|Monitorea interruptor| B[Funcion Foreign en ATP/EMTP]
    B -->|Envia estado (1/0) via UDP| C[Socket UDP (127.0.0.1:12345)]
    C -->|Recibe datos de UDP| D[Hilo de Recepcion en C]
    D -->|Actualiza variable global atomica| E[Variable Global Atomica]
    E -->|Lee estado del interruptor| F[Hilo Principal en C]
    F -->|Transforma a trama GOOSE| G[Trama de datos GOOSE]
    G -->|Envia mensaje GOOSE| H[Publicacion en Protocolo GOOSE]

    subgraph ATP_EMTP
        A
        B
    end

    subgraph Aplicacion_C
        D
        E
        F
        G
        H
    end
