# Agentic Journey — Diagrams

A running gallery of system diagrams generated end-to-end by an AI agent, as
part of documenting an agentic-engineering journey.

**Live site:** https://blancuzzij.github.io/agentic-journey/

Each diagram starts as a plain-language description, gets turned into a typed
JSON specification, and is deterministically compiled into a self-contained,
interactive HTML artifact (pan/zoom, dark/light themes, route tracing) via
[archify](https://github.com/tt-a1i/archify).

## Layout

- `index.html` — the gallery page served by GitHub Pages.
- `diagrams/<name>.html` — the rendered, interactive diagram.
- `diagrams/<name>.json` — the source specification that produced it.

## Adding a new diagram

1. Author a new `diagrams/<name>.json` spec and render/validate it with archify.
2. Copy the delivered `diagrams/<name>.html` alongside it.
3. Add one card to `index.html` linking to `diagrams/<name>.html`.
4. Commit and push — Pages redeploys automatically.
