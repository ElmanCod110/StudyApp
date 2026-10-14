# Data and Privacy Notes

This document is a guide to reviewing StudyApp's data boundaries, not a substitute for inspecting the code and network behavior of a particular release. Before making privacy promises, verify the current implementation and any future integrations.

## Start with the actual data flow

Review the browser code for local storage, IndexedDB, cookies, network requests, analytics, and third-party resources. Document only behavior that is confirmed in the implementation; do not infer privacy properties from the app's static appearance.


## Separate app cache from user data

The service-worker cache stores app resources so the shell can load offline. Treat that cache separately from preferences or session information: cached HTML and icons are not the same category as a user's personal study history.


## Review browser storage

If preferences or session state are persisted, list the exact keys and data fields, explain why each is needed, and define when it is updated or removed. Avoid storing information that the feature does not need.


## Explain local-device limits

Data stored in a browser profile may be accessible to other people who use that profile or device. Do not describe local storage as encrypted or private from device users unless the implementation demonstrably provides those protections.


## Document network requests

Use the browser Network panel to inspect requests during launch and a complete session. Identify the destination and purpose of any non-local request, including requests added by future analytics, fonts, or integrations.


## Handle clearing and reset

Where the app saves user settings or session data, document how a user can clear it. A reset action should explain its scope and should not imply that browser-managed service-worker caches or unrelated site data were removed unless that is true.


## Avoid secrets in client code

Never place private API keys, passwords, or other server credentials in client-side HTML or JavaScript. Anything delivered to a browser can be inspected by the person using it. Any future service integration should use an appropriate server-side boundary.


## Keep reports user-controlled

If a report export feature is added, generate it locally where practical and clearly describe what fields are included. Do not upload a report or add remote synchronization without an explicit feature design and user-facing explanation.
