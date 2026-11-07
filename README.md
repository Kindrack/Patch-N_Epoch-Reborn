# Patch-N: Project Epoch Reborn

A map patch for **World of Warcraft 3.3.5a (WotLK)**, modified for **[Project Epoch Reborn](https://project-epoch.org/)**. It adds dungeon entrance, cavern and mine maps to the world map, in the same way [WDM (World Dungeon Maps)](https://github.com/Trimitor/WDM-patch) does, trimmed down to the dungeons that exist on Project Epoch Reborn.

> **Status: on hold.**
> v0.1 is usable, but development is paused.
>
> **[Download Patch-N.zip (v0.1)](https://github.com/Kindrack/Patch-N_Epoch-Reborn/releases/download/v0.1/Patch-N.zip)** | [All releases](https://github.com/Kindrack/Patch-N_Epoch-Reborn/releases)
>
> Please read [Repository state](#repository-state-read-this-first) before downloading anything, and see the [Roadmap](#roadmap) for planned fixes.

---

## Repository state (read this first)

This repo is a little unusual, so here is exactly what is where:

| What | Where | What it is |
|---|---|---|
| **Files committed in the repo** | `main` branch | The **stock Patch-N from WDM**, exactly as it was at the time of commit. They are here as the baseline and reference. They are **not** the Project Epoch Reborn version. |
| **Project Epoch Reborn patch** | **[Releases](https://github.com/Kindrack/Patch-N_Epoch-Reborn/releases) → v0.1** (`Patch-N.zip`, containing `Patch-N.MPQ`) | The modified patch built for Project Epoch Reborn, made to work alongside the Patch-M that ships with Project Epoch Reborn (version from 23 October 2026). **This is the one you want to install.** |

I have **not** committed any of the changes to the repo, and only the release asset has been published. Because of that:

- The commit history will **not** show the changes. Compare the v0.1 release against the committed files if you want to see the differences.
- The repo contents will lag behind the release until the work is picked up again.

If you just want to use the patch, download it from the release and ignore the committed files.

---

## What is this?

WDM adds extra maps to the in-game world map for places that normally have none: dungeon entrances, caves, mines and similar locations. Project Epoch Reborn ships its own modified version of WDM's Patch-M, which includes the original WDM maps plus Project Epoch's custom content.

**Patch-N: Project Epoch Reborn** is a smaller companion patch. It keeps only the vanilla **Eastern Kingdoms** and **Kalimdor** dungeon entrances and caves, and adds a Blackfathom Deeps entrance map, which WDM never had.

It is designed to work with the **[ModernMapMarkers-Epoch](https://github.com/Kindrack/ModernMapMarkers-Epoch)** addon, which places dungeon portal markers on the world map. Left-click a marker to open the dungeon map, or right-click it to open the entrance map. These use the WDM patch maps if installed, and Atlas otherwise.

---

## What was changed compared to stock Patch-N

### Removed

To keep the patch focused on Project Epoch content, the following were stripped out:

- **Outland** zones
- **Northrend** zones
- **TBC Kalimdor** zones
- **Race starter areas**
- **Hyjal**
- **`Ogrimmar1_`**: Cleft of Shadows (Ragefire Chasm entrance map)
- **`TwilightsRun13_`**: cave in Silithus

What remains is the set of vanilla Eastern Kingdoms and Kalimdor dungeon entrances and caves.

### Added

- **`BlackfathomDeepsEntrance10_`**: a custom Blackfathom Deeps entrance map. Stock Patch-N has no map for it.

### Data files

The patch ships the `DBFilesClient` and `Interface/WorldMap` content needed for the remaining maps. The map data follows the stock 3.3.5a DBC layouts used by Project Epoch Reborn, so existing tools can read the tables without changes.

---

## Installation

1. Download **[Patch-N.zip](https://github.com/Kindrack/Patch-N_Epoch-Reborn/releases/download/v0.1/Patch-N.zip)** from the v0.1 release (not from the repo's source files). You can also get it from the [Releases page](https://github.com/Kindrack/Patch-N_Epoch-Reborn/releases).
2. Unzip it. The zip contains a single file, `Patch-N.MPQ`.
3. Place `Patch-N.MPQ` in your WoW `Data` folder, next to Project Epoch Reborn's own patch files (including Patch-M).
4. Restart the game client fully.

Keep the file name as `Patch-N.MPQ`. The client loads patches in alphabetical order, so Patch-N loads after Patch-M and its maps take priority over Patch-M's.

If you are using the **[ModernMapMarkers-Epoch](https://github.com/Kindrack/ModernMapMarkers-Epoch)** addon, no further setup is needed. Dungeon markers will open the maps from this patch when it is installed, and fall back to Atlas when it is not.

---

## Compatibility

- **Client:** WoW 3.3.5a (build 12340)
- **Server:** Project Epoch Reborn
- **Works with:** ModernMapMarkers-Epoch, Atlas, and the optional [WDM-addons](https://github.com/Trimitor/WDM-addons)

---

## Roadmap

Development is on hold. These are the planned fixes:

- Commit the Reborn changes to the repo so history and diffs are visible
- Some caves don't open the correct map when you enter them (WMO area mismatch)
- Verify entrance maps and click targets for every remaining dungeon
- Add a Sunken Temple entrance map. WDM doesn't have one, so this would be an original addition by this patch

---

## Credits

- **[Trimitor](https://github.com/Trimitor/WDM-patch)**: author of WDM and the original Patch-M and Patch-N maps this is built on. His [WDM-addons](https://github.com/Trimitor/WDM-addons) repo has optional addons that add floor names to the dungeon maps.
- **[Project Epoch Reborn](https://project-epoch.org/)**: the server and client environment this targets
- **Kindrack**: Project Epoch Reborn modifications

All original map art and tooling belong to their respective authors. This repo only redistributes modified map data for use on Project Epoch Reborn.

---

## Issues

Found a missing or wrong entrance map? Open an [issue](../../issues) and include the dungeon name and the in-game location.