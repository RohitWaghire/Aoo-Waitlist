# Aoo Waitlist

Live site (GitHub Pages): `https://rohitwaghire.github.io/Aoo-Waitlist/`

- `index.html` — waitlist landing (email capture)
- `feature.html` — feature request form
- `assets/` — local logo / icon (migrated off temporary Stitch URLs)

## How data collection works

Both pages keep the custom Stitch design. On submit they open the Tally form
as a **modal popup on the same page** (official `Tally.openPopup`, no redirect,
no new tab) with the typed answers pre-passed, so the visitor just confirms.
Responses land in the Tally dashboard (CSV / Sheets / Notion / notifications).

## Tally hidden fields (one-time setup, ~2 min — enables prefill)

Without this, the popup opens with empty fields; with it, answers arrive prefilled.

**Aoo Waitlist** (`xXq1G5`):
1. Open the form in Tally > add a **Hidden fields** block, name it exactly `email`.
2. Open the email question > **Default answer** > type `@` and pick the hidden `email` field.

**Aoo Feature Request** (`dWM1ro`):
1. Add **Hidden fields** named exactly: `type`, `short`, `details`, `email`.
2. For each visible question, set its **Default answer** (`@` mention) to the
   matching hidden field. (Screenshots can't be prefilled — visitors attach
   them in the popup.)

Hidden-field names are case-sensitive and must match the `hiddenFields` keys
in `index.html` / `feature.html`.
