# Build the Android APK
**Easiest:** push this folder to a GitHub repo. The workflow in `.github/workflows/build-apk.yml`
builds the APK and publishes it at
`https://github.com/<user>/<repo>/releases/download/latest/efootball-cards.apk`.

**Locally** (needs Node 22, JDK 21, Android SDK):
`npm install && npx vite build && npx cap add android && npx cap sync android && cd android && ./gradlew assembleDebug`
→ `android/app/build/outputs/apk/debug/app-debug.apk`

Multiplayer needs the Express server (`server.ts`) hosted somewhere; build with
`VITE_API_BASE=https://your-server` so the app can reach it. All other modes work offline.
