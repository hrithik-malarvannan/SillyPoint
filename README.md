# Silly Point

Single-file React cricket simulation game. No build step — React, ReactDOM
are pulled from a CDN and the app code is plain compiled JS embedded
directly in `index.html`.

## Run locally

Just open `index.html` in a browser. No server, no npm install needed.

If you want a local dev server anyway (some browsers restrict certain
features on `file://`):

```
npx serve .
```

## Deploy

### Vercel
1. Push this repo to GitHub.
2. Go to vercel.com → New Project → import the repo.
3. Framework preset: "Other" (or leave auto-detected — it's static).
4. Deploy. No build command, no environment variables needed.

### Netlify
1. Push this repo to GitHub.
2. Go to app.netlify.com → Add new site → Import an existing project.
3. Build command: leave blank. Publish directory: `.` (repo root).
4. Deploy.

### GitHub Pages
1. Push this repo to GitHub.
2. Repo Settings → Pages → Source: `main` branch, `/ (root)`.
3. Save — GitHub gives you a URL in a minute or two.

## Updating the game

The source of truth during development is the `.jsx` artifact worked on in
Claude. This `index.html` is a compiled export of that artifact (JSX →
plain JS, React pulled from CDN instead of `import`). After making changes
in the artifact, regenerate `index.html` and push again — there's currently
no automated sync between the two.

## Notes

- No backend, no database — all player/team data is embedded in the JS.
- No `.env` or secrets involved, so this deploys with zero configuration
  on any static host.
