# Calories App

A single-file calorie and weight tracker for GitHub Pages.

## Files in this package

- `index.html` — the complete app: HTML, CSS, JavaScript, and embedded food icons.
- `.nojekyll` — tells GitHub Pages not to run this static app through Jekyll.
- `README.md` — these setup, update, backup, and recovery notes.

There is no build step, server, database server, or package installation.

> Your diary data is **not stored in GitHub**. It is stored in the browser's `localStorage` under the key `plate-v1` for the website origin you use. The repository only holds the app code.

## First-time GitHub Pages setup

### 1. Create the repository

1. Sign in to GitHub.
2. Create a new repository named, for example, `calories-app`.
3. For the free GitHub Pages workflow, make it **Public**.
4. Do not initialize it with a README, `.gitignore`, or license for this first upload; this package already contains its README.

### 2. Upload the package contents

1. Unzip `calories-app-github.zip` on your computer.
2. Open the new GitHub repository.
3. Choose **Add file → Upload files**.
4. Upload the **contents** of the unzipped folder:
   - `index.html`
   - `README.md`
   - `.nojekyll`
5. Make sure `index.html` is at the repository root, not inside another folder.
6. Commit the files directly to the `main` branch.

Tip: `.nojekyll` starts with a dot, so it may be hidden by your computer's file picker. It is helpful but not required; `index.html` is the essential file.

### 3. Turn on GitHub Pages

1. In the repository, open **Settings → Pages**.
2. Under **Build and deployment**, choose **Deploy from a branch**.
3. Select branch **`main`** and folder **`/(root)`**.
4. Save if GitHub shows a Save button.
5. Wait for deployment, then use **Visit site** or open:

   `https://YOUR-USERNAME.github.io/calories-app/`

Replace `YOUR-USERNAME` and `calories-app` with your actual GitHub username and repository name.

## How your data is stored

GitHub Pages only publishes the code. Each browser/device stores its own data locally:

- Food diary and goals
- Recipes
- My Food database
- Food icon choices
- Weigh-ins
- Budget-calculator profile

Storage location: browser `localStorage`, key `plate-v1`, scoped to the site's origin (for example, `https://YOUR-USERNAME.github.io`).

That means:

- Replacing `index.html` at the **same site address** does **not** erase the diary.
- Data does **not** automatically sync between phones, browsers, or computers.
- A different GitHub username or custom domain is a different origin and will start empty until you restore a backup.
- Private/incognito browsing may discard the data when the session ends.
- Clearing browser/site data can erase the data.
- Anyone who visits your public app URL gets their own empty local diary; they cannot see the diary stored on your device.

## Always back up before an important update or move

In the working app:

1. Open **Goals**.
2. Under **Backup**, choose **Download backup file**.
3. Keep that file somewhere private, such as your files/iCloud Drive/Google Drive.
4. Optionally also use **Copy backup as text** and save the text privately.

Do **not** upload a backup file to a public GitHub repository. It contains your personal tracking data.

Make regular backups even when you are not updating. Browser storage is local and can be removed by the browser, operating system, or device cleanup.

## Safely update the GitHub copy later

When you receive a newer `index.html`:

1. Open the current working app first.
2. Go to **Goals → Download backup file** and save a backup.
3. Keep a copy of the previous working `index.html` as an extra rollback option.
4. In GitHub, open the repository.
5. Choose **Add file → Upload files**.
6. Upload the new file with the exact name `index.html`, replacing the existing file at the repository root.
7. Commit directly to `main`. Use a clear message such as `Update calories app 2026-11-01`.
8. Wait for GitHub Pages to deploy.
9. Refresh the **same app URL**. If the old version appears briefly, wait and refresh again or close/reopen the tab; do not clear website data.
10. Confirm your diary, recipes, weight history, and My Food are still present.

Your existing browser data should remain because only the static `index.html` changed; the site origin and `plate-v1` storage key did not.

### If an update looks wrong

GitHub keeps previous commits. You can download the previous `index.html` from the repository history and upload it again, or revert the bad commit. Your browser data is separate from the code rollback. If data itself needs recovery, use **Goals → Restore backup** with the backup you downloaded before updating.

## Moving to a new URL, browser, or device

1. In the old app, go to **Goals → Download backup file**.
2. Open the app at the new URL/device/browser.
3. Go to **Goals → Restore backup**.
4. Choose the backup file, or paste copied backup text.
5. Review the restore preview, then confirm.
6. Check the diary, recipes, weights, and My Food before deleting anything from the old location.

## Optional: update with Git on a computer

```bash
git clone https://github.com/YOUR-USERNAME/calories-app.git
cd calories-app
# Replace index.html with the newer version
git add index.html
git commit -m "Update calories app"
git push origin main
```

GitHub Pages will redeploy from `main` automatically.

## Troubleshooting

### GitHub Pages shows a 404

- Confirm `index.html` is at the repository root.
- Confirm Pages is set to **Deploy from a branch → main → /(root)**.
- Wait a few minutes for the first deployment.
- Confirm you are using the repository's project URL, including the repository name.

### The site shows the README instead of the app

`index.html` is probably missing from the selected publishing folder or nested inside another folder. Move it to the repository root.

### An update does not appear

Wait for deployment and refresh. Do not use “clear website data” to force a refresh, because that can delete the local diary. A normal refresh, closing/reopening the tab, or waiting for the Pages CDN is safer.

### The app opens but appears empty

You are probably on a different browser, device, private window, GitHub username, or custom domain. Restore your downloaded backup under **Goals → Restore backup**.
