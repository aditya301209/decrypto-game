# Decrypto Game - Version History

## v2.1.0 (Current) - Unique Player Identity System
**Released:** December 28, 2024

### New Features
- ✅ **Unique Player IDs:** Each browser tab gets its own player identity
- ✅ **Multi-tab support:** Open multiple tabs in same browser, each with different role
- ✅ **Cross-device ready:** Works perfectly across different devices and networks
- ✅ **Session persistence:** Player identity persists across page refreshes
- ✅ **Player ID display:** See your unique ID in the game info (for debugging)

### Technical Changes
- Generated unique player IDs: `player_timestamp_randomstring`
- Player identity stored as: `decrypto_{playerId}_gameCode/team/role`
- Auto-rejoin after page refresh using stored player ID
- Each tab/window maintains independent identity

### How It Works
- **Firebase (Cloud):** Shared game state for all players
- **sessionStorage (Local):** Individual player identity per tab
- Perfect for remote multiplayer across different networks!

---

## v2.0.1 - Session Identity Fix
**Released:** December 28, 2024

### Bug Fixes
- ✅ **Fixed:** Multiple browsers on same computer now maintain separate identities
- ✅ **Fixed:** Each browser tab remembers its team/role selection independently
- ✅ Uses sessionStorage to keep player identity per browser session
- ✅ Player identity persists across page refreshes

### Technical Changes
- Player identity (team/role) stored in browser sessionStorage instead of Firebase
- Session cleared when leaving game
- Identity restored on page refresh

---

## v2.0.0 - Simultaneous Play Edition
**Released:** December 28, 2024

### Major Features
- ✅ **Simultaneous gameplay**: Both teams play at the same time
- ✅ **Three-phase system**: Clues → Guessing → Results
- ✅ **Real-time synchronization**: Firebase-powered multiplayer
- ✅ **Status indicators**: See what actions are pending
- ✅ **Opponent clue visibility**: See opponent's submitted clues

### Game Rules
- ✅ **Unique codes**: No repeated numbers in a code (e.g., [1,2,3] not [1,1,2])
- ✅ **No duplicate codes**: Each code appears only once per game
- ✅ **8 round maximum**: Game ends after 8 rounds
- ✅ **Win conditions**: 2 miscommunications or 2 interceptions ends game early

### Technical Improvements
- ✅ Comprehensive error handling
- ✅ Safety checks for data structure
- ✅ Console logging for debugging
- ✅ Version display in UI

### UI Enhancements
- ✅ Phase indicator with round counter (e.g., "Round 3/8")
- ✅ Color-coded team displays (Blue/Orange)
- ✅ Responsive design for mobile
- ✅ Clear status messages

---

## v1.0.0 - Sequential Play Edition
**Initial Release**

### Features
- Sequential turn-based gameplay
- Teams alternate giving clues
- Basic Firebase integration
- Simple UI

### Known Issues (Fixed in v2.0.0)
- ❌ Slow gameplay (teams wait for each other)
- ❌ Codes could have repeated numbers
- ❌ Same code could appear multiple times
- ❌ No round limit
- ❌ Limited visibility into game state

---

## Version Numbering

We use semantic versioning: `MAJOR.MINOR.PATCH`

- **MAJOR**: Breaking changes or complete redesigns
- **MINOR**: New features, gameplay improvements
- **PATCH**: Bug fixes, small tweaks

---

## Planned Features (Future Versions)

### v2.1.0 (Planned)
- [ ] Game history/archive feature
- [ ] Ability to replay past rounds
- [ ] Better mobile layout for small screens
- [ ] Sound effects for actions
- [ ] Animated transitions between phases

### v2.2.0 (Planned)
- [ ] Customizable word banks
- [ ] Private game rooms with passwords
- [ ] Spectator mode
- [ ] In-game chat

### v3.0.0 (Future)
- [ ] AI opponent mode
- [ ] Tournament bracket system
- [ ] Player profiles and stats
- [ ] Achievements/badges

---

## Bug Fixes by Version

### v2.0.0
- Fixed: roundData undefined error
- Fixed: Codes with repeated numbers
- Fixed: Duplicate codes in same game
- Fixed: Game continuing past 8 rounds
- Fixed: Unable to see opponent's progress
- Fixed: Results not displaying correctly

### v1.0.0
- Initial release

---

## Credits

Built with:
- Firebase Realtime Database
- Vanilla JavaScript
- CSS3
- Love for word games ❤️

Inspired by the board game **Decrypto** by Thomas Dagenais-Lespérance
