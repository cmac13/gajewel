# Georgia Jewel Elevation Profiles

Interactive elevation profile charts for [The Georgia Jewel](https://www.georgiajewel.com/) ultramarathon race. These charts display aid station locations, cutoff times, crew access points, and other race information via hover tooltips.

## Live Demo

- **100-mile profile:** https://gajewel.vercel.app/index.html
- **50-mile profile:** https://gajewel.vercel.app/50-mile.html

## Embedding in Wix

### Option 1: Embed as iframe (Recommended)

Use Wix's "Embed a Site" element to iframe the hosted pages:

1. In the Wix Editor, add an **Embed a Site** element
2. Set the URL to:
   - `https://gajewel.vercel.app/index.html` (100-mile)
   - `https://gajewel.vercel.app/50-mile.html` (50-mile)
3. Adjust the iframe dimensions as needed (recommended: 100% width, 500-600px height)

### Option 2: Embed HTML directly

If you need to paste the HTML into a Wix HTML embed block:

1. Copy the contents of `index.html` or `50-mile.html`
2. Paste into a Wix **Embed HTML** element
3. The HTML already references the SVG files via absolute URLs (`https://gajewel.vercel.app/...`), so no changes are needed

## File Structure

| File | Description |
|------|-------------|
| `index.html` | 100-mile elevation profile page |
| `50-mile.html` | 50-mile elevation profile page |
| `gajewel-elevation-profile.svg` | 100-mile SVG chart |
| `gajewel-50-elevation-profile.svg` | 50-mile SVG chart |
| `stations.json` | 100-mile aid station data |
| `stations-50.json` | 50-mile aid station data |

## Features

- **Interactive tooltips** — Hover over any station marker to see:
  - Mile marker and elevation
  - Distance to next aid station
  - Distance to finish
  - Cutoff time
  - Crew access / drop bag / pacer indicators
- **Google Maps links** — Crew access badges link directly to Google Maps directions
- **Responsive design** — Scales to fit container width
- **Download button** — Users can download the raw SVG

## Local Development

Start a local server in the repo root:

```bash
python3 -m http.server 8000
```

Then open:
- http://localhost:8000/index.html
- http://localhost:8000/50-mile.html

## Troubleshooting

| Problem | Solution |
|---------|----------|
| "Failed to load profile" error | SVG URL is blocked or incorrect. Verify the Vercel deployment is live. |
| Tooltips don't appear | SVG didn't load properly, or station markers are missing from the SVG. |
| 403 Forbidden in Wix | Make sure you're using the absolute Vercel URLs, not relative paths. |

## Deployment

This repo is connected to Vercel. Pushing to `main` automatically deploys to https://gajewel.vercel.app.
