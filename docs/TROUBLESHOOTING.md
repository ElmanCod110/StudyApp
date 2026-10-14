# Troubleshooting Guide

Use this guide to collect useful information when StudyApp behaves unexpectedly. Start with the smallest reproducible case and avoid assuming that every problem is a service-worker issue.

## The page does not load

Confirm that the file path is correct and that the browser supports the features used by the app. If testing the PWA, serve the project from a supported local HTTP(S) origin and inspect the browser console for the first error.
