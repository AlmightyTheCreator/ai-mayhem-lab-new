# AI Mayhem Lab — Mobile/PWA Prototype

This is an upgraded mobile-ready version of **AI Mayhem Lab**.

## What is included

- Responsive mobile-first interface
- PWA manifest and service worker for installable web app behavior
- Offline caching after first load
- iOS home-screen icon support
- Android install prompt support where supported by browser
- Capacitor config for native iOS/Android wrappers
- Smoother character animations
- Browser text-to-speech voice reactions
- Rule-based AI chat prototype
- Encounter memory system with Remember / Start New options
- AI dialogue that references past tools, rooms, modes, names, and chat topics
- Memory controls to turn memory on/off or clear saved memories
- Unlock shop, XP, credits, rooms, modes, and tool progression

## Open locally

1. Unzip this folder.
2. Open `www/index.html` in a browser.

For best PWA testing, serve it instead of opening the file directly:

```bash
npm install
npm run serve
```

Then open:

```text
http://localhost:8080
```

## Make it installable as a PWA

Upload the `www` folder to a web host such as Netlify, Vercel, GitHub Pages, or your own server. Open the hosted HTTPS link on your phone.

- Android Chrome should show an install option.
- iPhone Safari can install it from Share → Add to Home Screen.

## Build native iOS and Android wrappers

Install Node.js first, then run:

```bash
npm install
npx cap add ios
npx cap add android
npx cap sync
```

Open the native projects:

```bash
npx cap open ios
npx cap open android
```

Requirements:

- iOS builds require a Mac with Xcode.
- Android builds require Android Studio.
- App Store / Play Store publishing requires developer accounts.

## Real AI chat upgrade path

The current chat is intentionally offline and rule-based. For real AI chat, add a secure backend endpoint and call it from `game.js`. Do **not** put private API keys directly inside the mobile app or browser JavaScript.

Suggested architecture:

```text
Mobile App / PWA → Your Backend → AI Model API
```

## Safety note

This build uses harmless prank, comedy, and chaos mechanics. It avoids graphic harm or torture mechanics.


## Encounter memory feature

On launch, players can choose **Remember Previous Encounters** or **Start New Encounter**.

When memory is on, the app stores lightweight encounter details on the device using `localStorage`, including:

- Names the player provides
- Favorite tools, rooms, and response modes
- Recent chat topics
- Memorable tool/room/mode moments
- Last encounter timestamps

The AI uses those details to add more personalized dialogue. Players can turn memory off or clear it from the Memory panel.
