# ⛳ Let's Golf by Otis Williams

A comprehensive golf tournament scoring application designed for men's golf clubs. Track scores in real-time, manage multiple game types, and share tournaments across devices.

## 🌟 Features

### 🎮 Two Scoring Modes

#### **Multi-Device Mode** (Default)
- Real-time tournament sharing across unlimited devices
- Live leaderboard updates
- QR code and shareable link for player registration
- Players can join mid-tournament
- Cloud-based score synchronization via Firebase
- Perfect for club tournaments and group events

#### **Single-Device Mode**
- Offline scoring on a single device
- No internet required
- Ideal for casual rounds or solo tracking
- All data stored locally

### 🏌️ Supported Game Types
- **Stroke Play** (Gross & Net)
- **Skins** (Gross, Net Full Handicap, Net 18 Max, Net 1/2 Pop)
- **Stableford** (Standard & Modified)
- **Best Ball** (2-Man, 3-Man, 4-Man)
- **Scramble** (2-Man, 3-Man, 4-Man)
- **Select Shot** (2-Man, 3-Man, 4-Man)

### 🏌️‍♂️ Supported Courses
- **Hidden Valley Golf Club**
- **Indian Hills Golf Club**
- **Jurupa Hills Country Club**

Each course includes:
- Complete hole-by-hole par and handicap ratings
- Front 9, Back 9, and total calculations
- Course rating and slope data

### 📊 Tournament Management

#### Setup Features
- Optional tournament naming (e.g., "Saturday Morning Scramble")
- Date selection
- Quick-add favorite players
- Import/export tournament data
- Team creation for team-based games

#### Scoring Features
- **Dual View Modes:**
  - Hole View: Score all players on each hole
  - Player View: Score all holes for each player
- Real-time progress tracking
- Auto-save functionality
- Resume saved rounds
- Live leaderboard (Multi-Device mode)

#### Results & Sharing
- Comprehensive results page
- Printable scorecards (Summary & Individual)
- Multiple export options:
  - Download as JSON
  - Print scorecards
  - Share results
- Tournament history tracking

### 🔗 Multi-Device Sharing (Multi-Device Mode Only)

When you return to the Setup page from an active tournament, the **Resume Round** section displays three sharing options:

#### **📱 QR Code**
- Generates scannable QR code
- Players scan to join tournament instantly
- No manual link entry required

#### **🔗 Share Link**
- Copies tournament join link to clipboard
- Share via text, email, or messaging apps
- One-click to copy

#### **💾 Save Tournament**
- Downloads complete tournament data as JSON file
- Includes all players, scores, and settings
- Archive completed tournaments
- Restore tournaments later

### 🎯 Player Management

#### Player Profiles
- Name and handicap tracking
- Quick-add favorite players
- Player history and statistics
- Import/export player lists

#### Handicap Options
- Positive handicaps (e.g., 10)
- Scratch (0)
- Plus handicaps (e.g., +2)
- Automatic stroke allocation by hole

### 📱 Mobile-Optimized
- Responsive design for all devices
- Touch-friendly interface
- Installable as Progressive Web App (PWA)
- Custom app icon
- Offline capability (Single-Device mode)

## 🚀 Getting Started

### Installation

1. **Upload Files:**
   - Upload `index.html` to your web server
   - Upload `apple-touch-icon.png` to the same directory

2. **Add to Home Screen:**
   - iOS: Safari → Share → Add to Home Screen
   - Android: Chrome → Menu → Add to Home Screen

### Quick Start

#### Starting a Multi-Device Tournament

1. **Setup:**
   - Scoring mode defaults to "Multi-Device"
   - Enter tournament name (optional)
   - Select date
   - Choose course
   - Select game type
   - Add players

2. **Start Tournament:**
   - Click "Start Scoring"
   - Tournament created with unique ID
   - Notification confirms creation

3. **Share Tournament:**
   - Click "← Back" to return to Setup page
   - "Resume Round" section appears with sharing options
   - **QR Code:** Tap to show scannable code
   - **Link:** Tap to copy shareable link
   - **Save:** Tap to download tournament file

4. **Players Join:**
   - Other players scan QR or open link
   - They register with name and handicap
   - Automatically added to tournament
   - Scores sync in real-time

5. **Scoring:**
   - Each device shows live updates
   - Score by hole or by player
   - Progress bar shows completion
   - Auto-saves continuously

6. **Results:**
   - Click "Results" when complete
   - View leaderboard
   - Print scorecards
   - Share final scores

#### Starting a Single-Device Tournament

1. **Setup:**
   - Toggle to "Single-Device" mode
   - Enter tournament details
   - Add players

2. **Score Offline:**
   - No internet required
   - All data stored locally
   - Resume anytime

3. **View Results:**
   - Print scorecards
   - Download tournament data
   - Share results via Results page

## 🎨 User Interface

### Color Scheme
- **Primary:** Blue gradient (#1e40af → #3b82f6)
- **Success:** Green (#10b981)
- **Accent:** Purple (#8b5cf6)
- **Background:** Dynamic gradient (green to blue)

### Key Design Elements
- Clean, modern interface
- Large touch targets for mobile
- Clear visual hierarchy
- Intuitive navigation
- Real-time feedback

## 💾 Data Management

### Local Storage (Single-Device)
- Automatic saving
- Resume interrupted rounds
- Player favorites
- Tournament history

### Cloud Storage (Multi-Device)
- Firebase Realtime Database
- Automatic synchronization
- Multi-device support
- Conflict resolution

### Export Options
- JSON format for tournaments
- Printable PDF scorecards
- Shareable result links

## 🔐 Privacy & Security

- No personal data collection
- Tournament data stored only in Firebase for Multi-Device mode
- Single-Device mode: 100% local, no cloud storage
- Tournaments auto-expire after completion
- No account creation required

## 📋 Technical Details

### Technologies Used
- **Frontend:** Pure HTML, CSS, JavaScript
- **Backend:** Firebase (Multi-Device mode only)
- **Storage:** LocalStorage + Firebase Realtime Database
- **Icons:** Custom gradient icon (180x180)

### Browser Support
- Safari (iOS 13+)
- Chrome (Android/Desktop)
- Firefox
- Edge

### Requirements
- **Multi-Device Mode:** Internet connection required
- **Single-Device Mode:** Works completely offline
- Modern web browser with JavaScript enabled

## 🎯 Best Practices

### For Tournament Hosts

1. **Start Early:** Create tournament before players arrive
2. **Share Immediately:** Display QR code at clubhouse or first tee
3. **Verify Players:** Check all players joined before starting
4. **Save Backup:** Download tournament file before starting (Safety!)
5. **Monitor Progress:** Check live leaderboard periodically

### For Players

1. **Join Promptly:** Scan QR code or use link before teeing off
2. **Enter Scores Immediately:** Update after each hole
3. **Verify Data:** Check your scores match the group
4. **Stay Connected:** Keep internet on for real-time sync

### For Scoring

1. **Use Hole View:** Fastest for group scoring
2. **Use Player View:** Best for individual review
3. **Double Check:** Verify scores before moving to next hole
4. **Save Often:** App auto-saves, but click "Back" periodically

## 🆘 Troubleshooting

### Common Issues

**Tournament Won't Start:**
- Verify all required fields filled
- Check internet connection (Multi-Device mode)
- Refresh page and try again

**Can't Join Tournament:**
- Verify link/QR code is current
- Check internet connection
- Make sure tournament hasn't ended

**Scores Not Syncing:**
- Check internet connection
- Verify you're in Multi-Device mode
- Refresh page to force sync

**Resume Round Not Showing:**
- Check you're on Setup page
- Verify tournament was started
- Check LocalStorage not cleared

## 📞 Support

For issues, feature requests, or questions:
- Created by: Otis Williams
- For: Men's Golf Club tournament management
- Version: 2.0 (January 2026)

## 🔄 Recent Updates

### Version 2.0 (January 2026)
- ✨ Added Multi-Device and Single-Device scoring modes
- ✨ Added optional Tournament Name field
- ✨ Tournament name displays on all pages and printouts
- ✨ Redesigned sharing with QR/Link/Save buttons in Resume section
- ✨ Improved mobile responsiveness
- ✨ Enhanced tournament save/export functionality
- ✨ Updated app icon with gradient design
- 🐛 Fixed multi-device tournament creation bug
- 🐛 Fixed player registration issues

### Version 1.0 (December 2025)
- Initial release
- Basic scoring functionality
- Cloud-based tournaments
- Multiple game types

## 📜 License

Created for personal and club use. Feel free to modify and adapt for your golf club's needs.

---

**⛳ Let's Golf!** - Making golf tournament scoring simple and fun.
