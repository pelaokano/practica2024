# Ejemplo de Diagrama de Flujo con Mermaid

```mermaid
graph TD
    A[ATP/EMTP Simulation] -->|Monitorear_interruptor| B[Funcion_Foreign_en_ATP_EMTP]
    B -->|Enviar_estado_por_UDP| C[Socket_UDP_127_0_0_1_12345]
    C -->|Recibir_datos_UDP| D[Hilo_de_Recepcion_en_C]
    D -->|Actualizar_variable_global_atomica| E[Variable_Global_Atomica]
    E -->|Leer_estado_interruptor| F[Hilo_Principal_en_C]
    F -->|Transformar_a_trama_GOOSE| G[Trama_de_datos_GOOSE]
    G -->|Enviar_mensaje_GOOSE| H[Publicacion_en_Protocolo_GOOSE]

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
