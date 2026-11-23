# SourceLens static website

A static HTML/CSS/JavaScript website prepared for GitHub + Netlify deployment.

## Preview locally
Open `index.html` in a browser. For a local server, run `python3 -m http.server 8080` from this directory and visit `http://localhost:8080`.

## Deploy to Netlify
- **Drag & drop:** Netlify Sites → Add new site → Deploy manually → drag this project folder (or its ZIP after extraction) into the deploy area.
- **GitHub:** Push the folder contents to a repository. In Netlify, import the repository. Build command: leave blank. Publish directory: `.`.
- `netlify.toml` is included for static publish configuration.

## Form note
The inquiry form is client-side only. On submit, it prepares a `mailto:` draft in the visitor's email app. It does not send or store data. For a production form, connect Netlify Forms or a backend endpoint and update the form handler.

## Content note
Case files are demonstration research templates, not actual completed supplier/client cases. Do not publish claims of certifications, laboratory accreditation, client projects or verified capabilities unless those are real and documented.
