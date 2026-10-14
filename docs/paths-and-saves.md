# Paths & Saves

## Pak Location

Mods / content paks go in:

```
Steam/steamapps/common/Ship Graveyard Simulator/ShipGraveyard/Content/Paks/
```

## Saves

Save games are stored under:

```
%LOCALAPPDATA%\ShipGraveyard\Saved\SaveGames\SGSGame1\
```

`Ship_GameInstance` default `SlotName` is `SGSGame1`.

## DLC / Submarines

- Submarine rows are named `1_0`–`1_3` in `DT_Ship_Stats`.
- `HasDLC` is set via `BIsDlcInstalled`.
- The computer has a `Uboats_Only` flag and a Darkweb PC variant that can restrict the catalog.

## Other Useful Paths (from asset dump)

- Config: `Config/DefaultEngine.json`, `DefaultGame.json`, `DefaultInput.json`
- Asset Registry: root `AssetRegistry.json`
- Baked ships: `Content/ShipGraveyard/BakedShips/`
- Destructible pieces: `Destructable_Objects/`
- UI sprites: `UI/mag/`
