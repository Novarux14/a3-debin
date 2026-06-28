# Debin - Arma 3 P3D Tool

Debin is a Windows desktop tool for inspecting Arma 3 P3D models, viewing model metadata, previewing LOD geometry, and reconstructing useful `model.cfg` information from ODOL files.

> The output may be incorrect or in some cases corrupt - please only use this for a tool and learning experience.



> Warning: This software is provided entirely as-is, without warranties or guarantees of any kind. Use it at your own risk.

## Features

- Open and inspect Arma 3 `.p3d` files.
- View high-level model stats including LODs, selections, bones, proxies, materials, and format.
- Preview model geometry in the built-in 3D viewer.
- Browse LODs and reset the viewer camera.
- View named selections, bones, proxies, and materials inside the app.
- Reconstruct and view `model.cfg` data without exporting first.
- Search inside the in-app `model.cfg` viewer with next/previous navigation.
- Export reconstructed `model.cfg` files.
- Reconstruct skeleton bones, root `sections[]`, animation selections, and animation axis names where recoverable.
- Debinarize ODOL P3D files to MLOD using the bundled conversion path.
- Compare a reference model/config against a target to spot missing selections, bones, sections, proxies, and LODs.

## Important Warning

This tool is experimental. Arma P3D and ODOL data can be complex, and not every original `model.cfg` detail is preserved in a way that can be perfectly reconstructed.

Always review exported or reconstructed files before using them in a mod project. Treat Debin as an inspection, learning, and helper tool rather than an authoritative converter.

## How To Run

1. Open the published app folder.
2. Run `app/Debin.exe`.
3. Click `Open P3D` and choose an Arma 3 `.p3d` file.

The app targets Windows and requires the .NET Desktop Runtime compatible with .NET 8 unless distributed as a self-contained build.

## model.cfg Reconstruction

Debin attempts to reconstruct `model.cfg` data from information embedded in the P3D, including:

- `CfgSkeletons`
- `CfgModels`
- `skeletonName`
- `sections[]`
- animation classes
- animation `selection`
- animation `axis` when a matching named axis selection can be resolved
- source ranges, angles, offsets, and source address values where available

Some values may be guessed, incomplete, or unavailable depending on the model and how much information survived binarization.

## Notes

Debin is intended for learning, inspection, and debugging Arma 3 model structure. Before uploading derived output into a mod repository or using it in-game, compare it against known-good configs and test carefully in the Arma 3 toolchain.
