# Progressive Web App Lifecycle

StudyApp includes a web app manifest and a service worker. This guide explains the expected lifecycle at a high level and provides checks for installation and cached navigation; exact installation prompts depend on the browser and device.

## Serve from a supported origin

Service workers generally require a secure context. Use HTTPS when hosted, or a local development server supported by the browser. Opening an HTML file directly is not a reliable way to test service-worker behavior.
