# Catholic Movement Data (markdown-only repo)

This repository is an **atomized**, **markdown-first** movement dataset intended for Git-based workflows.

- One node = one file.
- No JSON.
- YAML front matter holds structured fields.
- Markdown body holds the “main text” for the node.

This repo currently contains one movement: `mov-catholic` (movement slug: `catholic`).

## Layout

- `movements/<movementSlug>/movement.md` — movement header (front matter + summary)
- `movements/<movementSlug>/<collection>/*.md` — one file per node

Collections:

- `texts`
- `textCollections`
- `entities`
- `practices`
- `events`
- `rules`
- `claims`
- `media`
- `notes`

## Obsidian-friendly links

Every file includes an `aliases` entry equal to its canonical id (e.g. `ent-jesus-christ`), so you can link between nodes with simple wiki links like:

- `[[ent-jesus-christ]]`
- `[[txt-nicene-creed]]`
- `[[pr-sunday-mass]]`

These links are used throughout the front matter arrays (e.g. `mentionsEntityIds`, `supportingTextIds`, etc.) so Obsidian can build a graph and backlinks automatically.

## “Main text” field mapping

The markdown body is treated as the primary text field for each node type:

- **Movement** → `summary`
- **TextNode** (`type: text`) → `content`
- **Entity** → `summary`
- **Practice** → `description`
- **Event** → `description`
- **Rule** → `details`
- **Claim** → `text`
- **MediaAsset** (`type: media`) → `description`
- **Note** → `body`
- **TextCollection** → `description`

## Source / provenance

This dataset was converted from an earlier single-file JS dataset (`movements/catholic-church-data.js`, version `3.6`).

No semantic content was changed during the conversion:
- JSON fields became YAML front matter.
- The “main text” fields became markdown bodies.
