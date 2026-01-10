# Let's Golf ⛳
### by Otis Williams

A professional-grade, mobile-optimized golf tournament scoring application designed for men's golf clubs and casual tournaments alike.

---

## Overview

Let's Golf is a real-time, multi-device golf scoring system that eliminates the need for paper scorecards and complicated spreadsheets. Host a tournament from your phone, share a simple 6-character code, and let players score from their own devices with live leaderboard updates.

---

## Key Features

### 🏌️ Tournament Management
- **Host or Join** - Create tournaments as a host or join existing ones with a simple code (e.g., GOLF42)
- **Multi-Device Sync** - Real-time Firebase synchronization across all connected devices
- **Co-Host Support** - Delegate management responsibilities to trusted players
- **Auto-Rejoin** - Recognized devices automatically reconnect to active tournaments

### 📊 Flexible Game Formats
- **Stroke Play** - Traditional total score competition
- **Skins** - Hole-by-hole winner-take-all format
- **Stableford** - Points-based scoring (standard & modified)
- **Nassau** - Front 9, Back 9, and Overall winners
- **Footlong** - Front 9 and Back 9 competitions
- **Best Ball** - Team format with customizable options:
  - 1-4 players per team
  - 1-3 best scores per hole
  - Stroke Play or Match Play format

### 🎯 Scoring Options
- **Gross** - Raw scores
- **Net (Full Handicap)** - Full handicap strokes applied
- **Net (18 Max)** - Capped at 18 strokes maximum
- **Net (½ Pop)** - Half-stroke handicap (Skins only)

### 📱 Mobile-First Design
- Optimized for phones and tablets
- Touch-friendly score entry with +/- buttons
- Swipe navigation between holes
- Hole-by-hole view or full scorecard grid
- Color-coded scores (eagle, birdie, par, bogey, double+)
- Dark mode support

### 🏆 Live Leaderboard
- Real-time standings updates
- Filter by "My Players" or "All Players"
- Multiple scoring method views
- Tiebreaker logic on handicap holes

### 👥 Player Management
- Claim players to score for them
- Watch other players' progress
- Edit handicaps mid-round
- Add/remove players on the fly

### 💾 Data & History
- Tournament history with search
- Save tournament files (JSON backup)
- Load previous tournaments
- Persistent device recognition

---

## How It Works

### For Hosts
1. Open Let's Golf and tap **"Host New Tournament"**
2. Enter tournament details (date, game type, course)
3. Add players with names and handicaps
4. Start the tournament and share the **6-character code**
5. Manage players, view live results, finish when done

### For Players
1. Get the tournament code from your host
2. Open Let's Golf and enter the code
3. Claim yourself (or players you're scoring for)
4. Enter scores hole-by-hole
5. View live leaderboard anytime

---

## Supported Courses

Currently optimized for:
- Indian Hills Golf Club
- Jurupa Hills Country Club
- *(Additional courses can be added)*

---

## Technical Details

- **Platform**: Progressive Web App (HTML/CSS/JavaScript)
- **Backend**: Firebase Firestore (real-time database)
- **Authentication**: Anonymous device-based identification
- **Offline**: Partial offline support with local storage
- **Install**: Add to Home Screen for app-like experience

---

## Version History

### v8.1 (Current)
- Best Ball Team Builder with full customization
- Match Play scoring (3&2, 2UP, AS format)
- Consolidated game types
- Dynamic scoring method buttons (Gross/Net/Net18/Net½)
- Footlong and Nassau game formats
- Improved results page layout
- Load Tournament modal with join-by-code

### v7.x
- Join-by-code system
- Tournament history
- Auto-rejoin functionality
- Leave tournament options
- UI/UX refinements

### v6.x
- Multi-device real-time sync
- Host/Co-host system
- Player claiming mechanism
- Live leaderboard

---

## Installation

### As a Web App
Simply visit the hosted URL in any modern browser.

### As a Home Screen App (Recommended)
**iOS:**
1. Open in Safari
2. Tap Share → "Add to Home Screen"
3. Launch from home screen for full-screen experience

**Android:**
1. Open in Chrome
2. Tap Menu → "Add to Home Screen"
3. Launch from home screen

---

## Future Roadmap

- [ ] Additional course databases
- [ ] Player statistics & history
- [ ] Handicap tracking over time
- [ ] Tournament templates
- [ ] Push notifications
- [ ] Offline-first architecture
- [ ] Export to PDF scorecards

---

## License

© 2026 Otis Williams. All Rights Reserved.

This software and its source code are the intellectual property of Otis Williams. Unauthorized copying, modification, distribution, or use of this code, in whole or in part, is strictly prohibited without prior written permission from the copyright holder.

For licensing inquiries, contact the author.

---

## Credits

Developed with ❤️ for the golf community.

*Let's Golf - Making tournament scoring simple.*
