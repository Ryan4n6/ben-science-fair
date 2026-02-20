# How to Update Ben's Science Fair Repo

## Quick Reference

| What | Where |
|------|-------|
| **Repo** | https://github.com/Ryan4n6/ben-science-fair |
| **Live page (judges see this)** | https://ryan4n6.github.io/ben-science-fair/ |
| **QR code for board** | `presentation/qr_code.png` |
| **Local folder** | `/Users/admin/MASS_Trap/BEN_SCIENCE_FAIR/` |
| **This is SEPARATE from the M.A.S.S. Trap code repo** | Code lives in `/Users/admin/MASS_Trap/v2.5.0/` |

## Folder Structure

```
BEN_SCIENCE_FAIR/
├── README.md                              # GitHub landing page
├── HOW_TO_UPDATE.md                       # This file
├── submission/
│   ├── BEN_SCIENCE_FAIR_SUBMISSION.md     # Full written report (5th grade level)
│   └── BEN_VARIABLES_RESUBMIT.md         # Variables resubmission for Assignment #3/4
├── data/
│   └── BEN_SCIENCE_FAIR_DATA.csv         # Raw race data (37 runs)
├── docs/
│   └── index.html                         # Judge-facing data page (what the QR code points to)
├── photos/                                # Add experiment photos here
└── presentation/
    └── qr_code.png                        # Print this for the display board
```

## How to Edit the Judge Data Page

The page judges see when they scan the QR code is `docs/index.html`. It's a single self-contained HTML file — no dependencies, no build tools.

1. Open it in any text editor
2. Edit the HTML (data tables, findings, text, etc.)
3. Save, commit, push — it goes live in ~30 seconds

```bash
cd /Users/admin/MASS_Trap/BEN_SCIENCE_FAIR
# Edit docs/index.html however you want, then:
git add docs/index.html
git commit -m "Update data page"
git push
```

Wait 30 seconds, then refresh https://ryan4n6.github.io/ben-science-fair/

## How to Update the Written Submission

The submission files are in `submission/`. Edit them, commit, push:

```bash
cd /Users/admin/MASS_Trap/BEN_SCIENCE_FAIR
# Edit files in submission/, then:
git add submission/
git commit -m "Update submission"
git push
```

## How to Add Photos

Drop photos into the `photos/` folder, then:

```bash
cd /Users/admin/MASS_Trap/BEN_SCIENCE_FAIR
git add photos/
git commit -m "Add experiment photos"
git push
```

## How to Update Data

If you run more races and need to update the CSV:

1. Pull the latest data from the finish gate:
   ```bash
   curl -s -H "X-API-Key: admin" http://192.168.1.83/api/files?path=/runs.csv -o /tmp/runs.csv
   ```
2. Copy/filter the relevant runs into `data/BEN_SCIENCE_FAIR_DATA.csv`
3. Update the tables in `docs/index.html` to match the new data
4. Update `submission/BEN_SCIENCE_FAIR_SUBMISSION.md` if results changed
5. Commit and push everything

## How to Regenerate the QR Code

The QR code points to https://ryan4n6.github.io/ben-science-fair/

If you ever need to regenerate it (different size, different URL):

```bash
# 400x400 PNG (good for printing)
curl -o presentation/qr_code.png "https://api.qrserver.com/v1/create-qr-code/?size=400x400&data=https://ryan4n6.github.io/ben-science-fair/&format=png"

# 800x800 PNG (higher res for large poster board)
curl -o presentation/qr_code_large.png "https://api.qrserver.com/v1/create-qr-code/?size=800x800&data=https://ryan4n6.github.io/ben-science-fair/&format=png"
```

## How to Print the QR Code

1. Open `presentation/qr_code.png`
2. Print at about 2-3 inches square — judges need to scan it with a phone
3. Stick it on the display board near the data section
4. Add a label: "Scan for live data" or "View raw data"

## Why It's Set Up This Way

- **Ben's personal data is separate from the code project.** The M.A.S.S. Trap repo (github.com/Ryan4n6/MASS-Trap) has the firmware and dashboard code. This repo has Ben's science fair writeups and data. They link to each other but don't overlap.
- **The QR code points to GitHub Pages**, which auto-deploys when you push. No servers to manage.
- **The `.gitignore` in the M.A.S.S. Trap repo blocks `BEN_*` files** so Ben's stuff can never accidentally end up in the code repo.
- **The judge page is a single HTML file** with zero external dependencies. No JavaScript frameworks, no CDN links, no cookies. It will load on any phone instantly.

## Important: Don't Put This Stuff in the M.A.S.S. Trap Repo

The M.A.S.S. Trap code repo (`/Users/admin/MASS_Trap/v2.5.0/`) has a `.gitignore` that blocks all `BEN_*` files. This is intentional — Ben's personal science fair submissions don't belong in the public firmware codebase.

If you need to reference the M.A.S.S. Trap from Ben's submission, link to it:
- GitHub: https://github.com/Ryan4n6/MASS-Trap
- Project site: https://ryan4n6.github.io/MASS-Trap/

## Timeline Reminder

| Assignment | What | Due | Points |
|-----------|------|-----|--------|
| #3/4 | Variables/Materials/Procedure | Resubmit (graded 0/20) | 20 |
| #5/6/7 | Data/Results/Conclusion/Title/Abstract | Feb 20, 2026 | 30 |
| #8 | Display Board + Presentation | Mar 9, 2026 | 100 |
