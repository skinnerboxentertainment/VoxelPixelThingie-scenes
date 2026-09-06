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

## IPFS

The same scene, packed as one file (`vpb-scene-pack/1`), is pinned on IPFS:

- CID `bafybeibbu7hdh6jmuovoonsppyhjzni74av6koqkq2wjemqtgjvphkwi6m`
- https://gateway.pinata.cloud/ipfs/bafybeibbu7hdh6jmuovoonsppyhjzni74av6koqkq2wjemqtgjvphkwi6m

Verified 2026-09-06: opened from this repository's raw URL, from the local
folder, from the local pack, and from the gateway, all four give digest
`874d9a2552f19cb947279051346aa37d6b5fc421e85fdc41d6508b4605d11e14`.
Check it yourself from a VoxelPixelThingie checkout:

```
npm run scene:check -- <local folder or pack.json> https://raw.githubusercontent.com/skinnerboxentertainment/VoxelPixelThingie-scenes/main/scenes/reference-8/ pack:https://gateway.pinata.cloud/ipfs/bafybeibbu7hdh6jmuovoonsppyhjzni74av6koqkq2wjemqtgjvphkwi6m
```

## Signed seal and DID (2026-09-06)

`scenes/reference-8/manifest.json` carries an Ed25519 signature over its
seal. The container's DID is
`did:web:skinnerboxentertainment.github.io:VoxelPixelThingie-scenes:scenes:reference-8:frame:01a0746b-4c1e-70d7-860f-4911b12a768a`,
served by this repository's GitHub Pages at
`scenes/reference-8/frame/<container id>/did.json` (a copy sits at
`scenes/reference-8/did.json`). Signed pack on IPFS:
`bafybeihvkvcr7f2oidvs54fvtulqdkxsru3uruqwbpmggnuy3hcddangju`.
Verify with `npm run scene:check` in the main repository.
