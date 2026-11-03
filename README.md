# Wedding run sheet

- `index.html` - the whole app (markup, styles, scripts). A small module shim at the top maps Firebase (Firestore + Google sign-in) onto the `window.claude.use('db' | 'user')` shape the app uses.
- `firebase-config.js` - public Firebase web config.
- `firestore.rules` - security rules: anyone reads `plan/main` and `seating/main`; only listed editors write.

## Updating
Edit files, commit, push; GitHub Pages redeploys. Deploy rules with `firebase deploy --only firestore:rules` or paste them in the Firebase console (Firestore > Rules).

## Editors list lives in two places
1. `index.html` - the `EDITORS` array (cosmetic: shows or hides the Edit button).
2. `firestore.rules` - the email list in `isEditor()` (the real enforcement).

Keep them identical. In Firebase console, enable Google sign-in and add your GitHub Pages domain under Authentication > Settings > Authorized domains.
