# NetherPanel Docs

The standalone documentation website for [NetherPanel](https://github.com/Rishiahuja11/netherpanel) — a Minecraft server panel for Termux. Fully static (HTML/CSS/JS), no build step, deployable to Render (or any static host).

Live demo of the panel: set the `PANEL_URL` constant in `js/docs.js` to your panel's public address (default `http://localhost:3000`).

## One-click deploy on Render

1. **Push to GitHub**
   ```bash
   cd netherpanel-docs
   git init
   git add -A
   git commit -m "NetherPanel docs site"
   git branch -M main
   git remote add origin https://github.com/<your-username>/netherpanel-docs.git
   git push -u origin main
   ```

2. **Create the static site**
   - Go to [dashboard.render.com](https://dashboard.render.com)
   - **New +** → **Static Site**
   - Connect your `netherpanel-docs` GitHub repo
   - Name: `netherpanel-docs`
   - Root directory: `.`
   - Build command: *(leave empty)*
   - Publish directory: `*` *(leave empty — it defaults to root)*
   - Click **Create Static Site**

3. Done — the site is live at `https://netherpanel-docs.onrender.com`, auto-deploys on every push to `main`.

## Alternative: deploy the folder directly

No separate repo required — the docs also live in the panel repo at `public/docs/`. On Render, create a Static Site from the **netherpanel** repo and set:

- Root directory: `public/docs`
- Build command: *(empty)*
- Publish directory: *(empty — serve the root directory)*

## Customization

| File | What to change |
|------|----------------|
| `js/docs.js` | `YT_VIDEO_ID` (your YouTube short once uploaded), `YT_CHANNEL_URL`, `CHANNEL_SUBS`, `PANEL_URL` |
| `index.html` | Hero copy, feature list, quick links |
| `css/docs.css` | Theme colors (variables at the top), layout |

## Local preview

```bash
python3 -m http.server 8000   # then open http://localhost:8000
```