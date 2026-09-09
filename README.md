# Aoo Waitlist

Live site (GitHub Pages): `https://rohitwaghire.github.io/Aoo-Waitlist/`

- `index.html` — waitlist landing (email capture)
- `feature.html` — feature request form
- `assets/` — local logo / icon (migrated off temporary Stitch URLs)

## How data collection works

Both pages keep the custom Stitch design. On submit they POST invisibly in the
background to **SubmitKit** (`fetch`, no redirect, no popup, no new tab) and
show the on-page success message. Screenshots ride along inside the same
request. Everything lands in the SubmitKit dashboard + email notifications.

## SubmitKit setup (one-time, ~2 min)

1. Sign up at https://submitkit.dev (free: 500 submissions/mo, file uploads
   up to 5 MB per file, max 5 files per submission).
2. Create **two** forms (New form): one for the waitlist, one for feature
   requests. Copy each endpoint URL (`https://submitkit.dev/api/f/...`).
3. Paste them into the code:
   - `index.html` → `var SUBMITKIT_WAITLIST_URL = "https://submitkit.dev/api/f/..."`.
   - `feature.html` → `var SUBMITKIT_FEATURE_URL = "https://submitkit.dev/api/f/..."`.
4. Commit + push. Field names arrive as-is (`email` / `request-type`,
   `request-short`, `request-details`, `file-upload`, `request-email`).

Notes:
- The file hint on `feature.html` says "up to 5MB" to match the free plan
  (paid plans allow 25 MB — bump `MAX_FILE_BYTES` if you upgrade).
- Spam is handled by SubmitKit via the `_honeypot` + `_timestamp` hidden
  fields already in both forms.
