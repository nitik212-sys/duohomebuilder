# Duo Home Builder

A two-player isometric house builder: colour blocks, three floors, pitched roofs, decor, mood colours, mood timeline, day/night, undo, rotate view and save-as-image. Rooms are permanent: the same duo can return with the same 4-letter code.

## Set up (about 10 minutes, free)
1. Go to https://console.firebase.google.com, create a project, then add a **Web app** (`</>`). Copy its config.
2. Paste the config into `firebaseConfig` near the top of the script in `index.html`.
3. **Build > Authentication > Sign-in method**: enable **Anonymous**.
4. **Build > Firestore Database**: create a database (production mode), then open the **Rules** tab and paste in `firestore.rules`.
5. **Authentication > Settings > Authorized domains**: add `nitik212-sys.github.io`.
6. Push these files to the repo, then **Settings > Pages**: deploy from the `main` branch, root folder.
7. Open https://nitik212-sys.github.io/duohomebuilder/ and create a room.

## Notes
- Players are identified by Firebase anonymous sign-in, which is tied to one browser. Clearing site data or switching device means losing your seat in a room. Add Google sign-in later to make accounts follow you.
- The first two people to join a room claim it, and Firestore rules block everyone else.
- Free plan limits: about 20,000 writes per day. Cursor sharing uses the most writes.
