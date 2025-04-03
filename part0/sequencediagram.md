sequenceDiagram
    browser request
    server response

    browser->>server: POST  https://studies.cs.helsinki.fi/exampleapp/notes
    activate server
    server-->>browser: 302 Redirect to HTML document
    deactivate server

    browser->>server: GET  https://studies.cs.helsinki.fi/exampleapp/notes
    activate server
    server-->>browser: 200 OK HTML document
    deactivate server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/main.css
    activate server
    server-->>browser: the css file
    deactivate server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/main.js
    activate server
    server-->>browser: the JavaScript file
    deactivate server

    The browser executes the JavaScript code that fetches the JSON from the server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/data.json
    activate server
    server-->>browser: [{ "content": "Ishaq was here. Apeace!", "date": "2025-04-03T03:12:31.715Z" }, ... ]
    deactivate server

    The browser executes the callback function that renders the notes