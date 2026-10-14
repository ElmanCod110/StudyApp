# Architecture Notes

StudyApp is a small browser application whose main interface and styling live in `index.html`, with install metadata in `manifest.json` and offline behavior in `sw.js`. This overview is intentionally lightweight and should be updated when the structure changes.

## Main application entry point

The `index.html` file contains the page markup and embedded styles and application logic. When making a change, identify the relevant section first and keep the edit scoped to the behavior or component being changed.


## Manifest role

The `manifest.json` file provides the app name, short name, start URL, display mode, colors, orientation, and icon references used by supported browsers during installation.


## Service-worker responsibilities

The `sw.js` file installs a versioned cache, precaches the app shell assets, cleans up obsolete caches owned by the app, and handles eligible fetch requests. Keep cache ownership checks narrow so unrelated caches on the same origin are not removed.


## Keep paths deployment-aware

The manifest and service worker use relative paths. When deploying under a subdirectory, check the start URL, scope, precache entries, and navigation fallback together rather than assuming the app lives at the origin root.


## Separate UI from lifecycle behavior

User-facing timer interactions belong to the application interface, while install and fetch lifecycle behavior belongs to the service worker and manifest configuration. When debugging, isolate whether the failure is in the timer UI, browser storage, network, or cache lifecycle.


## Treat cache names as an interface

The cache prefix and revision are part of the update strategy. Change the revision when precached content changes, and make cleanup remove only older caches with the app's own prefix.


## Avoid unnecessary dependencies

For a small static app, additional libraries and build steps increase maintenance. Introduce a dependency only when it solves a concrete need, and document how it is loaded and what happens when it is unavailable.


## Document behavior at module boundaries

When a new script or module is introduced, document its purpose, inputs, outputs, and relationship to the timer state. Prefer explicit responsibilities over hidden side effects shared across unrelated controls.


## Keep this overview current

Revise these notes when files are split, new persistence is introduced, a remote service is added, or the service-worker strategy changes. A short accurate map is more useful than a detailed diagram that no longer matches the code.
