# kemo-legal

Public legal pages for Kemosabe apps, served by GitHub Pages at **https://legal.kemosabeonline.uk**.
Plain HTML + one stylesheet (`style.css`). No build step: edit the HTML and push to `main`.

| Path | What |
|---|---|
| `/` | list of apps |
| `/kazi/` | Swala Kazi language picker |
| `/kazi/{sw,en}/{terms,privacy,helper-agreement,conduct,safety,delete-account}` | Swala Kazi pages (the app opens the user's locale) |

## Rules
- Every page shows its version. Swala Kazi's current version is `2026-10-06`, matching `internal/legal` in kazi-backend. A change in substance means a new date here **and** a bump there, so users are asked to accept again.
- Keep `sw` and `en` in step: same sections, same anchors (`#cancel`, `#id-checked`, `#problems` ...).
- Words must match what the code does (kazi-backend `docs/RISK_FIX_PLAN.md`, `internal/common/policy/policy.go`). Never use the words "escrow" or "bank"; say "held by our licensed payment partner until the job is done".
- `[LEGAL ENTITY]`, `[ADDRESS]` and `[PDPC REGISTRATION NUMBER]` are placeholders the advocate fills before public launch. Remove the "pending advocate review" note at the same time.

## Add another app
Copy `kazi/` to `<app>/`, rewrite the content, and add the app to `index.html`.

## Hosting
GitHub Pages from `main` / root, custom domain in `CNAME`. DNS: `legal` CNAME → `chrisostomemataba.github.io`, DNS only (grey cloud), managed with kazi-backend `scripts/cf-dns.sh`; recorded in kazi-backend `docs/CLOUD.md` §3.2.
