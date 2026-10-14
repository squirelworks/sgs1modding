# Key Blueprints

## `Core/BP_ShipGameMode`

Central gameplay mode.

- `BookingShip(S_Ships_Stats)` — main entry for spawning a wreck.
- Stores `CurrentShipStats` and `NextShipStats` (SaveGame properties).
- Uses `GetStreamingLevel` on the row's `Level` name.
- Fires `ShipArrived`.
- Talks to `Base/Ship_Cutscenes_Manager`.
- Also involved in scrap spawning via `Lootable/BP_ScrapSpawnManager`.

## `Base/BP_Computer`

The yard computer.

- Has a `Uboats_Only` flag.
- Darkweb PC variant exists.
- Drives the ship selection UI.

## `Base/WBP_ComputerScreen`

Main computer widget.

- `SpawnShips` reads a DataTable of `S_Ships_Stats`.
- Uses `GetDataTableRowNames` + `GetDataTableRowFromName`.
- Filters by yard level and ship class.
- Builds `WBP_ShipSpawn` cards inside a `UniformGridPanel_Ships`.
- Uses `Ship_GameInstance` for DLC/filter state.

## `Base/WBP_ShipSpawn`

Individual ship card widget shown in the computer grid.

## `Base/Ship_Cutscenes_Manager`

Handles ship arrival cutscenes. Referenced by the game mode when a ship arrives. Cutscenes live under `Ships/Ship_*_Breaking_*` and related sequences.

## Player

`Characters/ShipCharacter/BP_ShipCharacter`

## Other Notable Assets

- `Base/BP_Barrack`, `BP_House`, `BP_Market`, `BP_ToolShop`, `BP_UpgradesShop`, `BP_Warehouse` — yard buildings and shops.
- Various `DT_Inspected*` tables for house furniture, tools, and upgrades progression.
- `Data/DT_Market_Items`, `DT_ToolsPrices`, `DT_Crafting_Receipts`, etc.
