# Accessibility Review Guide

This guide provides a practical checklist for reviewing StudyApp's interface with keyboard input, assistive technology, zoom, and reduced-motion preferences. It is a review aid, not a claim that every criterion has already been verified.

## Start with keyboard-only use

Reload the page and navigate through the interface using Tab, Shift+Tab, Enter, Space, and arrow keys where appropriate. Confirm that focus is visible and the current control can be identified without a mouse.


## Check focus visibility

Every interactive element should show a clear focus indicator against the dark background. Verify that focus is not hidden behind overlays and that moving focus does not unexpectedly activate a control.


## Verify input labels

Check that every setup input has a programmatic label, not only placeholder text. The visible label should describe the field's purpose and remain available when the user enters a value.


## Review icon-only controls

Controls represented only by an icon need an accessible name that communicates their action. Confirm that the name changes when the action changes, such as switching between pause and resume.


## Avoid noisy live announcements

A countdown that announces every second can make a screen reader difficult to use. Prefer announcing meaningful state transitions—such as paused, resumed, break started, or session completed—rather than every tick.
