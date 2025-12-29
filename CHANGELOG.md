# Decrypto Game - Version History

## v2.3.0 (Current) - Opponent Clue Tracker
**Released:** December 28, 2024

### Major New Feature
- ✅ **Clue Tracker:** Visual reference grid showing opponent's clues organized by word number (1-4)
- ✅ **Historical tracking:** See all clues from past rounds organized by which word they referenced
- ✅ **Current round highlighting:** This round's clues highlighted in yellow
- ✅ **Strategic tool:** Helps guessers identify patterns and improve interception attempts
- ✅ **Board game authentic:** Matches the reference sheets from the physical Decrypto game

### UI Improvements
- Clue tracker positioned between action section and history for easy reference
- Round labels (R1:, R2:, etc.) for quick identification
- Color-coded by team (blue/orange)

---

## v2.2.1 - Collapsible Game History
**Released:** December 28, 2024

### New Features
- ✅ **Collapsible rounds:** Click on any round to expand/collapse full details
- ✅ **Animated accordions:** Smooth expand/collapse with rotating arrow icon
- ✅ **Hover effects:** Visual feedback when hovering over rounds
- ✅ **Complete round data:** Each round shows codes, clues, guesses, interceptions, and results
- ✅ **Color-coded sections:** Team A (blue) and Team B (orange) backgrounds in history

### UI Improvements
- Game history is now interactive and space-efficient
- Multiple rounds can be expanded simultaneously
- Better visual organization with clear team separation

---

## v2.2.0 - Fair Win Conditions
**Released:** December 28, 2024

### Bug Fixes & Improvements
- ✅ **Fixed:** Both teams reaching 2 miscommunications simultaneously now results in a TIE
- ✅ **Fixed:** Both teams getting 2 interceptions simultaneously now results in a TIE
- ✅ **Improved:** 8-round limit winner determination with clear priority system
- ✅ **Improved:** Winner messages now include detailed scores

### Win Condition Logic
**During game (before round 8):**
- 2 miscommunications → Opponent wins
- 2 interceptions → That team wins
- Both hit limit simultaneously → TIE GAME

**At round 8:**
1. Fewest miscommunications wins
2. If tied, most interceptions wins
3. If still tied, perfect tie

### Score Display
- ✅ Reorganized to group by team color (Blue-Blue-Orange-Orange instead of alternating)

---

## v2.1.3 - Error Handling Fix
**Released:** December 28, 2024

### Bug Fixes
- ✅ **Fixed:** "Cannot read properties of undefined (reading 'push')" error during interception
- ✅ Added safety checks for `rounds` array before pushing
- ✅ Added safety checks for team score objects before incrementing
- ✅ Graceful handling of missing data structures

---

## v2.1.2 - Phase 3 & UI Update Fixes
**Released:** December 28, 2024

### Bug Fixes
- ✅ **Fixed:** Clue-givers now see Phase 3 (Results screen)
- ✅ **Fixed:** Buttons disappear immediately after submission (guess/interception)
- ✅ Added specific phase handling for clue-givers during all phases
- ✅ Immediate UI re-render after form submissions

### UI Improvements
- Clue-givers see status updates during guessing phase
- Better "waiting" messages explaining what's pending
- Instant visual feedback when actions complete

---

## v2.1.1 - Improved Feedback
**Released:** December 28, 2024

### New Features
- ✅ **Immediate feedback:** Alert shows if guess was correct/wrong when submitted
- ✅ **Interception feedback:** Alert shows if interception succeeded immediately
- ✅ **Enhanced results screen:** Bigger, clearer display of codes and outcomes
- ✅ Results visible to both clue-givers and guessers

### UI Improvements
- Secret codes displayed in larger, color-coded text
- Clear success/fail indicators with ✓/✗ symbols
- "Continue to Round X" button with next round number

---

## v2.1.0 - Unique Player Identity System
**Released:** December 28, 2024

### New Features
- ✅ **Unique Player IDs:** Each browser tab gets its own player identity
- ✅ **Multi-tab support:** Open multiple tabs in same browser, each with different role
- ✅ **Cross-device ready:** Works perfectly across different devices and networks
- ✅ **Session persistence:** Player identity persists across page refreshes
- ✅ **Player ID display:** See your unique ID in the game info (for debugging)

### Technical Changes
- Generated unique player IDs: Format `P{timestamp}{random}` (e.g., `Plsq3a5h8abc12`)
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

### v2.4.0 (Planned)
- [ ] Export game history as PDF/image
- [ ] Better mobile layout for small screens
- [ ] Sound effects toggle
- [ ] Dark mode

### v2.5.0 (Planned)
- [ ] Customizable word banks
- [ ] Game rooms with passwords
- [ ] Spectator mode
- [ ] Timer for turns

### v3.0.0 (Future)
- [ ] AI opponent mode
- [ ] Tournament brackets
- [ ] Player profiles and stats
- [ ] Achievements/badges
- [ ] Leaderboards

---

## Summary of All Bug Fixes

### v2.3.0
- N/A (new feature release)

### v2.2.1
- N/A (new feature release)

### v2.2.0
- Fixed: Simultaneous win conditions not handled fairly
- Fixed: 8-round limit winner calculation unclear

### v2.1.3
- Fixed: rounds.push() error during interception
- Fixed: Missing score objects causing crashes

### v2.1.2
- Fixed: Clue-givers couldn't see results phase
- Fixed: Buttons remaining after submission
- Fixed: Phase 3 not displaying for all players

### v2.1.1
- Fixed: No feedback after guess submission
- Fixed: Results screen not prominent enough

### v2.1.0
- Fixed: Multiple tabs sharing same identity
- Fixed: Browser refresh losing player state

### v2.0.1
- Fixed: Multiple browsers showing same setup
- Fixed: Player identity not persisting

### v2.0.0
- Fixed: Codes with repeated numbers
- Fixed: Duplicate codes in same game
- Fixed: Game continuing past intended limit
- Fixed: Unable to see opponent's progress
- Fixed: Results not displaying correctly
- Fixed: roundData undefined errors

---

## Credits

**Built with:**
- Firebase Realtime Database
- Vanilla JavaScript
- CSS3
- Love for word games ❤️

**Inspired by:**
The board game **Decrypto** by Thomas Dagenais-Lespérance

**Developed:** December 2024

**Current Version:** v2.3.0

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
