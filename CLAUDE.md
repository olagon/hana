# hana - working agreements for this folder

This folder is the single source of truth for hana, a paste-anything AI task
manager that runs as a published Claude artifact. Treat the files here as the
live code. Nothing ships from anywhere else.

## Files

- `hana.jsx` - the entire app, one React component written for the Claude
  artifact runtime
- `README.md` and `LICENSE` - published to GitHub at
  https://github.com/olagon/hana
- `CLAUDE.md` - this file

## Rules for every code change

1. Bump `APP_VERSION` at the top of `hana.jsx` on every change. Patch for
   fixes (1.1.1), minor for features (1.2.0). The version shows in the app
   footer, which is how Olin verifies what is actually live.
2. Never use em dashes or en dashes anywhere, including UI copy, comments,
   and prompt text. Hyphens are fine.
3. Do not remove these load-bearing pieces:
   - The splash scroll fix (`splashCardRef`, `splashBtnRef`, and the
     `preventScroll` focus effect). Without it the welcome card opens
     scrolled to the bottom.
   - The footer links: Olin Lagon's LinkedIn and
     https://github.com/olagon/hana
   - The serialized storage write queue in `persist()`. Rapid actions fire
     concurrent writes that the storage bridge cannot handle.
   - The retry loop with backoff around the extraction API call.
   - The strict merge rule in the extraction prompt (the Forest vs Mysa
     example). It prevents different tasks from being collapsed into one.
4. The app must keep working inside the Claude artifact runtime: use
   `window.storage`, never localStorage; keyless fetch to
   api.anthropic.com; model `claude-sonnet-4-6`.
5. New tasks default to today unless the pasted text names a deadline. Keep
   the splash, the help page, and the README wording consistent with actual
   behavior whenever behavior changes.
6. Keep it dead simple. Push back on features that add screens, settings, or
   ceremony.

## Ship loop

1. Make the change here and bump `APP_VERSION`.
2. Commit and push to GitHub from this folder.
3. Olin uploads `hana.jsx` to his artifact chat in claude.ai, updates the
   artifact there, and clicks Publish.
4. Verify by opening the public link and checking the footer shows the new
   version number.
