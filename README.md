# Influencer Performance Dashboard

A responsive, static marketing analytics dashboard for reviewing influencer campaign performance across Instagram, TikTok, and YouTube. It is built with semantic HTML and Tailwind CSS v4, with charts styled by Chart.css.

> This is a front-end demonstration with hard-coded sample figures. It does not connect to social networks, a database, or a live analytics API.

## Dashboard contents

- Summary KPIs: revenue, conversion rate, engagement rate, margin, and accumulated commission.
- Commission trend chart, ROAS comparison by platform, and conversion funnel.
- Product performance cards and operational tables for products and platforms.
- Alerts, opportunities, and ranked lists.
- Spanish-language interface, responsive layout, and navigation links to dashboard sections.

## Technology

- **HTML5:** page structure and sample content in `index.html`.
- **Tailwind CSS v4:** compiled locally with `@tailwindcss/cli`; `src/input.css` is the entry point and `src/output.css` is generated.
- **Chart.css:** styles HTML-table-based charts; loaded from jsDelivr.
- **Google Fonts:** Manrope and Space Grotesk, loaded remotely.
- **Python 3 + Flask:** simple development server in `server.py` (port 3000).
- **Node.js/npm:** installs and runs the Tailwind CLI.

There is no JavaScript application framework or application data/API layer. Dashboard values and filters are illustrative static markup.

## Requirements

- Node.js and npm
- Python 3
- Flask (`pip install flask`)
- Network access for Google Fonts and Chart.css CDN resources

## Run locally

From the repository root:

```bash
npm install
npm run build
pip3 install flask
npm run serve
```

Open **http://localhost:3000**. The server binds to `0.0.0.0:3000`, so the port may also be reachable from a development container or another device, depending on your environment.

### Development workflow

Run the Tailwind watcher in one terminal:

```bash
npm run dev
```

Run the server in another terminal:

```bash
npm run serve
```

The watcher rebuilds `src/output.css` when source files change. Stop it with `Ctrl+C`. To generate a minified stylesheet, run `npm run build`.

## npm scripts

| Command | Purpose |
| --- | --- |
| `npm run dev` | Compile Tailwind from `src/input.css` to `src/output.css` and watch for changes. |
| `npm run build` | Generate minified `src/output.css`. |
| `npm run serve` | Start the Flask development server on port 3000. |

## Project structure

```text
.
├── index.html       # Dashboard markup and sample data
├── server.py        # Flask static-file development server
├── package.json     # npm scripts and Tailwind dependencies
└── src/
    ├── input.css    # Tailwind v4 entry point
    └── output.css   # Generated stylesheet linked by index.html
```

## Customization

- Edit the dashboard markup and sample figures in `index.html`.
- Change Tailwind utility classes in the HTML, then rebuild (or keep `npm run dev` running).
- Add CSS imports or custom CSS to `src/input.css`.
- The Chart.css table charts (`charts-css line` and `charts-css bar`) and their values are defined in the HTML.
- For offline/self-hosted use, serve Chart.css and the fonts locally and update their `<link>` elements.

## Notes

- `server.py` is for local development, not production; Flask debug mode is enabled.
- The dashboard is static. Filtering, authentication, persistence, and live data refresh are not implemented.
- `src/output.css` is generated; rebuild after changing Tailwind classes.
