```mermaid
sequenceDiagram
	participant U as User
	participant C as Client
	participant S as Server
	

	U->>C: Input form data
	C->>+S: POST https://studies.cs.helsinki.fi/exampleapp/new_note
	S-->>-C: 302 redirect response
	C->>+S: GET https://studies.cs.helsinki.fi/exampleapp/notes
	S-->>-C: HTML document
	C->>+S: GET https://studies.cs.helsinki.fi/exampleapp/main.css
	S-->>-C: CSS file
	C->>+S: GET https://studies.cs.helsinki.fi/exampleapp/main.js
	S-->>-C: Javascript file
	Note right of C: The browser starts executing the JavaScript code that fetches the JSON from the server
	C->>+S: GET https://studies.cs.helsinki.fi/exampleapp/data.json
	S-->>-C: [{ "content": "HTML is easy", "date": "2023-1-1" }, ... ]
	Note right of C: The browser executes the callback function that renders the notes
	
