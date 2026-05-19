---
description: GameForge //webgamedev folder structure and artist-safe P4 workflow guidance.
---

# webgamedev-structure

Use this skill when a user asks about GameForge asset structure, `//webgamedev/` P4 placement, checkout/submit steps, folder placement, local overrides, `_Common-New`, Spine exports, video animations, UI art, audio, text/data assets, artist-safe P4 workflows, or whether an asset belongs in `ASSETS/GLOBAL`, `ASSETS/LOCAL`, or source `assets`.

GameForge is the system name. Treat `//webgamedev/` as the P4 source of truth and the folder template as canonical. Tiki Titans, Tesla, and older project names are examples only.

## First Principles

- Final runtime assets go in `GAMEFORGE_folderstructure/ASSETS`.
- Source and WIP files go in `assets`, not the runtime delivery tree.
- `ASSETS/GLOBAL` maps to `//webgamedev/assets/_Common-New/`.
- `ASSETS/LOCAL` maps to `//webgamedev/<gamefolder>/`.
- `LOCAL` overrides `GLOBAL` only when the relative path under each root is identical.
- If unsure between global and local, choose `LOCAL` and leave a note.
- P4 mutating operations require explicit user approval and `--apply` when using bundled scripts.

## Reference Docs

- `GAMEFORGE_STRUCTURE.md`: canonical folder and override rules.
- `ASSET_PLACEMENT.md`: where each common art/audio/data asset belongs.
- `PERFORCE_ARTIST_WORKFLOWS.md`: safe P4 setup, edit, submit, and history workflows.
- `SAFETY_RULES.md`: preview-first, binary locking, GLOBAL review, and blocked operations.
- `INTEGRATIONS.md`: how this structure should guide adjacent H5G plugins and skills.

When answering placement questions, cite the exact target path and explain whether it is source, runtime `LOCAL`, or runtime `GLOBAL`.
