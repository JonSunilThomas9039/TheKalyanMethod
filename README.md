# FormFit frontend MVP

## Run
Extract the ZIP and open `index.html` in a modern browser, or serve the folder using VS Code Live Server. Data persists in that browser's localStorage.

The responsive layout is mobile-first: phones use a sticky header with a hamburger navigation drawer and bottom-sheet dialogs; tablets use a compact sidebar; larger screens use the full desktop sidebar. A local server such as VS Code Live Server is recommended for camera permissions and consistent browser behavior.

On mobile, the navigation is a hamburger drawer with no fixed bottom action bar. Trainees open on Today's check-in; the full navigation remains available from the drawer.

## Three demo accounts
- Maya Chen — Trainer (`FORM-MAYA-24`)
- Alex Morgan — Trainee, already connected to Maya with seeded daily workout and meals
- Jamie Patel — Trainee, independent until a request is accepted

## Try QR connection
1. Switch to Jamie Patel.
2. Open **My trainer** and click **Scan trainer QR code**. The prototype simulates scanning the QR payload.
3. Switch to Maya Chen → **Connection requests** → **Accept request**.
4. Jamie becomes connected and appears under My trainees.

`assets/trainer-qr.png` is a real QR code encoding `FORMFIT_TRAINER:MAYA:FORM-MAYA-24`. The scan button simulates the scan rather than opening the camera; entering the trainer code is also supported.

## Included
- Role-specific trainer and trainee screens.
- QR-identifying trainer profile and request/accept/decline flow.
- Daily workout sessions, exercises, actual weight/reps, draft/publish and rest-day controls.
- Trainer-only daily nutrition targets (calories, protein, carbs, fat, fiber, water, optional micronutrient notes) and daily meal plans.
- Trainers can edit exercise names, sets, reps and weights, add exercises, and edit meal details and nutrition values inline. Standard exercises and meals appear as editable autocomplete suggestions; trainers can type and save custom exercises or meals without changing the code. Draft actions preserve target edits before publishing.
- Trainee meal completion, meal photos, substitution notes, daily check-ins, morning/evening weight, sleep, steps, water and progress photo.
- Calendar, logbook, goals, trainee overview and browser persistence.
- Shared monthly Calendar for trainers and trainees, with Monday-first navigation, per-date workout/meal indicators, single-tap date selection, desktop double-click/mobile double-tap previews, trainer trainee selection, and links into the existing date-bound planners.
- Deterministic demo schedules and historical check-ins around the current date for Alex and independent personal activity for Jamie.

## Prototype limitations
No backend, real authentication, cross-device sync or secure storage. All demo accounts run in the same browser data store; connection requests are not shared between browsers. Photos are stored in localStorage, so use small images only. A production app needs backend authorization, database storage, server-managed QR tokens, and private image storage with consent controls.


## Troubleshooting
- If the browser shows an old version, extract the ZIP to a new folder and hard-refresh the page.
- Use the **Reset demo data** control if the saved local demo state gets into an unexpected state.
- For camera scanning, run with VS Code Live Server (localhost), allow camera permission, and use a recent Chrome/Edge browser. The fallback code is `FORM-MAYA-24`.
- Requests only appear in the trainer account inside this same browser profile. Cross-device requests need a backend, which this frontend-only prototype does not include.
- Calendar previews show published plans to trainees and draft or published plans to trainers. Workout and Meals are accessible through tabs or horizontal swipes. The calendar uses the same stored plan records as the existing workout and meal planners.
