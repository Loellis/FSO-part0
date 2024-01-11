# Exercise 0.5 - Single page app diagram

```mermaid
sequenceDiagram
    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/spa
    server-->>browser: HTML document (200 OK)
    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/main.css
    server-->>browser: CSS file (200 OK)
    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/spa.js
    server-->>browser: JS file (200 OK)
    Note right of browser: Browser executes JS that fetches JSON data from server
    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/data.json
    server-->>browser: [{...} , ..., {...}]
    browser->>server: GET https://studies.cs.helsinki.fi/favicon.ico
    server-->>browser: 404 Not Found
    Note right of browser: Browser executes callback function to render notes
```