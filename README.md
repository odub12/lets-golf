# 🏌️ Let's Golf

**A mobile-first golf scoring PWA for live tournaments, side games, and payouts.**

Built as a single-file progressive web app — no app store, no install, no account required. Open the link and start scoring.

**Live:** [odub12.github.io/lets-golf](https://odub12.github.io/lets-golf/)
**Version:** 15.9.81 · SW 1.0.91
**Last updated:** February 2026

---

## What It Does

Let's Golf replaces paper scorecards, spreadsheet payouts, and group text chains with one app that works on any phone. A host creates a tournament, players join with a code, and everyone scores in real time on their own device.

**For the host:** Set up the course, invite players, manage the roster, track scores, calculate payouts, and share results — all from your phone.

**For players:** Join with a 4-character code, enter your scores hole by hole, and see the live leaderboard update as the round unfolds.

**Solo play:** Skip the multiplayer setup entirely. Create a round, add players manually, and score a casual round with full handicap support.

---

## Key Features

### Scoring
- Hole-by-hole score entry with swipe navigation between holes
- Compact player card carousel (swipe between players)
- Score visualization — color-coded by relation to par (eagle, birdie, par, bogey, double+)
- Real-time leaderboard with gross, net, and Stableford views
- USGA handicap application with full, 80%, or 90% methods
- Course handicap auto-calculation from slope/rating
- Supports 1–100 players per tournament

### Multi-Device Sync
- Host creates tournament → gets a host code (LG-MMDD-H###)
- Players join with a player code (LG-MMDD-P###)
- All scores sync in real time via Firebase
- Co-host promotion — delegate host controls to another device
- Conflict resolution with newest-wins timestamps
- Works offline with automatic reconnection and sync

### Course Database
- 45,000+ courses searchable by name or city
- Auto-loads pars, handicap indexes, slope, and rating
- Custom course builder with per-hole par and handicap entry
- Edit courses after creation

### Payout Calculator
- Configurable buy-in with real-time pot calculation
- Built-in categories: Gross Skins, Net Skins, Low Gross, Low Net
- Footlong Out/In with Gross, Net, or Both scope and configurable places paid
- Closest to the Pin (KP) — auto-detects par 3s with per-hole winner selection
- Skins options: par-or-better requirement, carryover with multi-hole pots
- Custom categories with swipe-to-delete
- Percentage or fixed-dollar allocation mode
- Editable place split ratios (e.g. change 60/25/15 to 50/30/20)
- Save/load named preset templates ("IHMC Saturday", "Skins Only")
- Shareable image export via native share sheet or download
- Full config syncs to all devices via Firebase

### Player Management
- Player profiles with GHIN handicap index, home course, tee preference
- Roster import from previous rounds
- "My Players" device-level player claiming
- Quick Add modal for fast player entry mid-round
- Player history with round-by-round scoring trends

### Results & Sharing
- Detailed results with gross and net breakdowns
- Stableford point calculations
- Signed digital scorecards
- Copy-to-clipboard text summaries
- CSV export for external analysis

### Quality of Life
- Dark mode (system preference or manual toggle)
- Interactive tutorials for each screen (Setup, Scoring, Side Games, Profile)
- Deep link support for sharing tournament join links
- Pull-to-refresh on scoring pages
- Notification system for sync events, errors, and confirmations
- Works fully offline after first load (service worker cached)

---

## Tech Stack

| Layer | Technology |
|-------|-----------|
| Frontend | Vanilla HTML/CSS/JS — single file, no framework |
| Sync | Firebase Firestore (real-time listeners) |
| Auth | Firebase Anonymous Auth (auto-created, optional) |
| Hosting | GitHub Pages + Netlify mirror |
| Offline | Service Worker with versioned cache |
| Course Data | External API (golfcourseapi.com) |

### Architecture

The entire app lives in two files:

- `index.html` — 34,800 lines, 1.7 MB. Contains all CSS, HTML, and JavaScript inline. 786 functions, 546 event handlers, 7 primary screens.
- `sw.js` — Service worker for offline caching with version-controlled cache busting.

No build step, no bundler, no dependencies to install. Deploy by copying two files.

### Data Storage

- **Firebase Firestore** — Tournament sync, user profiles, golf identity. Collections: `tournaments`, `users`, `userProfiles`.
- **localStorage** — Device-level preferences, cached round state, payout templates, custom courses. 22 keys namespaced by Firebase UID via `userGet`/`userSet` helpers.
- **Service Worker cache** — Offline-first with network fallback.

### Key Internal Systems

- **Newest-wins sync:** Every score entry gets a timestamp. On sync conflict, the most recent write wins per player per hole.
- **Deletion tombstones:** Deleted players are tracked so they don't resurrect from stale Firebase data.
- **User-scoped storage (v77):** All localStorage keys are prefixed with the user's Firebase UID, preventing data collision between accounts on shared devices.
- **Score timestamps:** `scoreTimestamps` object tracks `"playerName-holeIndex": timestamp` for granular conflict resolution.

---

## Screens

| Screen | Description |
|--------|-------------|
| **Setup** | Course search/selection, tournament name, date, handicap method, tee selection |
| **Host Home** | Tournament dashboard — join codes, player count, start round, payout calculator |
| **Guest Home** | Player view after joining — see tournament info, claim your player slot |
| **Scoring** | Hole-by-hole entry with player carousel, hole navigation, live leaderboard |
| **My Players** | Device-level player management — claim players, view your scores |
| **Player Management** | Host roster controls — add, remove, reorder, assign to devices |
| **Results** | Final leaderboard, signed scorecards, sharing, CSV export |

---

## Multi-Device Flow

```
Host Device                          Player Devices
─────────────                        ──────────────
1. Setup tournament
2. Select course
3. Start Multi-Device
4. Share player code ──────────────► 5. Enter player code
                                     6. Claim a player slot
7. See all players joined
8. Start round
9. Score on host device ◄──────────► 9. Score on own device
   (scores sync real-time)              (scores sync real-time)
10. Open payout calculator
11. Configure & calculate
    (config syncs to all) ─────────► 12. See read-only results
13. Share image / copy text
```

---

## Firebase Structure

```
tournaments/{tournamentId}
├── name, date, course, courseName
├── players[] — name, handicap, scores[], deviceId, addedAt
├── devices/{deviceId} — role, joinedAt, isCoHost
├── coHosts[] — array of device IDs
├── hostDeviceId, hostCode, playerCode
├── payoutConfig — full payout setup (synced to all devices)
├── scoreTimestamps — per-player-per-hole timestamps
└── deletedPlayers — tombstone array

userProfiles/{uid}
└── golfIdentity — name, handicap, homeCourse, tee, ghinNumber

users/{uid}
└── device preferences, saved state
```

---

## Running Locally

No build required. Serve the two files with any static server:

```bash
# Python
python3 -m http.server 8000

# Node
npx serve .

# Or just open index.html directly in a browser
# (Firebase sync requires HTTPS or localhost)
```

For full multi-device functionality, deploy to HTTPS (GitHub Pages, Netlify, etc.) or use `localhost`.

---

## Deployment

```bash
# Copy files to your hosting root
cp index.html sw.js /path/to/deploy/

# GitHub Pages
git add index.html sw.js
git commit -m "v1.0.91"
git push origin main
```

The service worker version (`CACHE_VERSION` in `sw.js`) controls cache busting. Bump it on every deploy so returning users get the update.

---

## IHMC Integration

Let's Golf has a secondary Firebase connection to the Indian Hills Men's Club app (`ihmc-golf` project). This integration is scaffolded but not yet fully wired:

- IHMC events can include `hostCode`/`playerCode` fields to auto-link tournaments
- Registered players from IHMC events can be imported as the tournament roster
- API key referrer restrictions need configuration for the Let's Golf domain

---

## Version History Highlights

| Version | What Changed |
|---------|-------------|
| v1.0.91 | Payout templates, custom splits, image export, config bleed fix |
| v1.0.90 | Hyper-save loop fix, co-host persistence, config isolation |
| v1.0.89 | Payout Calculator v2 — KP, Footlong, skins options, custom categories |
| v1.0.87 | Payout Calculator v1 — Firebase sync, host/player permissions |
| v15.9.81 | Tutorial system, deep links, course edit, max players 100 |
| v15.9.80 | User-scoped localStorage, Oak Quarry fix, auth prompts |
| v15.0.0 | Full UI reskin — navy/cardinal/forest/tan palette |
| v12.12.9 | Original README version — pre-Firebase, local-only scoring |

---

## License

Private project. Not open source.

---

*Built for the Indian Hills Men's Club and anyone who'd rather score on their phone than dig for a pencil.*
