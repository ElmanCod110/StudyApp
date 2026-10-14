# StudyApp User Guide

StudyApp (shown in the interface as **Study Chrono**) is a browser-based timed-practice tool. It helps you structure a study session, schedule rest periods, and review a summary when you finish.

The timer is a planning aid, not a measure of knowledge or a substitute for your own judgment.

## Before you begin

Open `index.html` in a modern browser. For the full Progressive Web App (PWA) experience—including service-worker caching—serve the project from a local or hosted HTTP(S) origin. Browsers generally do not enable service workers for ordinary remote pages or every local-file setup.


## Configure a session

On the setup screen, choose the number of tests for the session. The field accepts values from 1 to 5,000. Use a smaller number when learning the controls or trying a new schedule; a long session is not automatically a better session.

The preview beneath the setup options gives you an at-a-glance view of the planned session structure. Check the estimate before beginning, especially when using custom breaks.


## Choose a time preset

The time presets set the target duration for each question. Select a duration that reflects the work you are practising rather than choosing the shortest option by default.

A target is a pacing guide: finishing early or timing out should be treated as session information, not as a score by itself. You can use a short practice run to learn how the timer behaves before starting a longer session.


## Break planning

Study Chrono offers automatic and custom break planning. Automatic planning adjusts the number and spacing of breaks to the size of the session. Custom planning lets you choose how many tests occur between short breaks, the short-break length, how often a long break occurs, and its duration.

Break previews are estimates based on the current configuration. Changing the session size or a break setting can change the schedule, so review the preview again before starting.


## During a focus session

Use **Done** when you finish a question before the timer expires. Use **Skip** when you want to move on without marking the question as completed normally. The report records skipped and timed-out questions separately.

The pause control is a limited allowance rather than an unlimited stop button. If you use a pause, wait for the interface to resume the timer before continuing your work. Avoid refreshing the page during a session because progress is not currently saved for recovery.


## Break and review screens

When a scheduled break begins, the app switches to a break screen and displays the remaining time. You can skip a break if you are ready to continue, but consider using the planned rest to stand up, change focus distance, or get a drink.

After the focus phase, the review phase provides time to consolidate what you covered. Use the finish-review control when you are ready to view the report.


## Read the session report

The report summarizes elapsed time, pace, skipped items, timeouts, and time reclaimed by finishing questions early. Its insight cards are generated from the session's timing data and configuration.

Interpret these insights as prompts for reflection, not diagnoses or guarantees about learning. For example, a faster final third may reflect growing familiarity, while a slower finish may indicate that the schedule deserves adjustment. Consider context before changing your study habits.


## Install and use offline

When hosted on HTTPS (or an eligible local development origin), the app can register its service worker and cache the main app shell. Depending on the browser, an install option may appear in the browser menu or address bar.

For an offline check, open the app once while online, allow it to finish loading, and then try navigating to it after disconnecting. Browser installation and offline behavior vary by platform. An offline copy may not include resources that were never cached.


## Troubleshooting

- **The app opens but does not install:** confirm that you are using a supported browser and a secure origin, and check that the web app manifest and icons load.
- **Offline launch does not work:** first open the app online, then confirm the service worker was registered in the browser's developer tools.
- **An old interface keeps appearing:** the browser may still have an earlier service-worker cache. Reload after reconnecting and allow the updated worker to activate.
- **The report is not what you expected:** check whether questions were completed, skipped, or timed out; the report distinguishes these outcomes.
- **A session was lost after refresh:** session recovery is not implemented yet. Avoid refreshing during a long session until recovery is added.


## Accessibility and manual checks

You can navigate the visible controls with a keyboard and use browser zoom to enlarge the interface. If a control is difficult to focus, activate, or understand with assistive technology, note the browser and the affected control when reporting the problem.

A quick manual pass before a release should cover:
1. Start a short session and complete a question.
2. Skip a question and confirm the report distinguishes it.
3. Pause and resume using the available pause allowance.
4. Reach a scheduled break and use the skip-break control.
5. Finish review and start a new session.
6. Load the app online, then check offline launch and cache update behavior.

This checklist is descriptive; it does not imply that automated or manual tests have been run for a particular change.
