# Let's Golf ⛳

A comprehensive mobile-first golf tournament scoring and management application.

**Version:** 10.13  
**Last Updated:** January 13, 2025

---

## 🎯 Overview

Let's Golf is a single-file HTML application designed for real-time golf tournament scoring with support for multiple devices, various game formats, and detailed statistics tracking. Perfect for casual rounds with friends or organized club tournaments.

---

## ✨ Key Features

### 🏌️ Tournament Modes

- **Single Device Mode** - Score your round on one device
- **Multi-Device Mode** - Host/player tournament with real-time sync via Firebase
  - **Host** creates tournament and manages all settings
  - **Co-Host** can help manage (uses host code)
  - **Players** join via 6-character code, claim and score their players

### 📊 Game Formats

| Format | Description |
|--------|-------------|
| **Stroke Play** | Traditional scoring - lowest total wins |
| **Skins** | Win the hole outright to win a skin |
| **Stableford** | Points-based scoring system |
| **Stableford (Modified)** | Includes negative points for high scores |
| **Nassau** | Front 9, Back 9, and Overall competitions |
| **Footlong** | Game with -3/+3 scoring per hole |

### 🎲 Side Games (Best Ball)

- Configure teams with 2-4 players each
- Set how many scores count per hole (1, 2, or 3)
- Choose format: Stroke Play, Skins, or Stableford
- Visual toggle between Tourney and Side Game views

### 📈 Scoring Methods

- **Gross** - Raw scores
- **Net** - Full handicap strokes applied
- **Net 18** - Maximum 18 strokes (capped)
- **Net ½** - Half-pop handicap (Skins only)

---

## 📱 Views

### Home Page
- Resume existing round
- Start new round (single or multi-device)
- Join existing tournament via code

### Player View (Scorecard)
- Swipeable carousel of player cards
- 6x3 grid showing all 18 holes
- Color-coded scores (birdie, par, bogey, double+)
- Net scores displayed below gross
- Running total with to-par through holes played

### Hole View
- Score entry for current hole
- Handicap dots indicator
- Stats tracking buttons (FIR, GIR, Putts, Dots)
- Running gross and net totals
- Swipe or tap arrows to navigate holes

### Results / Leaderboard
- Real-time leaderboard with rankings
- Filter: My Players / All Players
- Toggle between Tourney and Side Game
- Medal indicators (🥇🥈🥉)
- Skins display winning scores: "Holes: 1(4), 2(3)"

### Scorecards Modal
- **Summary Table** - All players in scrollable grid with stats columns
- **Individual Cards** - Detailed per-player scorecards
- Stats rows: FIR, GIR, Putts, Dots (when data exists)

---

## 📊 Stats Tracker

Track detailed statistics for each player:

| Stat | Description | Display |
|------|-------------|---------|
| **FIR** | Fairway in Regulation | ✓/✗ (skipped on Par 3s) |
| **GIR** | Green in Regulation | ✓/✗ |
| **Putts** | Number of putts | 0-4 quick select, # for 5+ |
| **Dots** | Game-specific dots/points | 0-4 quick select, # for 5+ |

### Stats in Hole View
- Compact buttons below score input
- Green fill = hit, Red fill = miss
- Running totals shown below each button

### Stats on Scorecards
- Summary table shows totals for each stat
- Individual cards show per-hole breakdown
- Only displays stats that have data entered

---

## 🔧 Player Management

### My Players Page
- **Claimed Players** (yellow) - You're scoring these
- **Watching** (blue) - See scores, can't edit
- **Available** - Can claim or watch
- Reorder players with ↑↓ buttons
- Edit handicaps inline

### Host/Co-Host Tools
- Add/remove players mid-round
- Edit any player's handicap
- Access all management features
- Clear all scores option

---

## 🏆 Course Support

**Built-in Course:** Indian Hills Golf Club (Riverside, CA)
- Par 70 (35/35)
- Full hole-by-hole data with handicap ratings

**Course Selection:**
- Multiple tee options when available
- Handicap ratings per hole for net calculations

---

## 💾 Data & Sync

### Local Storage
- Round data persists in browser
- Stats tracker data saved per device
- Player order preferences remembered
- Best Ball team configurations saved

### Firebase Sync (Multi-Device)
- Real-time updates across all devices
- Visual sync indicator
- Auto-reconnect on connection loss
- Offline capability with sync on reconnect

---

## 🎨 UI Features

- **Dark/Light modes** for outdoor visibility
- **Fullscreen mode** for focused scoring
- **Mobile-optimized** touch targets
- **Swipe gestures** for navigation
- **Color-coded scores** for quick recognition
- **Haptic feedback** on score entry
- **Pull-to-refresh** for manual sync

---

## 🚀 Quick Start

### Solo Round
1. Tap "Start New Round"
2. Select "Single Device"
3. Add players and handicaps
4. Choose game type
5. Start scoring!

### Host a Tournament
1. Tap "Start New Round"
2. Select "Multi-Device (Host)"
3. Configure tournament settings
4. Share the **Join Code** with players
5. Share **Host Code** with co-hosts (optional)

### Join a Tournament
1. Tap "Join Tournament"
2. Enter the 6-character code
3. Set your device name
4. Claim your players
5. Start scoring!

---

## 📋 Version History

### v10.13 (Current)
- Stats columns on scorecards (FIR, GIR, Putts, Dots)
- Per-hole stats on individual player cards

### v10.12
- Tourney/Side Game visual toggle
- Stats tracker reorder (FIR → GIR → Putts → Dots)
- Smaller stat buttons in Hole View
- Putts/Dots popup with # for 5+
- Skins show winning scores
- Fixed Player Card running total bug
- Net score added to Hole View running totals

### v10.11
- Stats tracker system (FIR, GIR, Putts, Dots)
- Running totals in Hole View

### v10.x
- Best Ball / Side Game support
- Multiple scoring methods
- Co-host functionality
- Player claiming system

---

## 📄 Technical Details

- **Single HTML file** - No build process required
- **Firebase Firestore** - Real-time database
- **No dependencies** - Vanilla JS, CSS
- **PWA-ready** - Can be installed on mobile
- **Responsive** - Works on phone, tablet, desktop

---

## 🤝 Credits

Developed for **Indian Hills Men's Golf Club**  
Built with ❤️ for the love of the game

---

*Let's Golf!* 🏌️‍♂️⛳
