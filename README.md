# Agentic Journey — Diagrams

A running gallery of system diagrams generated end-to-end by an AI agent, as
part of documenting an agentic-engineering journey.

**Live site:** https://blancuzzij.github.io/agentic-journey/

Each diagram starts as a plain-language description, gets turned into a typed
JSON specification, and is deterministically compiled into a self-contained,
interactive HTML artifact (pan/zoom, dark/light themes, route tracing) via
[archify](https://github.com/tt-a1i/archify).

## How it's organized

The gallery is a drill-down, not a flat list: one simple overview diagram to
start, and detail diagrams a reader can go deeper into from there. Each detail
diagram's copy says explicitly which node of the overview it's zooming into.

## Layout

- `index.html` — the gallery page served by GitHub Pages.
- `diagrams/<name>/index.html` — a thin wrapper page with a persistent
  "back to gallery" bar, embedding the real diagram via iframe.
- `diagrams/<name>.html` — the actual archify-delivered diagram. Frozen once
  validated — never hand-edited after delivery.
- `diagrams/<name>.json` — the source specification that produced it.
- `diagrams/<name>/og-image.png` — the 1200×630 Share Card (via archify's
  Export → Share Card) used for link previews (Open Graph / Twitter Card).

## Adding a new diagram

1. Author a new `diagrams/<name>.json` spec and validate/deliver it with archify
   (`node bin/archify.mjs validate ...` then `deliver ...`).
2. Copy the delivered `diagrams/<name>.html` and `.json` into this repo's
   `diagrams/` folder.
3. Create `diagrams/<name>/index.html` — copy an existing wrapper page and
   update the title, description, iframe `src`, and back-link.
4. Open the diagram, use **Export → Share Card** to get a 1200×630 PNG, save
   it as `diagrams/<name>/og-image.png`.
5. Add the Open Graph / Twitter meta tags to the wrapper page (title,
   description, url, image — see an existing wrapper for the pattern).
6. Add one card to `index.html` under "Go deeper" (or promote it to a new
   overview if it starts its own drill-down).
7. Commit and push — Pages redeploys automatically within a minute or two.
