# Decrypto Word List Management

## Overview
The game uses an external `words.txt` file to load the word bank. This makes it easy to add, remove, or modify words without editing the game code.

## File Location
- **File:** `words.txt`
- **Same directory as:** `index-simultaneous.html`

## Format
- One word per line
- Words should be in UPPERCASE (will be auto-converted if not)
- Empty lines are ignored
- Duplicates are automatically removed

## Example (words.txt):
```
PIANO
THUNDER
DIAMOND
CASTLE
ROBOT
```

## How to Add More Words

### Method 1: Edit words.txt directly
1. Open `words.txt` in a text editor
2. Add new words, one per line
3. Save the file
4. Refresh the game page

### Method 2: Replace entire file
1. Create a new text file with your word list
2. Save it as `words.txt`
3. Replace the old file
4. Refresh the game page

## Word Guidelines

### Good Words:
- ✅ Concrete nouns (PIANO, CASTLE, OCEAN)
- ✅ Common concepts (LOVE, FEAR, TIME)
- ✅ Easy to visualize
- ✅ Not too similar to other words

### Avoid:
- ❌ Very obscure words
- ❌ Words too similar to existing ones (ROCK/STONE)
- ❌ Proper nouns (PARIS, JOHN)
- ❌ Offensive or controversial terms

## Current Word Count
The default file contains **120 unique words**.

## Verification
When the game loads, check the browser console (F12):
```
Loaded 120 unique words from words.txt
```

If you see this message, your words loaded successfully!

## Fallback
If `words.txt` fails to load (file not found, network error, etc.), the game will automatically fall back to an embedded list of 120 words.

## Tips for Game Balance
- **Minimum recommended:** 100 words (for variety)
- **Sweet spot:** 150-200 words (fresh words each game)
- **Too many?** 500+ words may slow down loading

## Testing Your Word List
1. Add/modify words in `words.txt`
2. Refresh the game page
3. Check console for: `Loaded X unique words from words.txt`
4. Create a new game
5. Verify words display correctly

## Troubleshooting

### Words not loading?
- Check file is named exactly `words.txt`
- Check file is in same directory as HTML file
- Check browser console for errors (F12)
- Verify file encoding is UTF-8

### Duplicates showing?
The game automatically removes duplicates, but if you see duplicates in-game, clear your browser cache and refresh.

### Special characters?
Stick to A-Z letters for best compatibility. Avoid numbers, symbols, or accented characters.

## Contributing Words
Great words to add:
- Animals: WOLF, FOX, WHALE, TIGER
- Nature: VOLCANO, CAVE, STORM, SUNSET
- Objects: THRONE, LANTERN, SCROLL, ARMOR
- Abstract: WISDOM, COURAGE, MYSTERY, DESTINY
- Technology: COMPUTER, INTERNET, SATELLITE, LASER

Have fun expanding your word bank! 🎮✨
