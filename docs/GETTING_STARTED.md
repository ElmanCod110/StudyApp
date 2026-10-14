# Getting Started with StudyApp

StudyApp, presented in the interface as **Study Chrono**, is a browser-based timer for structuring timed practice and breaks. This guide walks through a low-risk first run and explains what to check before depending on the app for a longer session.

## Quick start

Start with a short session and learn the main controls before choosing a longer duration. For service-worker and installation features, serve the project from an HTTP(S) origin rather than relying on a file opened directly from disk.


## Choose a way to open the app

For a quick look, open `index.html` in a modern browser. To test installation and offline behavior, serve the folder from an HTTP(S) origin so the browser can register `sw.js`. A local development server is sufficient; no build step is documented as required by the current repository.
