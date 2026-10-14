# Data and Privacy Notes

This document is a guide to reviewing StudyApp's data boundaries, not a substitute for inspecting the code and network behavior of a particular release. Before making privacy promises, verify the current implementation and any future integrations.

## Start with the actual data flow

Review the browser code for local storage, IndexedDB, cookies, network requests, analytics, and third-party resources. Document only behavior that is confirmed in the implementation; do not infer privacy properties from the app's static appearance.
