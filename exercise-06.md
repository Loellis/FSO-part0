# Exercise 0.6 - New note in Single page app diagram

```mermaid
sequenceDiagram
    Note right of browser: JS handles rerendering of page when button is clicked
    Note right of browser: JS triggers POST to server via sendToServer function
    browser->>server: POST https://studies.cs.helsinki.fi/exampleapp/new_note_spa
    server-->>browser: HTML document (201 Created)
```