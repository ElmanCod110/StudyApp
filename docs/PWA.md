# Progressive Web App Lifecycle

StudyApp includes a web app manifest and a service worker. This guide explains the expected lifecycle at a high level and provides checks for installation and cached navigation; exact installation prompts depend on the browser and device.

## Serve from a supported origin

Service workers generally require a secure context. Use HTTPS when hosted, or a local development server supported by the browser. Opening an HTML file directly is not a reliable way to test service-worker behavior.


## Understand the manifest

The manifest defines the app's name, launch URL, display mode, theme colors, and icon assets. When changing a manifest field, verify that its paths remain relative to the deployed app location.


## First installation visit

Load the app while online so the browser can fetch the app shell and the service worker can populate its cache. A first-time offline visit cannot cache files that have never been downloaded.


## Install from the browser

Use the browser's install action when available. Installation UI varies by platform; verify the app name, icon, and launch behavior rather than expecting every browser to show the same prompt.


## Understand the cache revision

The service worker uses an app-specific cache name with a revision suffix. When precached assets change in a release, update the revision so the new worker can populate a fresh cache and remove obsolete caches belonging to this app.


## Check navigation fallback

With the app already cached, test a navigation while offline. The intended fallback is the cached app shell for navigation requests, not returning the HTML shell for every failed asset request.


## Check asset requests

Verify that successful same-origin GET requests can be cached as intended and that cross-origin or non-GET requests are not handled as app-shell navigations. Use browser developer tools to inspect request and cache behavior.


## Update without surprising users

After deploying a new revision, test both an ordinary reload and an installed-app launch. Avoid a release strategy that silently interrupts an active timer; document any user action needed to load an update.
