graph TD
    subgraph LoRa Network
        A[LoRa Node\n(with Sensor)]
        B(LoRa Gateway\n(with WiFi))
        A -->|LoRa Communication\n(Multi-hop/Single-hop)| B
    end

    subgraph Backend System
        D(Flask Server)
        E(SQLite Database)
        D -->|Database Connection\n(Read/Write)| E
    end

    subgraph Frontend System
        F[User]
        G(Frontend Dashboard\n(Browser))
        F -->|Accesses via Browser| G
    end

    B -->|HTTP\n(Data/Logs)| Internet(Internet / Local Network)
    Internet -->|HTTP\n(Ingestion/API)| D
    G -->|HTTP\n(API Calls - GET)| D
