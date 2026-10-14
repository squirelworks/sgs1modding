# Maps & Streaming

Wrecks are **not** spawned as actors in the main level. They are separate streamed sublevels.

## Map List

### Main Maps
- `MainMenu`
- `GameMap1` — primary yard
- `MovementMap` — test/partial

### Surface Ships (`/Game/ShipGraveyard/Maps/Ships/`)
- `SShip1_FishingRed` (Atropos)
- `SShip2_FishingYellow`
- `SShip3_FishingGreen`
- `SShip4_FishingBig`
- `SShip5_Platform`
- `MShip1_HanRed`
- `MShip2_RoroGrey`
- `MShip3_RoroGreen`
- `MShip4_MagRed`
- `MShip5_OilShip`
- `LShip1_ContainerGreen`
- `LShip2_ContainerBlue`
- `LShip3_OilTankerRed`
- `LShip4_OilTankerBlack`
- `LShip5_OilTankerDome`
- `BeachScrap`

### Submarines (`/Game/ShipGraveyard/Maps/Submarines/`)
- `SubHan`
- `SubMag`
- `SubTyphoon`
- `SubVictor`

## Example: `SShip1_FishingRed` (Atropos)

This is a relatively small prefab (~144 actors) and a good reference for structure:

- Visual hull: StaticMesh `kuter2` at approximately `(16770, 1575, -84)`, yaw 105°, scale 1.25/1.5
- Apex pieces: `BPC_H_T1_*` / `BPC_F_*` (using `BP_HammerScrap` / `BP_SawScrap`)
- 4 chests
- 7 `BP_LootableItem`
- 2 ladders
- 1 `BP_WorldIcon`
- 35 BlockingVolumes

Mesh kit assets live under `Ships/SmShip1` and `Destructable_Objects/`.

## Streaming

`BP_ShipGameMode.BookingShip`:
1. Receives an `S_Ships_Stats` row.
2. Stores it in `CurrentShipStats` / `NextShipStats` (SaveGame).
3. Calls `GetStreamingLevel` on the `Level` name.
4. Fires `ShipArrived`.
5. Communicates with `Ship_Cutscenes_Manager`.

`BeachScrap` package name is simply `BeachScrap`.

Scrap spawning is handled separately via `Lootable/BP_ScrapSpawnManager` (`SpawnShipScrap` / `RespawnBeachScrap`).
