# Decrypto Game - Version History

## v3.0.0 (Current) - Flexible Roles & Expanded Word Bank 🎉
**Released:** December 28, 2024

### 🎭 MAJOR GAMEPLAY CHANGE: Flexible Role System
**Revolutionary new approach to team roles!**

**Old System:**
- Players chose "Clue-Giver" or "Guesser" when joining
- Same person gave clues every round
- Fixed roles throughout the game

**New System:**
- Players only choose their team when joining
- Each round, ANY player can claim the clue-giver role
- First to click "🙋 I'll Give Clues This Round!" becomes that round's clue-giver
- Everyone else automatically becomes a guesser
- Roles reset every round - fresh opportunity for everyone!

### Benefits of Flexible Roles
- ✅ **Everyone participates actively** - No more sitting on sidelines
- ✅ **Shared responsibility** - Take turns giving clues
- ✅ **More engaging** - All players stay involved every round
- ✅ **Strategic depth** - Pick the best clue-giver for each set of words
- ✅ **Fair distribution** - No one is stuck in one role

### 📚 Expanded Word Bank (120 Words!)
**Added 56 new words** (previously 64, now 120):
- Animals: BEAR, BIRD, EAGLE, HORSE, SNAKE
- Objects: ANCHOR, BALLOON, BOTTLE, CAMERA, CANDLE, CHAIR, COMPASS, HAMMER, LADDER, LAMP, NEEDLE
- Food: APPLE, BUTTER, CHEESE, COFFEE, HONEY
- Nature: BEACH, DESERT, FEATHER, FLAME, FLOWER, FOUNTAIN, GALAXY, GARDEN, ICE, ISLAND, JUNGLE, LEAF, LIGHTNING, PLANET, RAINBOW, SMOKE
- Materials: CRYSTAL, GOLD, MARBLE, METAL, PAINT, PAPER, PEARL, RUBY, SILVER
- Concepts: CIRCLE, DANCE, ENGINE, GIANT, GUITAR, JEWEL, MASK, MUSIC, PHOENIX, PYRAMID

### Technical Implementation
- Added `clueGiverClaimed` flag to roundData
- `claimClueGiverRole()` function for role claiming
- Automatic role reset at round start
- Firebase synchronization of claimed status
- Removed fixed role selection from join screen

### UI Changes
- Simplified join screen (no role dropdown)
- New claim button interface during clue phase
- Player info shows team only (no fixed role)
- Status message explains flexible role system

---

## v2.4.0 - Mobile-Friendly & Responsive
**Released:** December 28, 2024

### Mobile Optimization
- ✅ **Comprehensive responsive design** for tablets and phones
- ✅ **Touch-friendly interactions** with minimum 44px touch targets
- ✅ **Prevents iOS zoom** on input focus (16px font size)
- ✅ **Disabled double-tap zoom** for smoother experience
- ✅ **Removed tap highlights** for cleaner look

### Responsive Breakpoints
**Tablet (≤768px):**
- 2-column word grid
- Stacked score cards
- Smaller, optimized fonts
- 2-column clue tracker
- Compact padding

**Phone (≤480px):**
- 1-column layouts throughout
- Full-width buttons
- Single-column word grid
- Single-column clue tracker
- Extra compact design

### Touch Improvements
- Proper `-webkit-tap-highlight-color` removal
- `touch-action: manipulation` for no double-tap zoom
- `-webkit-appearance: none` for consistent inputs
- Smooth font rendering with antialiasing
- Better spacing between interactive elements

---

## v2.3.1 - Win Message & Validation Fixes
**Released:** December 28, 2024

### Bug Fixes
- ✅ **Fixed:** Win messages now clearly state winner (e.g., "Team A wins" not "Team A - Team B lost")
- ✅ **Fixed:** Cannot submit duplicate numbers in guess (e.g., 3-3-1 now blocked)
- ✅ **Fixed:** Cannot submit duplicate numbers in interception
- ✅ Validation message explains the rule clearly

### Improved Win Messages
- "Team A (Blue) wins - Team B had 2 miscommunications!"
- "Team B (Orange) wins - 2 successful interceptions!"
- Clear, celebratory tone
- Winner mentioned first

---

## v2.3.0 - Opponent Clue Tracker
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

- **MAJOR**: Breaking changes or complete redesigns (v1.0.0 → v2.0.0 → v3.0.0)
- **MINOR**: New features, gameplay improvements (v2.0.0 → v2.1.0)
- **PATCH**: Bug fixes, small tweaks (v2.1.0 → v2.1.1)

---

## Planned Features (Future Versions)

### v3.1.0 (Planned)
- [ ] Show who claimed clue-giver role each round in history
- [ ] "Pass clue-giver" button to unclaim if someone else wants to
- [ ] Notification when teammate claims role
- [ ] Timer option for clue/guess phases

### v3.2.0 (Planned)
- [ ] Custom word banks (upload your own words)
- [ ] Difficulty levels (easy/medium/hard word sets)
- [ ] Export game history as PDF
- [ ] Dark mode toggle

### v4.0.0 (Future)
- [ ] Team chat feature
- [ ] Voice chat integration
- [ ] Tournament mode with brackets
- [ ] Player statistics and leaderboards
- [ ] Achievement system
- [ ] AI opponent mode

---

## Breaking Changes by Version

### v3.0.0
- **BREAKING:** Removed fixed role selection
- Players no longer choose "Clue-Giver" or "Guesser" at join
- Roles are now claimed dynamically each round
- Old game saves may not work properly with new system

### v2.0.0
- **BREAKING:** Changed from sequential to simultaneous gameplay
- Old game format not compatible

---

## Summary of All Bug Fixes

### v3.0.0
- N/A (major feature release)

### v2.4.0
- N/A (optimization release)

### v2.3.1
- Fixed: Win messages confusing (mentioned loser team)
- Fixed: Duplicate numbers allowed in guesses/interceptions

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

**Current Version:** v3.0.0

**Total Versions Released:** 15 (including patches)

**Lines of Code:** ~1,800+

**Word Bank Size:** 120 words

**Players Supported:** 2-8+ (any number per team)

---

## What's Next?

We're constantly improving Decrypto! Have suggestions? Found a bug? Let us know!

**Upcoming priorities:**
1. Show clue-giver identity in game history
2. Timer options for faster gameplay
3. Custom word banks
4. Enhanced mobile experience
5. Social features (chat, voice)

Stay tuned for v3.1.0! 🚀

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
