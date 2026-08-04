# Network & Web Basics Exercise

## 1. Internet Mapping Activity

```mermaid
graph TD
    A[<font color='#000000'><b>Client Computer</b></font>] -->|Request: URL| B(<font color='#000000'><b>Local Router/Wi-Fi</b></font>)
    B -->|Encrypted Traffic| C(<font color='#000000'><b>ISP - Modem/Gateway</b></font>)

    subgraph "Core Internet (Backbone)"
    C --> D{<font color='#000000'><b>DNS Resolver</b></font>}
    D -->|Query: Where is example.com?| E(<font color='#000000'><b>Root DNS Server</b></font>)
    E -->|TLD Server IP| D
    D -->|Query: To TLD Server| F(<font color='#000000'><b>TLD DNS Server - .com</b></font>)
    F -->|Authoritative Server IP| D
    D -->|Query: To Auth Server| G(<font color='#000000'><b>Authoritative DNS Server</b></font>)
    G -->|Final IP Address| D
    D -->|Sends IP to Client| C
    end

    C -->|Sends Request to IP| H(<font color='#000000'><b>Web Server</b></font>)
    H -->|Processes Request| H
    H -->|Sends HTML Response| C
    C -->|Delivers Content| B
    B -->|Renders Webpage| A

    %% Styling Sanduuqyada
    style A fill:#ffb6c1,stroke:#333,stroke-width:2px
    style B fill:#add8e6,stroke:#333,stroke-width:2px
    style C fill:#add8e6,stroke:#333,stroke-width:2px
    style H fill:#ffb6c1,stroke:#333,stroke-width:2px
    style D fill:#fffaca,stroke:#333
    style E fill:#fffaca,stroke:#333
    style F fill:#fffaca,stroke:#333
    style G fill:#fffaca,stroke:#333

    subgraph "Legend"
    L1[<font color='#000000'><b>User Action/Device</b></font>]
    L2(<font color='#000000'><b>Network Infrastructure</b></font>)
    L3{<font color='#000000'><b>Core Logic/DNS Lookup</b></font>}

    style L1 fill:#ffb6c1,stroke:#333
    style L2 fill:#add8e6,stroke:#333
    style L3 fill:#fffaca,stroke:#333
    end