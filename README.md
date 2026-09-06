# VoxelPixelThingie scenes

Scenes exported from [VoxelPixelThingie](https://github.com/skinnerboxentertainment/VoxelPixelThingie)
in the SPEC.md section 10 layout: one folder per bit with `passport.json`
(current state) and `events.jsonl` (history), and a sealed `manifest.json`
with SHA-256 hashes per file.

This repository is a mirror. Git is the distributed store: every clone is
a full copy, every commit is append-only, and every file has a fingerprint.

Read a scene from here over HTTPS with the project's `FetchStore`, for
example:

```
npm run scene:check -- <local folder> https://raw.githubusercontent.com/skinnerboxentertainment/VoxelPixelThingie-scenes/main/scenes/reference-8/
```

| Scene | Bits | Events | Notes |
|-------|-----:|-------:|-------|
| `scenes/reference-8` | 485 | 54,392 | the demo's 8x8x8 with a 3x3x3 corner carved, three passports |
