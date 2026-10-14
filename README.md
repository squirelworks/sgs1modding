# Ship Graveyard Simulator 1 — Unofficial Modding Notes

Unofficial reverse-engineering and modding documentation for **Ship Graveyard Simulator 1** (Steam App ID 1286880, Unreal Engine 4.25, module `ShipGraveyard`).

The goal of this repository is to document the game's architecture well enough to add new ships (and related content) as mods.

## Contents

- [Overview](docs/overview.md) — High-level architecture
- [Ship Catalog](docs/ship-catalog.md) — `DT_Ship_Stats`, `S_Ships_Stats`, classes, and all 19 vanilla rows
- [Maps & Streaming](docs/maps-and-streaming.md) — Streamed sublevels, how wrecks are loaded
- [Key Blueprints](docs/key-blueprints.md) — Game mode, computer, cutscenes, player
- [Adding a New Ship](docs/adding-a-ship.md) — Practical checklist based on current knowledge
- [Paths & Saves](docs/paths-and-saves.md) — Pak locations, save games, DLC flags

## Quick Facts

- Engine: Unreal Engine 4.25
- Module: `ShipGraveyard`
- Ship catalog type: `Base/S_Ships_Stats` (Guid `59AB94C9-424CB5DE-0FCA2B8C-09C5BF8D`)
- Catalog DataTable: `Data/DT_Ship_Stats` (19 rows)
- Wrecks are streamed sublevels under `/Game/ShipGraveyard/Maps/Ships/` and `/Maps/Submarines/`
- Computer UI: `Base/WBP_ComputerScreen` + `Base/BP_Computer`
- Game mode: `Core/BP_ShipGameMode`

This documentation was generated from extracted asset dumps and runtime analysis. Contributions and corrections are welcome.

**Disclaimer**: This is unofficial documentation for educational/modding purposes. All game content remains the property of its respective owners.
