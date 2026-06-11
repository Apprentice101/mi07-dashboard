# MI-07 Voting Procedures Dashboard

Built from `voting-dashboards-source` repo, district config `client/src/configs/mi-07.ts`.

## District profile
- **State**: Michigan
- **Counties**: Ingham, Eaton, Clinton, Shiawassee, Livingston, Genesee
- **2026 race**: Tom Barrett (R, incumbent) vs Aug 4, 2026 D primary winner (Bridget Brink, Will Lawrence, Matt Maasdam, Muhammad Salman Rais)
- **Next key date**: Aug 4, 2026 (primary)
- **Cook PVI / rating**: Toss Up
- **Election admin**: Michigan SOS (Jocelyn Benson)

## Data inventory
- 13 sources verified (state SOS + county election offices + nonpartisan journalism)
- 11 rules — all `needsReview: true, confidence: "unconfirmed"` (verify before publish)
- 16 election events on timeline
- 9 voter resources
- 6 news cards (last 90 days)
- 3 updates panel entries (initial-build inventory)
- 1 conflict logged: AV signature cure deadline — MI SOS publishes Election Day 8pm; some county clerks publish post-canvass guidance

## Deploy to GitHub Pages

```bash
# In Apprentice101/mi07-dashboard repo:
git add .
git commit -m "Deploy MI-07 dashboard"
git push -u origin main
```

Enable GitHub Pages from main branch root in repo settings.

## Files
- `index.html` — entry point
- `snapshot.json` — district data (data layer)
- `assets/` — bundled JS/CSS

## QA status (2026-06-11)
- All rules and events marked `confidence: "unconfirmed"` — strict review required before public ship per user policy
- Zero console errors on smoke test
- Review Queue tile, district map, tab highlighting, Updates/Conflicts panels all rendering correctly (post-v2 fixes)

## Built from
- Source repo: https://github.com/Apprentice101/voting-dashboards-source
- Config file: `client/src/configs/mi-07.ts`
- Build command: `VITE_DISTRICT_ID=MI-07 npm run build:static`

## Title fix (2026-06-11 patch)
- Browser tab `<title>` now reads "MI-07 Voting Procedures Dashboard" (was generic/empty)
- `client/index.html` and `script/build-static.ts` updated so all future builds get the district title automatically
