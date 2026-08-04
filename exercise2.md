# Socodka URL-ka - Diagram

## Sida URL-ku uga gudbo Browser-ka ilaa Bogga la Arko

```mermaid
sequenceDiagram
    participant U as 👤 User
    participant B as 🌐 Browser
    participant D as 🗂️ DNS Server
    participant W as 💻 Web Server

    U->>B: 1. Wuxuu geliyaa URL-ka<br/>(tusaale.com)
    B->>B: 2. Wuxuu hubiyaa Cache-ka<br/>(haddii horey loo booqday)
    
    alt Cache lama helin
        B->>D: 3. DNS Lookup codsi<br/>(magaca domain-ka)
        D-->>B: 4. Wuxuu soo celiyaa<br/>IP Address
    end

    B->>W: 5. TCP/SSL Connection<br/>oo la sameeyo
    B->>W: 6. HTTP Request<br/>(GET /page)
    W->>W: 7. Server-ku wuxuu<br/>processess-gareeyaa codsiga
    W-->>B: 8. HTTP Response<br/>(HTML, CSS, JS, Sawirro)
    B->>B: 9. Browser-ku wuxuu<br/>render gareeyaa bogga
    B-->>U: 10. Bogga wuu ku soo<br/>muuqdaa shaashadda
```

## Qaybaha URL-ka (URL Breakdown)

```mermaid
graph LR
    A["https://www.tusaale.com/alaabta?nooc=khudaar#sawirada"]
    A --> B["Protocol<br/>https://"]
    A --> C["Domain<br/>www.tusaale.com"]
    A --> D["Path<br/>/alaabta"]
    A --> E["Query<br/>?nooc=khudaar"]
    A --> F["Fragment<br/>#sawirada"]
```

## Sharaxaad Kooban

| Tallaabo | Qeybta | Shaqada |
|---|---|---|
| 1 | User | Wuxuu geliyaa URL-ka browser-ka |
| 2 | Browser | Wuxuu hubiyaa cache-ka |
| 3-4 | DNS Server | Domain-ka wuxuu u beddelaa IP address |
| 5 | Browser + Server | Xiriir ayaa la sameeyaa (TCP/TLS) |
| 6 | Browser | Wuxuu diraa HTTP Request |
| 7 | Web Server | Wuxuu processess-gareeyaa codsiga |
| 8 | Web Server | Wuxuu soo celiyaa HTTP Response |
| 9-10 | Browser | Wuxuu render gareeyaa oo bogga soo bandhigaa |