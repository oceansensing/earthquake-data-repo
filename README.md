# earthquake-data-repo

The world's **earthquakes**, from the U.S. Geological Survey: a data repository of the oceansensing ocean map system, with its own
schedule and its own place on Cloudflare R2, and no code of its own.

**Nothing is published yet.** `PLAN.md` is the founding plan; `CLAUDE.md` carries what must not be
got wrong and the shared doc doctrine.

## What it publishes

The world's earthquakes as the U.S. Geological Survey's Earthquake Hazards Program reports them, every ten minutes, in one file, `quakes.json`: every earthquake of magnitude 4.5 and above worldwide in the past 30 days, of 2.5 and above in the past 7 (the smaller ones mostly from the United States' regional networks — the USGS's worldwide catalog starts near 4.5), and every event it marks significant in the past 30 — each with its time, place, depth, magnitude and its type, whether it has been reviewed, its PAGER impact estimate where there is one, the USGS's tsunami flag, its significance, its felt reports and intensities, and its event page. Newest first. R2's alone.

These products are published to **Cloudflare R2 alone**, for a downstream reader: no Pages site,
and the website neither draws nor lists them (the site pipeline's D13).

## Where the data comes from

The U.S. Geological Survey's real-time GeoJSON summary feeds (`earthquake.usgs.gov/earthquakes/feed/v1.0/`): `4.5_month`, `2.5_week` and `significant_month`, made again each minute. **Their terms were read before a line was written** (2026-11-11): USGS-authored data are in the U.S. public domain, the USGS asking to be credited as "U.S. Geological Survey"; its logo is not used and no endorsement implied.

## How it runs

The orchestrator (the site's private `pipeline/`), the fetchers and the
published-file contract all come from `oceansensing.github.io`, checked out at
run time. This repository carries `pipeline/products.toml` and its publish
workflow, and nothing else executable. Each run publishes to Cloudflare R2 alone
(the site pipeline's D13). Related repositories: none it depends on.

**Which document gets what, and what "update docs" means across all
thirty-four repositories, is the doctrine block at the top of `CLAUDE.md`**: the
same text in all thirty-four, held equal by the site's `check:docs`.

## Structure

```
README.md       what this is
CLAUDE.md       what must not be got wrong, and the shared doc doctrine
PLAN.md         the founding plan and running record
DECISIONS.md    dated one-way decisions, D1 onward
pipeline/       products.toml, the declaration the orchestrator reads
.github/        the publish workflow
```
