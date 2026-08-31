# City Vibe Guide

A personal, Eater-style city guide — editorial writing + interactive map in a single static site. No build step, no backend. Host free on GitHub Pages.

## How it works

`index.html` loads `places.md` and renders everything. Edit the markdown file to change content. Push to GitHub, it's live.

## File structure

```
index.html     ← the app (don't need to touch this)
places.md      ← all your content lives here
images/        ← drop photos here, reference in places.md
README.md      ← you're reading it
```

## Adding a spot

Open `places.md` and add a new entry at the bottom. Copy this template:

```
---

# Place Name

- Category: Cheap Eats
- Price: $
- Location: 20.9150, -100.7450
- Image: images/place-name.jpg
- Google Maps: https://www.google.com/maps/search/?api=1&query=Place+Name+City
- Instagram: https://www.instagram.com/handle/
- Facebook: https://www.facebook.com/page/

Your writeup goes here. Write as much as you want — it's your guide.
Multiple paragraphs work too, just leave a blank line between them.
```

### Rules

- Start each entry with `---` on its own line (except the first entry)
- The `# Name` line is required
- `Category` and `Location` are required — everything else is optional
- Leave out any line you don't need — it just won't show up
- Get coordinates from Google Maps: right-click any spot → "Copy coordinates"
- Description is everything after the `- metadata` lines — just write naturally

### Fields

| Field | Required | Example |
|-------|----------|---------|
| `# Name` | Yes | `# Café Rama` |
| `Category` | Yes | Must match one in the Categories section |
| `Location` | Yes | `20.9130, -100.7432` (lat, lng) |
| `Price` | No | `$`, `$$`, or `$$$` |
| `Image` | No | `images/cafe-rama.jpg` |
| `Google Maps` | No | Full Google Maps URL |
| `Instagram` | No | Full Instagram URL |
| `Facebook` | No | Full Facebook URL |

## Editing the guide info

The top of `places.md` (above the `===` line) controls the page header:

```
Guide: City Vibe Guide
Title: Where to Eat, Drink, and Wander in San Miguel de Allende
Subtitle: The taquerias and mezcalerías that make this town feel like home.
Author: SL FNK
Updated: August 2026
More Guides: [JLW](#), [ALEPNK](#)
```

## Adding a category

In the `## Categories` section, add a line with the name and a hex color:

```
## Categories

Cheap Eats: #E07A3A
Sit Down: #D95B43
Drinks: #8B5DAD
Landmark: #3D6B5E
Coffee: #8B6914
```

Filter buttons and pin colors update automatically.

## Adding images

1. Resize photos to ~800px wide (keeps the repo light)
2. Upload to an `images/` folder in the repo
3. Reference in your entry: `- Image: images/cafe-rama.jpg`

## Hosting on GitHub Pages

1. Create a new repo on GitHub
2. Upload `index.html`, `places.md`, and `README.md`
3. Go to **Settings → Pages → Source** → select `main` branch, `/ (root)`
4. Live at `https://yourusername.github.io/repo-name/`

## Making a guide for another city

1. Fork or copy this repo
2. Replace everything in `places.md` with your own content
3. Push — done

## Stack

- [Leaflet](https://leafletjs.com/) + [CARTO Voyager](https://carto.com/basemaps/) tiles — free, no API key
- Vanilla JS, no framework, no build step
- Google Fonts: Source Serif 4 + DM Sans
