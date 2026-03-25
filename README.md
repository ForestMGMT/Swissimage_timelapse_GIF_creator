# SWISSIMAGE Timelapse GIF Creator

Generate animated timelapse GIFs from historical Swiss aerial imagery (swisstopo SWISSIMAGE Zeitreise), straight from your browser — no GIS software needed.

![Example: draw a box on the map, get a timelapse GIF](https://github.com/ForestMGMT/Swissimage_timelapse_GIF_creator/raw/main/docs/preview.gif)

---

## What it does

- Shows an interactive map with current swisstopo aerial imagery
- You draw a rectangle over any area in Switzerland
- It downloads one aerial photo per year (from as far back as 1926)
- Assembles everything into an animated GIF with a year label on each frame

---

## Requirements

- **Python 3.10 or newer** — download from [python.org](https://www.python.org/downloads/)
- An internet connection (images are fetched live from swisstopo — no account needed)

---

## Installation

**1. Download the code**

Click the green **Code** button on this page → **Download ZIP**, then unzip it somewhere on your computer.

Or if you have git:
```bash
git clone https://github.com/ForestMGMT/Swissimage_timelapse_GIF_creator.git
```

**2. Open a terminal and navigate to the folder**

On Windows, open Command Prompt or PowerShell and run:
```bash
cd path\to\Swissimage_timelapse_GIF_creator\swissimage_timelapse
```

**3. Install dependencies**
```bash
python -m pip install -r requirements.txt
```

This installs everything needed (Pillow, Streamlit, Folium, pyproj). Takes about a minute.

---

## Running the app

```bash
python -m streamlit run app.py
```

Your browser will open automatically at `http://localhost:8501`.

---

## How to use it

1. **Draw a box** on the map using the rectangle tool (top-left of the map)
2. A green message confirms the coordinates were captured
3. Enter a **project name** (used for the output filename)
4. Set a **year range** (e.g. 1960 to 2020) and a **step** (e.g. every 5 years)
5. Click **Run**
6. When done, click **Download timelapse GIF**

---

## Tips

- Smaller areas = faster downloads and sharper images
- A step of 5 years gives a good balance between detail and file size
- The `frames/` folder stores the downloaded images so re-runs are faster
- Coverage varies by region — some areas have data back to the 1930s, others only from the 1970s

---

## Data source

Aerial imagery: [SWISSIMAGE Zeitreise](https://www.swisstopo.admin.ch/en/timetravel-aerial-images) by [swisstopo](https://www.swisstopo.admin.ch), accessed via their public WMS.
Coordinates in EPSG:2056 (Swiss LV95).
