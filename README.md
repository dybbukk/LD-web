# Live & Direct — Netlify deployment

This repo contains a single-page static site (index.html). The project is prepared for Netlify Forms and ready to deploy.

What I changed to support Netlify
- The contact form includes:
  - name="contact"
  - data-netlify="true"
  - data-netlify-honeypot="hp"
  - <input type="hidden" name="form-name" value="contact" />
- Form client-side validation left in place; when deployed to Netlify the form will submit natively and Netlify will capture submissions.
- Added `netlify.toml` with publish directory and a redirect rule and basic security headers.

Quick deploy steps
1. Push to GitHub (repo root must contain index.html)
2. In Netlify: "New site from Git" → connect GitHub → select this repo
   - Build command: (leave blank)
   - Publish directory: .
3. Deploy.
4. After first deploy, go to Site → Forms in Netlify to view submissions.

Local testing with Netlify CLI
- Install: `npm i -g netlify-cli`
- Run: `netlify dev`
- Open http://localhost:8888 — dev server will emulate Netlify Forms.

Notes
- Netlify Forms captures submissions only when the site is served by Netlify (or via `netlify dev`).
- Configure form notifications (email/webhook) from the Netlify admin UI if you want alerts on new submissions.
