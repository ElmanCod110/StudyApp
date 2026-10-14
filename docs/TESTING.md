# Manual Testing Guide

Use this guide to check the main StudyApp workflow after changes. It focuses on repeatable manual checks and does not imply that an automated test suite or CI workflow exists.

## Baseline launch check

Open the app in a modern browser and confirm that the initial screen renders without obvious layout failures. Open the developer console when investigating a suspected runtime error and record any relevant message.


## Test session setup

Change the available session settings and select a preset if one is offered. Confirm that displayed values match the chosen configuration before starting the timer.


## Test timer transitions

Run a short session and observe start, pause, resume, break, skip, and completion paths where supported by the interface. Check that the visible state and available action remain consistent after each transition.


## Test boundary values

Try the smallest allowed values and any documented upper bounds. Empty, non-numeric, or out-of-range input should not create a negative or unusable duration; record the exact input if behavior differs from expectations.


## Test narrow layouts

Use a narrow mobile viewport and inspect setup, running timer, paused state, and final report. Check for clipped controls, overlapping labels, unreadable values, and horizontal overflow.
