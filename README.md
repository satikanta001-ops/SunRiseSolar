# Sun Rise Solar — Business Manager

Warehouse, GST billing, accounts, HR and reports in one web app.
Data is stored in Firebase Firestore (project `sun-rise-solar`) and syncs live between phone and PC.

## Files
| File | What it is |
|---|---|
| `index.html` | The whole app |
| `manifest.webmanifest` | Lets phones/PCs install it as an app |
| `sw.js` | Makes the app open offline |
| `icon-*.png` | App icons |
| `firestore.rules` | Security rules to paste into the Firebase console |

## One-time Firebase setup
1. **Authentication → Get started → Sign-in method → Email/Password → Enable.**
2. **Authentication → Users → Add user** — create the shop account (email + strong password).
3. **Authentication → Settings → User actions** — turn off *Enable create (sign-up)* so nobody else can make an account.
4. **Authentication → Settings → Authorized domains → Add domain** — `satikanta001-ops.github.io`.
5. **Firestore Database → Create database** — production mode, location `asia-south1 (Mumbai)`.
6. **Firestore Database → Rules** — paste `firestore.rules`, put your shop email in it, **Publish**.

## Hosting on GitHub Pages
1. Create a repository (for example `Sun-Rise-Solar`) and upload all files in this folder.
2. **Settings → Pages → Deploy from a branch → `main` / root → Save.**
3. Open `https://satikanta001-ops.github.io/Sun-Rise-Solar/` (use your repo name).

## First use
- Each phone/PC signs in **once** with the shop email and password.
- On the first device, choose **Start fresh** (create the Admin) or **Move it to the cloud** if this device used the earlier on-device version, or restore a backup file.
- Staff then log in with their name + PIN.

## Updating the app
Replace `index.html` in the repository. Devices pick up the new version the next time they open the app online.
If you change `sw.js`, raise the version in `const CACHE = 'srs-v1'`.
