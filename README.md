# CornHub

Modern private search + proxy front-end.  
Dark, clean, mobile-ready. Pure static — works on jsDelivr, GitHub Pages, Cloudflare Pages, Netlify, or any static host.

- DuckDuckGo / Brave Search / Startpage (no Google tracking)
- Custom proxy gateway field (`{url}` template)
- Quick apps grid
- Settings saved in localStorage
- Zero dependencies

## Quick test

Open `index.html` in any browser.

## Host on jsDelivr (recommended)

jsDelivr does **not** have an upload form. It serves files from:

1. **GitHub** (easiest)
2. **npm** (if you publish the package)

### Option A — GitHub → jsDelivr (fastest)

1. Create a **public** GitHub repository named `cornhub` (or any name).
2. Upload these two files to the **root**:
   - `index.html`
   - `package.json` (optional but good)
3. Commit & push to the `main` branch.
4. Your live CDN URL is:

```
https://cdn.jsdelivr.net/gh/YOUR_USERNAME/cornhub@main/index.html
```

Or pin a commit for stability:

```
https://cdn.jsdelivr.net/gh/YOUR_USERNAME/cornhub@COMMIT_SHA/index.html
```

Bookmark that URL. Open it at school.

### Option B — npm → jsDelivr

1. Create a free npm account at https://www.npmjs.com
2. In the `cornhub` folder run:

```bash
npm login
npm publish --access public
```

3. After publish, the URL becomes:

```
https://cdn.jsdelivr.net/npm/cornhub@1.0.0/index.html
```

(Update the version in `package.json` when you change files.)

### Option C — GitHub Pages

Repo → Settings → Pages → Source: Deploy from branch → `main` / root.  
You get `https://YOUR_USERNAME.github.io/cornhub/`.

## Making the proxy actually unblock sites

The UI is only the front door. For full site proxying you still need a backend (Ultraviolet, Scramjet, Wisp, etc.).

1. Open **Settings** (gear icon).
2. Paste your gateway template in **Custom proxy gateway**.
   - Example: `https://your-proxy.example/?url={url}`
   - Or path style: `https://your-proxy.example/service/{url}`
3. Save. Now every link and search can go through that gateway.

If the field is empty, links open directly (or through the chosen search engine).

## Files

```
cornhub/
  index.html      ← the entire app
  package.json    ← npm metadata (for jsDelivr / npm)
  README.md       ← this file
```

No build step. No node_modules required for the site itself.

## License

MIT — use it, fork it, re-skin it.
