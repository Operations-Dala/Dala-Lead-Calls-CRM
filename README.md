# Dala Lead Calls CRM — Call Ops Dashboard

A real-time call-tracking and follow-up dashboard for Dala Technologies' business development team.

## What it does
- Logs calls per rep (MW, JZRZ) with status (Cold / Warm / Hot / Declined / Won)
- Surfaces an action queue: overdue follow-ups, due today, due tomorrow, not-yet-called prospects
- Tracks call counts (today / this week / all-time) per rep and combined
- Shares one master prospect list (Contacts) across both reps, showing who has already reached each company
- Team Overview compares both reps side by side

## Data
Currently persists to a private per-browser-session storage layer built into the environment it was created in (Claude artifacts). To run this as a standalone site, that storage layer won't be present — see "Next steps" below.

## Files
- `index.html` — the entire dashboard (HTML/CSS/JS, no build step, no dependencies except Google Fonts)

## Running locally
Just open `index.html` in a browser. No server or build step required.

## Next steps to make this production-ready
1. **Swap storage**: replace the `window.storage.get/set` calls in the `<script>` block with calls to your own backend API (e.g. `fetch('/api/calls')`), or point them at Firebase/Supabase for a quick real backend.
2. **Auth**: currently there's no login — anyone with the link can see and edit data. Add auth before sharing widely.
3. **Multi-device sync**: once on a real backend, calls logged on one device will show up on others in real time (currently data is local to whichever browser/session logged it).
