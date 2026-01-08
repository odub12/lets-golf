# ⛳ Let's Golf by Otis Williams

A modern, mobile-first golf scoring application designed for tournament management and live scoring. Built as a Progressive Web App (PWA) that works seamlessly on iOS, Android, and desktop browsers.

---

## 🌟 Features

### Scoring Modes
- **Multi-Device Mode** - Real-time collaborative scoring with Firebase sync. Share a QR code or link to let multiple scorers join your tournament.
- **Single-Device Mode** - Traditional scoring for when one device handles all scores.

### Game Types Supported
- Stroke Play (Gross & Net)
- Gross Skins
- Net Skins (Full Handicap)
- Net Skins (18 Max)
- Net Skins (1/2 Pop)
- Stableford
- Best Ball
- Scramble

### Scoring Views
- **Hole View** - Score one hole at a time for all players. Swipe left/right to navigate between holes.
- **Player View** - See a complete scorecard for each player. Features a 6-column x 3-row compact layout with swipe navigation between players.

### Input Methods
- **Touch Mode** - Tap +/− buttons or tap scores to open an expanded input modal with quick-select buttons.
- **Voice Mode** - Speak scores hands-free. Just tap a score cell and say the number.

### Putt Tracking
- **[P] Button** - Small purple button next to each player's name in Hole View
- **Quick Entry** - Tap to open putt popup, tap 0-6 to record putts instantly
- **Visual Indicator** - Button shows putt count when entered (e.g., [2])
- **Scorecard Integration** - PUTTS column appears on scorecards when complete data exists
- **Firebase Sync** - Putt data syncs across all devices in multi-device mode

### Multi-Device Collaboration
- **Host Controls** - Create tournaments, manage players, share invite links/QR codes.
- **Co-Host Support** - Promote trusted scorers to co-host status for shared management.
- **Claim Players** - Each device can claim specific players to score for.
- **Watch Players** - View (read-only) other players' scores without claiming them.
- **Real-time Sync** - All scores update instantly across all connected devices via Firebase.
- **Newest-Wins Conflict Resolution** - Intelligent merging when multiple devices edit simultaneously.

### Additional Features
- **Auto-Save** - Scores are automatically saved to local storage and synced to the cloud.
- **Resume Round** - Pick up exactly where you left off, even after closing the browser.
- **Scorecard Modal** - View a traditional scorecard layout with front 9, back 9, and totals.
- **Results Page** - See final standings with sorting by gross/net scores.
- **Live Leaderboard** - Real-time standings during play.
- **Player Management** - Add, edit, or remove players mid-round (host only).
- **Quick Add Players** - Save frequently used players with handicaps for one-tap adding.
- **Handicap Dots** - Visual indicators showing strokes received on each hole.
- **Net Score Display** - See net scores alongside gross scores in Hole View.
- **PWA Support** - Install to your home screen for a native app experience.

---

## 📱 Supported Courses

The app comes pre-configured with the following courses:

| Course | Par | Holes |
|--------|-----|-------|
| Indian Hills Golf Club | 70 | 18 |
| Jurupa Hills Country Club | 70 | 18 |
| Green River Golf Club | 71 | 18 |
| Hidden Valley Golf Club | 72 | 18 |

Each course includes complete hole-by-hole data: par values, handicap rankings, and yardages.

---

## 🚀 Getting Started

### Quick Start
1. Open the app in your browser at your hosted URL (e.g., `https://yourusername.github.io`)
2. Select **Multi-Device** or **Single-Device** mode
3. Set the tournament date and optionally name your tournament
4. Select your course and game type
5. Add players using Quick Add buttons or manually enter names and handicaps
6. Tap **Start Scoring**

### Installing as a PWA (iOS)
1. Open the app in Safari
2. Tap the **Share** button (square with arrow)
3. Scroll down and tap **Add to Home Screen**
4. Name it "Let's Golf" and tap **Add**
5. Launch from your home screen for fullscreen experience

### Installing as a PWA (Android)
1. Open the app in Chrome
2. Tap the menu (three dots)
3. Tap **Add to Home Screen** or **Install App**
4. Confirm installation

---

## 🎮 How to Use

### Starting a Round

1. **Choose Scoring Mode**
   - *Multi-Device*: Creates a cloud tournament that others can join
   - *Single-Device*: All scoring happens on one device

2. **Configure Tournament**
   - Set the date
   - Name your tournament (optional)
   - Select the course
   - Choose the game type

3. **Add Players**
   - Tap Quick Add buttons for saved players
   - Or type a name and handicap, then tap "+ Add Player"
   - Swipe left on a player to delete them

4. **Start Scoring**
   - Tap the "Start Scoring" button
   - You'll be taken to the Hole View by default

### Scoring

**Hole View (Default)**
- Shows the current hole with all players listed
- Tap the score circle to open expanded input with quick-select buttons
- Swipe left/right or use navigation buttons to change holes
- Tap the hole number to jump to any hole

**Player View**
- Tap "Players" button to switch views
- Shows complete 18-hole scorecard per player
- Swipe left/right to navigate between players

**Voice Input**
- Tap "Voice" to enable voice mode
- Tap any score cell
- Speak the score clearly (e.g., "four" or "bogey")
- The app recognizes numbers and golf terms

### Tracking Putts

1. In Hole View, find the **[P]** button next to each player's name
2. Tap **[P]** to open the putt popup
3. Tap a number (0-6) to record putts for that hole
4. The popup closes automatically and the button shows the putt count
5. To clear a putt entry, tap **[P]** and then tap **Clear**

**Viewing Putt Totals:**
- Open the Scorecard (📋 button)
- If any player has complete putt data (all 18 holes), a **PUTTS** column appears
- Players with incomplete data show "--"

### Multi-Device Sharing

When you start a Multi-Device tournament:
1. Tap **Home** to return to the Host Home page
2. Tap:
   - **🔗 Link** - Copy invite link to clipboard
   - **📱 QR** - Display QR code for others to scan
   - **💾 Save** - Download tournament data as a file

Other scorers can:
- Scan the QR code
- Click/tap the shared link
- Enter their initials when joining
- Claim players they want to score for
- Watch other players' scores in real-time

### Viewing Results

1. Tap the **🏆** (trophy) button in the header
2. Use the dropdown to switch between result views:
   - Stroke Play Gross
   - Stroke Play Net
   - Gross Skins
   - Net Skins (various handicap methods)
   - Stableford
3. Tap **Finish** when the round is complete to clear data and start fresh

---

## 📋 Scorecard Features

Tap the **📋 Card** button to open the scorecard modal:

### View Options
- **All Players - Summary Table** - Compact view with all players
- **All Players - Individual Cards** - Detailed card for each player
- **My Players - Summary Table** - Only your claimed/watched players
- **My Players - Individual Cards** - Detailed cards for your players
- **Individual Player** - Select a specific player

### Score Display
- Front 9, back 9, and total scores
- Gross and net scores (when applicable)
- Relative to par (+/−)
- **PUTTS column** - Shows total putts when complete data exists

### Color Coding
- 🟢 Green = Birdie or better
- 🔵 Blue = Par
- 🟡 Yellow/Orange = Bogey
- 🔴 Red = Double bogey or worse

---

## 🔧 Technical Details

### Technology Stack
- **Frontend**: Vanilla HTML, CSS, JavaScript (single-file application)
- **Backend**: Firebase Firestore (real-time database)
- **Authentication**: Firebase Anonymous Auth
- **Hosting**: GitHub Pages (or any static host)

### Browser Support
- Safari (iOS 13+)
- Chrome (Android, Desktop)
- Firefox
- Edge

### Data Storage
- **Local**: localStorage for offline capability and auto-save
- **Cloud**: Firebase Firestore for multi-device sync

### File Structure
```
index.html      - Complete single-file application
manifest.json   - PWA manifest (if using)
README.md       - This file
```

---

## 🛠️ Configuration

### Adding New Courses

To add a new course, find the `courses` object in the JavaScript section and add a new entry:

```javascript
courses.your_course = {
    name: "Your Course Name",
    par: 72,
    totalPar: 72,
    holes: [
        { number: 1, par: 4, handicap: 7, yards: 385 },
        { number: 2, par: 3, handicap: 15, yards: 165 },
        // ... continue for all 18 holes
    ]
};
```

Then add the course to the dropdown in the HTML:
```html
<option value="your_course">Your Course Name</option>
```

### Adding Quick Add Players

Quick Add players are stored in localStorage. To add default players, find the `quickAddPlayers` array and modify it:

```javascript
let quickAddPlayers = [
    { name: "Player Name", handicap: 12 },
    // Add more players
];
```

---

## 📝 Version History

### v7.5 - 2025-01-08 (Putt Tracking)
- **NEW**: Putt tracking feature with [P] button next to player names
- **NEW**: Putt input popup with quick-tap 0-6 buttons
- **NEW**: PUTTS column on scorecards (shows when complete data exists)
- **NEW**: Putt data syncs via Firebase in multi-device mode
- UI refinements and bug fixes

### v7.4 - 2025-01-08 (UI Refinements)
- Improved hole view player rows
- Enhanced score input modal
- Better mobile responsiveness

### v7.0 - 2025-01-04 (Multi-Device Overhaul)
- Multi-device collaborative scoring with Firebase
- Real-time sync across all connected devices
- Hole View and Player View scoring modes
- Voice input for hands-free scoring
- QR code and link sharing for tournaments
- Watch players feature for non-hosts
- Co-host support for shared management
- Newest-wins conflict resolution
- Auto-save and round resume capability

---

## 🤝 Support

For issues, feature requests, or questions:
- Create an issue on the GitHub repository
- Contact: Otis Williams

---

## 📄 License

© 2026 Otis Williams. All Rights Reserved.

This software and its source code are the intellectual property of Otis Williams. Unauthorized copying, modification, distribution, or use of this code, in whole or in part, is strictly prohibited without prior written permission from the copyright holder.

---

## 🙏 Acknowledgments

- Built with ❤️ for the Indian Hills Men's Golf Club
- Designed and developed by Otis Williams
- Powered by Firebase for real-time collaboration

---

*Happy Golfing! ⛳🏌️‍♂️*
