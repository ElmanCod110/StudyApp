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


## Test keyboard operation

Complete the main workflow without a mouse. Check focus order, focus visibility, activation keys, and whether focus remains predictable after a screen or state transition.


## Test reload behavior

Reload before a session, during a session, and after a completed session. Record which state is intentionally restored and which state is reset; do not assume persistence is guaranteed unless the app documents it.


## Test offline behavior

After one successful online load, disconnect the network and reload the app. Confirm the cached app shell is available, then note any feature that still requires network access. Restore connectivity after the test.
