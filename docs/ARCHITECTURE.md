# Architecture Notes

StudyApp is a small browser application whose main interface and styling live in `index.html`, with install metadata in `manifest.json` and offline behavior in `sw.js`. This overview is intentionally lightweight and should be updated when the structure changes.

## Main application entry point

The `index.html` file contains the page markup and embedded styles and application logic. When making a change, identify the relevant section first and keep the edit scoped to the behavior or component being changed.
