# Overview

Ship Graveyard Simulator 1 is built in Unreal Engine 4.25. The primary module is `ShipGraveyard`.

## High-Level Flow

1. Player interacts with the **Computer** (`Base/BP_Computer`) in the yard.
2. The computer UI (`Base/WBP_ComputerScreen`) reads the ship catalog DataTable (`Data/DT_Ship_Stats`).
3. It filters ships by yard level and class, then presents cards (`Base/WBP_ShipSpawn`).
4. When a ship is booked, `Core/BP_ShipGameMode.BookingShip` is called with an `S_Ships_Stats` row.
5. The game mode streams the corresponding level (via `Level` name field) and triggers arrival cutscenes through `Base/Ship_Cutscenes_Manager`.
6. The wreck appears as a streamed sublevel containing the visual hull, destructible pieces, loot, chests, blocking volumes, etc.

## Important Asset Locations

| Purpose | Path |
|---------|------|
| Ship catalog type | `/Game/ShipGraveyard/Base/S_Ships_Stats` |
| Ship catalog data | `/Game/ShipGraveyard/Data/DT_Ship_Stats` |
| Hard mode catalog | `/Game/ShipGraveyard/Data/HardMode/DT_Ship_Stats_HM` |
| Computer | `/Game/ShipGraveyard/Base/BP_Computer` |
| Computer UI | `/Game/ShipGraveyard/Base/WBP_ComputerScreen` |
| Ship card widget | `/Game/ShipGraveyard/Base/WBP_ShipSpawn` |
| Game mode | `/Game/ShipGraveyard/Core/BP_ShipGameMode` |
| Cutscene manager | `/Game/ShipGraveyard/Base/Ship_Cutscenes_Manager` |
| Player | `/Game/ShipGraveyard/Characters/ShipCharacter/BP_ShipCharacter` |
| Maps root | `/Game/ShipGraveyard/Maps/` |
| Ship wrecks | `/Game/ShipGraveyard/Maps/Ships/` |
| Submarines | `/Game/ShipGraveyard/Maps/Submarines/` |

## Maps

- `MainMenu`
- `GameMap1` — main yard
- `MovementMap` — test / partial map
- Streamed ship levels: `SShip1`–`SShip5`, `MShip1`–`MShip5`, `LShip1`–`LShip5`, `BeachScrap`
- Streamed sub levels: `SubHan`, `SubMag`, `SubTyphoon`, `SubVictor`

All `ShipTransform` values in the catalog are identity; the actual pose lives inside the streamed map.
