```markdown
# Port Virtual World — PVL.ONE

Interactive digital-twin platform for port communities. Each port is mapped with
the same method — transport modes, terminals, operator archetypes and carbon
footprint — so any two port communities can be compared, combined, and
simulated as green corridors.

🔗 Live site: https://portvirtualworld.github.io/portvirtualworld/ 
*(update this link once GitHub Pages is enabled)*

---

## 📁 Structure

```
portvirtualworld/
├── index.html              # Landing page — select a port community
├── barcelona/
│   ├── index.html          # Barcelona port digital twin
│   └── images/
│       └── banner-barcelona.jpg
├── civitavecchia/
│   └── index.html
├── palermo/
│   └── index.html
└── rotterdam/
    └── index.html
```

Each `<port>/index.html` is self-contained: transport modes, terminal cards,
operator archetypes, community lead profile, and an interactive Leaflet map.

---

## ➕ Adding a new port

1. Duplicate an existing folder (e.g. `barcelona/`) and rename it to the new
   port's slug, e.g. `valencia/`.
2. Inside its `index.html`, edit the `CONFIG`, `LEAD`, `ARCHETYPES`, `MODES`,
   `NODES`, `NAUTIC_SERVICES` and `TERMINALS` objects near the bottom of the
   file with that port's real data.
3. If the port has its own banner image, drop it in `valencia/images/` and
   point `#hero .hero-photo { background-image: url("./images/...") }` to it.
4. Add a card for it in the root `index.html`'s `PORTS` array:
   ```js
   {
     slug: "valencia",
     name: "Valencia",
     region: "Western Mediterranean · Spain",
     flag: "ES",
     color: "#1E6BB8",
     scene: "scene-...",   // or reuse an existing icon
     live: true,           // false = shows "Coming soon"
     stats: [ {v:"..",k:"Members"}, {v:"..",k:"Terminals"}, {v:"..",k:"TEU/yr"} ]
   }
   ```

---

## 🛠 Tech stack

- Plain HTML / CSS / vanilla JavaScript — no build step, no framework
- [Leaflet.js](https://leafletjs.com/) + CARTO Voyager tiles for the port maps
- Google Fonts: Mulish (body) & JetBrains Mono (mono/labels)
- All data lives inline in each page's `<script>` block — no backend, no database

---

## 🌐 Deploying

This is a static site — works out of the box with **GitHub Pages**:

1. Go to **Settings → Pages**
2. Source: `Deploy from a branch`
3. Branch: `main`, folder: `/ (root)`
4. Save — your site will be live at `https://<org>.github.io/<repo>/`

---

## 📄 License / Credits

Part of the **PLIKA Network** · [pvl.one](https://pvl.one) · [plika.org](https://plika.org)
```
