# Turnotech HSE 360° North — GitHub Ready

**Owner / Admin:** Ali Hamza — EHS Lead North  
**Email:** Ali.hamza@turnotech.com.pk  
**Live Google Sheet:** [EHS QC Tracker](https://docs.google.com/spreadsheets/d/1qlZzPGtDBDKdWU8IUOStAthH7PvxUOzQyOo-62aYEqE/edit?usp=sharing)  
**Sheet ID:** `1qlZzPGtDBDKdWU8IUOStAthH7PvxUOzQyOo-62aYEqE`

Single-file static app. No backend needed. Works on GitHub Pages.

## Features
- ✅ Dashboard — 1635 Total, 1631 Closed, 268 North, 2 Reviewing, 2 Rejected
- ✅ EHS QC Tracker — Task Explorer (ISDP style) with Search / Filter
- ✅ **Live Google Sheet Auto-Sync** — Sync Now + Auto-Sync every 60s
- ✅ Project Issues — KHI5302 Tower Leakage, 9520 Fire Extinguisher, 55343 Duplicate
- ✅ Rejected Tasks — Sheet1 (7 rejected)
- ✅ **Admin Control** — Ali Hamza = Full Control (Add/Edit/Delete/Approve)
- ✅ **Team Limited Permission** — View + Add only, Delete hidden, Pending Approval
- ✅ User & Permission Control — Admin only tab + Permission Matrix
- ✅ Incidents, Inspections, PTW, Actions, Reports

## How Live Sync Works
1. App fetches CSV from:
   - `https://docs.google.com/spreadsheets/d/{SHEET_ID}/gviz/tq?tqx=out:csv&sheet=Tracker`
   - Fallback: `/export?format=csv&gid=0`
2. Counters update automatically.
3. If fetch fails → shows cached data + warning.

> **Important for GitHub Pages:** In Google Sheet → **Share → Anyone with link can view**  
> Otherwise browser will block live fetch (CORS / permission) and app will show cached data.

To change Sheet: Edit `CONFIG.sheetId` in `index.html` (top of `<script>`) OR use the Sheet URL box in the app → Connect New Sheet.

## Run Locally
```bash
# Option 1: Just open index.html in browser
# Option 2: Python server
python -m http.server 8000
# Then open http://localhost:8000
```

## Deploy to GitHub Pages (2 minutes)

### Option A — GitHub Web (No command line)
1. Go to github.com → New Repository → Name: `hse-360-north`
2. Upload all files from this folder (index.html, README.md, .github/workflows/deploy.yml)
3. Go to Repo → Settings → Pages → Source: **GitHub Actions**
4. Wait 1 min → Your link: `https://<your-username>.github.io/hse-360-north/`

### Option B — Command Line
```bash
git init
git add .
git commit -m "HSE 360 North - Live Google Sheet Auto-Sync"
git branch -M main
git remote add origin https://github.com/<your-username>/hse-360-north.git
git push -u origin main
```
Then: Settings → Pages → Source: GitHub Actions

## File Structure
```
hse-360-north/
├── index.html                  # Full app (single file)
├── README.md                   # This file
├── .gitignore
└── .github/workflows/deploy.yml  # Auto-deploy to GitHub Pages
```

## Admin vs Team
| Feature | Admin (Ali Hamza) | Team |
|---------|-------------------|------|
| View Dashboard / Tracker | ✅ | ✅ |
| Add Incident / Inspection | ✅ | ✅ (Pending Approval) |
| Edit / Delete | ✅ | ❌ Hidden |
| Approve | ✅ | ❌ |
| Reports / User Control | ✅ | ❌ Hidden |

## Change Team Members
Edit the User & Permission Control table in `index.html` — search for `User & Permission Control`.

---
Built for Turnotech North — EHS 360°
