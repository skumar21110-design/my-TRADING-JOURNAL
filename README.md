# Trading Journal - deploy online (free)

Result: a website with login (email/password or Google). Your trades and screenshots sync to the cloud and open on any PC or phone.

## Step 1 - Create the Firebase project (5 min)
1. Go to https://console.firebase.google.com and sign in with Google.
2. Add project -> any name (e.g. my-trading-journal). Analytics not needed.
3. Build -> Authentication -> Get started -> enable "Email/Password" and "Google".
4. Build -> Firestore Database -> Create database -> production mode -> pick a region near you.
5. Firestore -> Rules tab -> paste the contents of firestore.rules -> Publish.
6. Project settings (gear) -> Your apps -> Web (</>) -> register app -> copy the firebaseConfig values.

## Step 2 - Paste the config
Open index.html in a text editor. Near the top, replace the 4 PASTE_... values in `firebaseConfig` with yours.

## Step 3 - Put it online (pick one)
- Netlify (easiest): go to https://app.netlify.com/drop and drag the deploy folder in. You get a link like https://something.netlify.app
- Or Firebase Hosting / GitHub Pages / Vercel (any static host works).

## Step 4 - Allow your site for login
Firebase -> Authentication -> Settings -> Authorized domains -> Add your Netlify domain (e.g. something.netlify.app).

Open your link, create an account, and use it from any PC. Each account sees only its own trades.

Notes: screenshots are shrunk and stored in your Firestore (about 1 MB limit per trade, so a few images each). Keep using Backup file now and then.
