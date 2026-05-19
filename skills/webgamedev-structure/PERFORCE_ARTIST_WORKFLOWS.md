# Perforce Artist Workflows

Helix Core is currently branded as P4 in product docs; the command remains `p4`.

## Setup Checks

Confirm the environment before changing files:

```text
p4 set
p4 info
p4 login -s
p4 client -o
```

Expected setup includes `P4PORT`, `P4USER`, `P4CLIENT`, `P4CONFIG`, a valid `p4 login`, and a workspace view that maps the needed `//webgamedev/...` paths.

## Read-Only Diagnostics

These commands are safe diagnostics:

```text
p4 info
p4 set
p4 login -s
p4 client -o
p4 opened
p4 opened -as
p4 status
p4 reconcile -n
p4 sync -n
p4 diff -sa
p4 changes
p4 filelog
p4 fstat
```

Use `p4 opened -as` before editing binary art to see who else has files open.

## Sync

Preview first:

```text
p4 sync -n //webgamedev/<gamefolder>/...
```

Apply only after review:

```text
p4 sync //webgamedev/<gamefolder>/...
```

## Edit Existing Files

Check locks/opened files first for binary assets:

```text
p4 opened -as //webgamedev/<gamefolder>/texture/portrait/symbols/hp1.webp
p4 edit //webgamedev/<gamefolder>/texture/portrait/symbols/hp1.webp
```

## Add New Files

Place files in the correct GameForge path, then add:

```text
p4 add //webgamedev/<gamefolder>/texture/portrait/symbols/hp1.webp
```

## Reconcile Local Changes

Preview first:

```text
p4 reconcile -n //webgamedev/<gamefolder>/...
```

Apply only after checking the preview:

```text
p4 reconcile //webgamedev/<gamefolder>/...
```

Never automate `p4 reconcile -w`.

## Move, Delete, and Revert

Use explicit targets and review the changelist before submit:

```text
p4 move oldPath newPath
p4 delete filePath
p4 revert filePath
```

Never automate `p4 revert -w`.

## Submit

Before submitting:

```text
p4 opened
p4 diff -sa
p4 changes -m 10 //webgamedev/<gamefolder>/...
```

Submit with a changelist and clear description:

```text
p4 submit -c <change> -d "Description"
```

For `GLOBAL` / `_Common-New` changes, confirm cross-game impact, ownership, and QA expectations before submit.

## History and Review

Use these to answer what changed and why:

```text
p4 filelog filePath
p4 changes filePath
p4 fstat filePath
p4 diff -sa filePath
```

Resolve conflicts deliberately. Do not automate binary conflict resolution.
