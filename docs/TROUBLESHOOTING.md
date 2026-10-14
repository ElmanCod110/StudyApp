# Troubleshooting Guide

Use this guide to collect useful information when StudyApp behaves unexpectedly. Start with the smallest reproducible case and avoid assuming that every problem is a service-worker issue.

## The page does not load

Confirm that the file path is correct and that the browser supports the features used by the app. If testing the PWA, serve the project from a supported local HTTP(S) origin and inspect the browser console for the first error.


## The timer seems stuck

Check whether the timer is paused, whether the current session has already completed, and whether the expected action is available. Reproduce with a short session and record the state shown before and after each control.


## The layout is clipped

Record the viewport size and browser zoom, then check the setup screen, active timer, and report separately. Note whether the issue affects one control or the whole page and whether horizontal scrolling appears.
