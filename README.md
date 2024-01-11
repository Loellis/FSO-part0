# FSO-part0
First part of University of Helsinki's Full Stack open course.


## Exercise 0.4 - New note diagram
**Steps when posting a new note:**
1. On button click, browser sends user input to server
2. Server sends redirect to new location (302)
3. Browser reloads webpage, requests HTML
4. Server returns HTML
5. Browser requests CSS file
6. Server returns CSS
7. Browser requests JS file
8. Server returns JS file
9. JS causes browser to request JSON data
10. Server returns JSON
11. Browser executes the callback to render the notes including the new ones

**On button click the following sequence will occur:**
```mermaid
sequenceDiagram
    browser->>server: POST https://studies.cs.helsinki.fi/exampleapp/new_note
    server-->>browser: 302 Redirect to https://studies.cs.helsinki.fi/exampleapp/notes
    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/notes
    server-->>browser: HTML document (304 Not Modified)
    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/main.css
    server-->>browser: CSS file (304 Not Modified)
    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/main.js
    server-->>browser: JS file (304 Not Modified)
    Note right of browser: Browser executes JS that fetches JSON data from server
    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/data.json
    server-->>browser: [{...} , ..., {...}]
    Note right of browser: Browser executes callback function to render notes
``````

