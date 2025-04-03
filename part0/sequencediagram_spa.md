sequenceDiagram
    browser request
    server response

    browser->>server: POST  https://studies.cs.helsinki.fi/exampleapp/notes
    activate server
    server-->>browser: 201 Created - creates the new_note_spa JSON file
    deactivate server