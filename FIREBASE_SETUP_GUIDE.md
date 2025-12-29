# Firebase Setup Guide for Decrypto

This guide will walk you through setting up Firebase for your Decrypto game so it works with real-time multiplayer across different devices.

## Step 1: Create a Firebase Account

1. Go to [https://console.firebase.google.com](https://console.firebase.google.com)
2. Sign in with your Google account
3. Click "Add project" or "Create a project"

## Step 2: Create Your Firebase Project

1. **Enter a project name**: e.g., "Decrypto-Game"
2. **Google Analytics**: You can disable this (not needed for this game)
3. Click "Create project"
4. Wait for the project to be created (takes about 30 seconds)
5. Click "Continue"

## Step 3: Set Up Realtime Database

1. In your Firebase console, look at the left sidebar
2. Click on "Build" to expand it
3. Click on "Realtime Database"
4. Click "Create Database"
5. **Choose location**: Select the region closest to you (e.g., "United States")
6. **Security rules**: Select "Start in test mode" (we'll configure this properly later)
7. Click "Enable"

You should now see an empty database with a URL like:
`https://your-project-id-default-rtdb.firebaseio.com/`

## Step 4: Configure Database Security Rules

**IMPORTANT:** The default test mode rules allow anyone to read/write for 30 days. For this game, we'll set it up to allow anyone to access (since we're using game codes for security).

1. In the Realtime Database page, click on the "Rules" tab
2. Replace the existing rules with:

```json
{
  "rules": {
    "games": {
      "$gameCode": {
        ".read": true,
        ".write": true
      }
    }
  }
}
```

3. Click "Publish"

**Note:** This allows anyone to read/write to games. For a production app, you'd want to add authentication, but for a casual game with friends, this is fine.

## Step 5: Get Your Firebase Configuration

1. Click on the gear icon (⚙️) next to "Project Overview" in the left sidebar
2. Click "Project settings"
3. Scroll down to "Your apps" section
4. Click on the web icon (`</>`) that says "Web"
5. **Register app**: Give it a nickname like "Decrypto Web App"
6. Click "Register app"
7. You'll see a code snippet that looks like this:

```javascript
const firebaseConfig = {
  apiKey: "AIzaSyDXXXXXXXXXXXXXXXXXXXXXXXXXX",
  authDomain: "your-project.firebaseapp.com",
  databaseURL: "https://your-project-default-rtdb.firebaseio.com",
  projectId: "your-project",
  storageBucket: "your-project.appspot.com",
  messagingSenderId: "123456789012",
  appId: "1:123456789012:web:abcdef1234567890"
};
```

8. **Copy this entire configuration object**

## Step 6: Add Configuration to Your HTML File

1. Open the `decrypto-firebase.html` file in a text editor
2. Find the section that says:

```javascript
// ============================================
// FIREBASE CONFIG HERE - REPLACE WITH YOUR OWN
// ============================================
const firebaseConfig = {
  apiKey: "YOUR_API_KEY_HERE",
  authDomain: "YOUR_PROJECT_ID.firebaseapp.com",
  ...
```

3. **Replace the entire `firebaseConfig` object** with the one you copied from Firebase
4. Save the file

## Step 7: Test Your Setup

1. Upload the `decrypto-firebase.html` file to Google Sites
2. Open the page
3. You should see a **green "Connected"** indicator next to the title
4. The red warning box at the top should disappear
5. Try creating a game - it should work!

## Step 8: Share and Play

1. Create a game and get the game code
2. Share the URL and game code with your friends
3. Everyone can join from different devices/browsers
4. Updates happen automatically in real-time!

## Troubleshooting

### "Not Connected" Error
- Make sure you've replaced ALL the placeholder values in firebaseConfig
- Check that your databaseURL is correct
- Make sure Realtime Database is enabled in your Firebase console

### "Permission Denied" Error
- Check your database rules (Step 4)
- Make sure the rules are published

### Game Not Syncing
- Check your browser console (F12) for errors
- Make sure all players are using the same game code
- Verify your Firebase database URL is correct

### Database Rules Warning
If you see a warning that your database rules are insecure:
- This is expected for a casual game
- The game uses random codes for security
- For a public/commercial app, you'd add Firebase Authentication

## Firebase Free Tier Limits

Firebase's free "Spark" plan includes:
- **Realtime Database**: 1GB storage, 10GB/month downloads
- This is more than enough for hundreds of games

Your Decrypto games use minimal data:
- Each game: ~5KB
- You can run thousands of games on the free tier

## Optional: Custom Domain

If you want to use your own domain:
1. In Firebase Console, go to "Hosting"
2. Click "Get started"
3. Follow the instructions to deploy and connect a custom domain

## Security Best Practices (Optional)

For a more secure setup:
1. Enable Firebase Authentication
2. Update database rules to require authentication
3. Add user management to track who's playing

But for a casual game with friends, the current setup is fine!

---

## Quick Reference

**Firebase Console:** https://console.firebase.google.com
**Your Project:** [Your project name]
**Database URL:** [Your database URL]

Once set up, you never need to touch Firebase again - it just works!
