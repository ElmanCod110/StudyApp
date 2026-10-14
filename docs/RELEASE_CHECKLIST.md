# Release Checklist

Use this checklist before publishing a StudyApp update. It is intentionally small and focused on changes that can affect the single-page interface, installation metadata, and offline cache behavior.

## Review the scope

Confirm which files changed and why. Keep the release focused, remove accidental debug output, and ensure the documentation describes the behavior that is actually being shipped.


## Check the main workflow

Run a short study session and exercise the core controls that the change may affect. Verify the expected state transitions and read the final report if the change touches session completion.


## Review accessibility basics

Check keyboard focus, accessible names for icon-only controls, reduced-motion behavior, text contrast, and the ability to understand state changes without relying only on color or animation.


## Check small-screen layouts

Inspect setup, active timer, paused state, and report at a narrow viewport. Confirm that controls remain usable, text is not clipped, and no unintended horizontal overflow is introduced.


## Update cache revision when needed

If precached assets change, review the service-worker cache revision and update it when appropriate. Confirm that cleanup remains restricted to the app's cache namespace and that the shell can be populated successfully.


## Verify install metadata

When changing the manifest or icons, check that the name, start URL, scope, theme colors, and referenced image paths are consistent with the intended deployment location.


## Perform an offline smoke test

After a successful online load, disconnect the network and try a navigation. Confirm the cached shell behavior, then reconnect and verify that normal navigation works again.


## Record release limitations

Document known issues, browser-dependent behavior, and checks that could not be performed. Do not describe a manual or automated test as passing unless it was actually run and observed.
