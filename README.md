# Catholic Movement Data (atomized repo)

This repository is an **atomized** movement dataset intended for Git-based workflows (add/remove/edit single nodes as single files).

## Layout

- `movements/<movementSlug>/movement.json` — movement header
- `movements/<movementSlug>/<type>/<idSlug>.json` — one file per node
- `movements/<movementSlug>/texts/<textSlug>.md` — optional markdown content for a text node

This repo currently contains one movement: `mov-catholic` (movement slug: `catholic`).

> Note: Content was converted from a single-file JS dataset (`movements/catholic-church-data.js`, version `3.6`) into this folder-based structure. No semantic content was changed; text `content` strings were moved into adjacent `.md` files.

## Source

- `source/movements/catholic-church-data.js` is a verbatim copy of the original single-file dataset used as the conversion input.
