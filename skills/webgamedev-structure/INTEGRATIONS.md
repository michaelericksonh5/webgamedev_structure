# Integrations

## slot-art

Use GameForge placement when turning generated slot art into delivery assets. Generated final symbols, backgrounds, big-win art, logo, UI, effects, fonts, audio, and data should land in `GAMEFORGE_folderstructure/ASSETS/LOCAL` unless the prompt explicitly says the asset is platform-wide.

## Spine Animation

Spine source work stays in source `assets`. Final runtime Spine exports go to `texture/portrait/animations/spine`, with atlas, skeleton data, and texture pages kept together.

## AI Video

AI-generated or edited source video belongs under source `assets` until approved and built. Final runtime video animation outputs go to `texture/portrait/animations/video`.

## RTK Token Saver

Keep token-saving or setup wrappers optional and user-run. Marketplace install should remain inert and must not run P4 commands automatically.

## skill-auditor

Audits should verify that this plugin remains skills-only, references only existing sibling docs, keeps scripts optional, and blocks dangerous P4 operations.
