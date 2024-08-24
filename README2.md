# Ejemplo de Diagrama de Flujo con Mermaid

```mermaid
graph TD
    A[ATP/EMTP Simulation] -->|Monitorear interruptor| B[Funcion Foreign en ATP/EMTP]
    B -->|Enviar estado (1 o 0) por UDP| C[Socket UDP (127.0.0.1:12345)]
    C -->|Recibir datos de UDP| D[Hilo de Recepcion en C]
    D -->|Actualizar variable global atomica| E[Variable Global Atomica]
    E -->|Leer estado del interruptor| F[Hilo Principal en C]
    F -->|Transformar a trama GOOSE| G[Trama de datos GOOSE]
    G -->|Enviar mensaje GOOSE| H[Publicacion en Protocolo GOOSE]

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
