# ✨ the dashboard that will find Gabi a job ✨

A job hunt dashboard that reads the Cold outreach and Applications tabs of a Google Sheet and shows follow-ups, charts and totals for each pathway. It runs in the browser and is hosted free on GitHub Pages.

## Files

- `index.html` is the dashboard.
- `config.js` holds your two sheet links. This is the only file you need to edit.
- `.nojekyll` tells GitHub Pages to serve the files as-is.

## 1. Publish your Google Sheet tabs

1. Open your job hunt sheet in Google Sheets.
2. Click **File → Share → Publish to web**.
3. In the first dropdown (it says "Entire document"), choose **Cold outreach**.
4. In the second dropdown (it says "Web page"), choose **Comma-separated values (.csv)**.
5. Click **Publish**, then **OK** to confirm.
6. Copy the link that appears. It ends in `output=csv`.
7. Without closing the window, switch the first dropdown to **Applications**, keep CSV selected, and copy that link too. (If the Publish button shows again, click it.)
8. Under **Published content and settings**, make sure **Automatically republish when changes are made** is checked.

## 2. Add your links

Open `config.js` in any text editor (TextEdit, Notepad or VS Code) and paste each link between the quotes:

```js
window.DASHBOARD_CONFIG = {
  outreachCsv: 'PASTE THE COLD OUTREACH LINK HERE',
  applicationsCsv: 'PASTE THE APPLICATIONS LINK HERE',
  followUpWindowDays: 7
};
```

Save the file. You can open `index.html` in your browser now to check that your data shows up.

## 3. Put it on GitHub Pages

1. Sign in at github.com (or create a free account).
2. Click the **+** in the top right, then **New repository**.
3. Name it, for example `job-hunt-dashboard`. Choose **Public** (free GitHub Pages needs a public repo) and click **Create repository**.
4. On the new repo page, click **uploading an existing file**.
5. Drag in `index.html`, `config.js`, `.nojekyll` and `README.md`, then click **Commit changes**.
   On a Mac, `.nojekyll` is hidden. In Finder, press **Cmd + Shift + .** to show hidden files.
6. Click **Settings** (top of the repo), then **Pages** in the left sidebar.
7. Under **Build and deployment**, set Source to **Deploy from a branch**. Pick **main** and **/(root)**, then click **Save**.
8. Wait a minute or two and refresh the Pages settings. Your link appears at the top:
   `https://YOUR-USERNAME.github.io/job-hunt-dashboard/`

## Updating

- **New data:** just edit the sheet. Google republishes within about five minutes; reload the dashboard to see it.
- **Changing links or settings:** on GitHub, click `config.js`, click the pencil icon, make your change, and click **Commit changes**.
- **New columns:** columns are matched by header name, so adding or reordering columns is fine. Renaming one the dashboard uses will break that chart.

## Troubleshooting

- **"Showing sample data":** `config.js` still has empty links, or it wasn't uploaded.
- **"Couldn't load the … data":** check the tab is still published and the link ends in `output=csv`.
- **Site shows a 404:** Pages can take a few minutes the first time, and `index.html` must be in the top level of the repo, not in a folder.
- **Old data:** wait five minutes, then hard-refresh (Cmd + Shift + R on Mac, Ctrl + Shift + R on Windows).
