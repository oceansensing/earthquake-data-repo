# earthquake-data-repo: the founding plan and running record

The world's **earthquakes**, from the U.S. Geological Survey. Created on GitHub by the owner and given its documents by the site's
`pipeline/scaffold/new-origin.py`. **Nothing is published yet.**

## What it is for

The world's earthquakes as the U.S. Geological Survey's Earthquake Hazards Program reports them, every ten minutes, in one file, `quakes.json`: every earthquake of magnitude 4.5 and above worldwide in the past 30 days, of 2.5 and above in the past 7 (the smaller ones mostly from the United States' regional networks — the USGS's worldwide catalog starts near 4.5), and every event it marks significant in the past 30 — each with its time, place, depth, magnitude and its type, whether it has been reviewed, its PAGER impact estimate where there is one, the USGS's tsunami flag, its significance, its felt reports and intensities, and its event page. Newest first. R2's alone.

## Where the data comes from

The U.S. Geological Survey's real-time GeoJSON summary feeds (`earthquake.usgs.gov/earthquakes/feed/v1.0/`): `4.5_month`, `2.5_week` and `significant_month`, made again each minute. **Their terms were read before a line was written** (2026-11-11): USGS-authored data are in the U.S. public domain, the USGS asking to be credited as "U.S. Geological Survey"; its logo is not used and no endorsement implied.

## Open

1. The first dispatched run, read: `quakes.json` on R2, its count and its newest event as the USGS's own map shows.
2. Then the ten-minute schedule, and a day of its runs read: none refused, the budget held.
3. NOAA's tsunami warning centers' latest bulletins (tsunami.gov), beside the earthquakes.
