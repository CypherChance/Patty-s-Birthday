# Gwen Birthday Web App

## Quick start

1. Keep the app file as `gwen-birthday.html`.
2. Open it in browser for local testing.
3. For real sharing + no YouTube Error 153, deploy on GitHub Pages (HTTPS).

## Push to GitHub

Run these commands in this folder:

```bash
git init
git add .
git commit -m "Create Gwen birthday app"
git branch -M main
git remote add origin https://github.com/<your-username>/<repo-name>.git
git push -u origin main
```

## Enable GitHub Pages

In GitHub repo:

1. Go to **Settings > Pages**
2. Source: **Deploy from a branch**
3. Branch: **main** and folder: **/** (root)
4. Save

Then your app is live at:

`https://<your-username>.github.io/<repo-name>/gwen-birthday.html`

## Enable real-time sync between you and her

The file supports Firebase Realtime Database.

1. Create a Firebase project.
2. Enable **Realtime Database**.
3. In Firebase project settings, create a **Web App** and copy config.
4. In `gwen-birthday.html`, fill the `CONFIG.firebase` values.
5. Set a shared `roomId` (already set: `gwen-birthday-room`).
6. Re-deploy to GitHub.

### Suggested temporary DB rules (for testing)

Use safer rules later. This is open access:

```json
{
  "rules": {
    ".read": true,
    ".write": true
  }
}
```

## Why this fixes YouTube Error 153

- Local `file://` pages can fail YouTube embed identity checks.
- Hosting via GitHub Pages gives a proper HTTPS origin.
- The player URL now also includes `origin=...` for better compatibility.
