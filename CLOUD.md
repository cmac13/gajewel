# Cloud runbook

## Purpose
Static HTML pages render interactive elevation profiles by fetching SVG assets.

## Structure
- `index.html`: 100-mile elevation profile.
- `50-mile.html`: 50-mile elevation profile.
- `gajewel-elevation-profile.svg`: 100-mile SVG asset.
- `gajewel-50-elevation-profile.svg`: 50-mile SVG asset.

## Local preview
1. Start a simple static server in the repo root.
2. Open `http://localhost:8000/index.html`.
3. Open `http://localhost:8000/50-mile.html`.

Example server command:
- `python3 -m http.server 8000`

## Wix embed checklist
1. Ensure SVG URLs are publicly accessible (no auth, no 403).
2. Update the HTML embed to use absolute SVG URLs in:
   - `fetch("https://.../gajewel-elevation-profile.svg")`
   - `href="https://.../gajewel-elevation-profile.svg"`
3. Repeat for the 50-mile SVG.
4. Verify tooltips render when hovering over station markers.

## Troubleshooting
- If the chart shows "Failed to load profile", the SVG URL is blocked or incorrect.
- If tooltips do not appear, the SVG did not load or markers are missing.
