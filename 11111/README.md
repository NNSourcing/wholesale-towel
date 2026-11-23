# SourceLens website
Static site (HTML/CSS/JS, no build step). Hash-routed, so no redirect rules are needed.

## Before launch
- Set `CONTACT_EMAIL` at the top of `js/app.js`. The form has no backend: it opens a **mailto draft**; nothing is stored or transmitted by the site.
- External dependency: Google Fonts (Space Grotesk, Inter, IBM Plex Mono). Fallbacks are defined. All imagery is local inline SVG.
- Case files and the sample report are labelled demonstrations. Replace them only with real, approved work.
- About page: add an independence policy only once it is truly adopted.

## GitHub
`git init && git add . && git commit -m "SourceLens" && git branch -M main && git remote add origin <repo-url> && git push -u origin main`

## Netlify
Add new site > Import from Git > choose the repo. Build command: empty. Publish directory: `.` (or drag the folder into Netlify Drop).

## Optional form backend
Add `data-netlify="true"` and `name="check"` to the form and replace the mailto logic in `js/app.js` with a fetch POST.
