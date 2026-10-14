# Troubleshooting Guide

Use this guide to collect useful information when StudyApp behaves unexpectedly. Start with the smallest reproducible case and avoid assuming that every problem is a service-worker issue.

## The page does not load

Confirm that the file path is correct and that the browser supports the features used by the app. If testing the PWA, serve the project from a supported local HTTP(S) origin and inspect the browser console for the first error.


## The timer seems stuck

Check whether the timer is paused, whether the current session has already completed, and whether the expected action is available. Reproduce with a short session and record the state shown before and after each control.


## The layout is clipped

Record the viewport size and browser zoom, then check the setup screen, active timer, and report separately. Note whether the issue affects one control or the whole page and whether horizontal scrolling appears.


## Installation is unavailable

Confirm that the app is served from an origin supported by the browser and that the manifest and icon paths load successfully. Install options differ by browser and operating system, so compare against that platform's normal install flow.


## Offline launch fails

First load the app successfully while online so its service worker can install and cache the shell. Then check whether the service worker is active and whether its precache requests succeeded. A cache cannot supply files that were never stored.


## The installed app looks outdated

Reload the app and inspect the active worker and app-specific cache revision. After an asset release, verify that the cache revision changed when required and that obsolete caches are limited to the app's own namespace.
