# Aoo Waitlist

Live site (GitHub Pages): `https://rohitwaghire.github.io/Aoo-Waitlist/`

- `index.html` — waitlist landing (email capture)
- `feature.html` — feature request form
- `assets/` — local logo / icon (migrated off temporary Stitch URLs)

## Connect tally.so (to collect data)

1. Create 2 forms at https://tally.so:
   - **Aoo Waitlist**: 1 Email field.
   - **Aoo Feature Request**: Type (dropdown), Short title, Details, Screenshots (file), Email.
2. Copy each Share link, e.g. `https://tally.so/r/XXXXXX`.
3. Paste them:
   - `index.html` → `const TALLY_WAITLIST_URL = "https://tally.so/r/..."`.
   - `feature.html` → `const TALLY_FEATURE_URL = "https://tally.so/r/..."`.
4. Commit + push. Submit on the site opens Tally pre-filled so responses land in Tally dashboard (CSV / Sheets / Notion / email notifications).

Full inline embed alternative is commented inside both HTML files.
