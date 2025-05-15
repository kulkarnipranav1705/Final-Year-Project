```mermaid
graph TD
    subgraph LoRa Network
        A[LoRa Node<br>(with Sensor)]
        B(LoRa Gateway<br>(with WiFi))
        A -->|LoRa Communication<br>(Multi-hop/Single-hop)| B
    end

    subgraph Backend System
        D(Flask Server)
        E(SQLite Database)
        D -->|Database Connection<br>(Read/Write)| E
    end

    subgraph Frontend System
        F[User]
        G(Frontend Dashboard<br>(Browser))
        F -->|Accesses via Browser| G
    end

    B -->|HTTP<br>(Data/Logs)| Internet(Internet / Local Network)
    Internet -->|HTTP<br>(Ingestion/API)| D
    G -->|HTTP<br>(API Calls - GET)| D
