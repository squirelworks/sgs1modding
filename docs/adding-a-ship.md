# Adding a New Ship

Based on the current reverse-engineering of the catalog, streaming, and computer UI.

## Minimum Requirements

1. **Streamed level**
   - Create a new level (e.g. `MShip6_MyShip`) under `/Game/ShipGraveyard/Maps/Ships/`.
   - Place the visual hull mesh, destructible pieces (`BP_HammerScrap` / `BP_SawScrap` style), chests, lootables, ladders, blocking volumes, and a world icon as needed.
   - Reference `SShip1_FishingRed` as a relatively simple example.

2. **Catalog row**
   - Add a new row to `Data/DT_Ship_Stats` (or a mod-injected equivalent).
   - Fill an `S_Ships_Stats` struct:
     - `Name`, `Flag`, `ProductionDate`, `Weight`, `Price`
     - `Icon` / `IconMini` (PaperSprites)
     - `ShipClass` (E_Ship_Class)
     - `Level` = the exact streamed map name
     - `NeededLevel`
     - `MaterialsInfo` and `MaterialsChance`
     - `CutsceneNumber` (or 0 if unused)
     - `ShipTransform` can stay identity

3. **Icons**
   - Place PaperSprites under `UI/mag/` following the existing naming pattern.

4. **Cutscene (optional)**
   - If you want an arrival cinematic, add entries under the cutscene system and set `CutsceneNumber` accordingly.

## Integration Points

- The computer (`WBP_ComputerScreen.SpawnShips`) automatically picks up any row that passes the level and class filters, provided it can read the DataTable.
- `BP_ShipGameMode.BookingShip` will stream whatever `Level` name is in the row.
- DLC/submarine filtering goes through `Ship_GameInstance` (`HasDLC` / `BIsDlcInstalled` for sub rows `1_0`–`1_3`).

## Notes & Caveats

- All vanilla `ShipTransform` values are identity; the real placement is authored in the streamed map.
- Materials and scrap types are driven by the maps and the `MaterialsInfo` / chance structs.
- For pure data mods, injecting a new DataTable row + a streamed level package is the cleanest path.
- Hard mode uses a separate table (`DT_Ship_Stats_HM`).

This is still incomplete. More work is needed on the exact scrap/Apex piece blueprints, loot tables, and how the computer discovers the DataTable at runtime.
