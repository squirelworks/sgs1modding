# Ship Catalog

## Struct: `S_Ships_Stats`

Defined in `/Game/ShipGraveyard/Base/S_Ships_Stats`.

- Guid: `59AB94C9-424CB5DE-0FCA2B8C-09C5BF8D`
- Size: ~352 bytes

| Field | Type | Notes |
|-------|------|-------|
| Name | Text | Display name |
| Flag | Text | Country flag code |
| ProductionDate | Text | Year |
| Weight | Text | Weight string |
| Price | int | Cost |
| Icon | PaperSprite | Large icon |
| IconMini | PaperSprite | Small icon |
| ShipClass | E_Ship_Class | S / M / L / U_M / U_L |
| Level | Name | Streamed map name |
| MaterialsInfo | Map (EItems → E_ShipMatAmount) | Expected materials |
| MaterialsChance | S_Spawn_Chance | Spawn chances (in Destructable_Objects) |
| NeededLevel | int | Required yard level |
| CutsceneNumber | int | Cutscene index |
| ShipTransform | Transform | Always identity in vanilla |

## Enum: `E_Ship_Class`

| Enumerator | Display |
|------------|---------|
| NewEnumerator0 | S |
| NewEnumerator1 | M |
| NewEnumerator2 | L |
| NewEnumerator4 | U_M |
| NewEnumerator5 | U_L |

## DataTable: `DT_Ship_Stats`

Path: `/Game/ShipGraveyard/Data/DT_Ship_Stats`

19 rows total:
- Surface ships: rows `1`–`15`
- Submarines: rows `1_0`–`1_3` (DLC / Uboats_Only related)

### Full Catalog

| Row | Name | Flag | Year | Weight | Price | Class | Level | NeededLevel |
|-----|------|------|------|--------|-------|-------|-------|-------------|
| 1 | Atropos | UK | 1985 | 3600 | 1 | S | SShip1_FishingRed | 1 |
| 2 | Friday | US | 1990 | 4000 | 100 | S | SShip5_Platform | 5 |
| 3 | Flame | DM | 2001 | 35000 | 400 | M | MShip1_HanRed | 5 |
| 4 | Lotus | PL | 1991 | 4000 | 250 | S | SShip2_FishingYellow | 10 |
| 5 | Lydia | SK | 1992 | 35000 | 700 | M | MShip4_MagRed | 10 |
| 6 | Harpy | JA | 1984 | 7600 | 600 | S | SShip4_FishingBig | 15 |
| 7 | Sophie | IT | 1989 | 65000 | 1000 | L | LShip3_OilTankerRed | 15 |
| 8 | Harvey | US | 1996 | 41000 | 900 | M | MShip2_RoroGrey | 20 |
| 9 | Venus | NH | 1995 | 54000 | 1350 | L | LShip5_OilTankerDome | 20 |
| 10 | Clam | PL | 1988 | 6400 | 900 | S | SShip3_FishingGreen | 25 |
| 11 | Roebuck | UK | 1995 | 53000 | 2000 | L | LShip2_ContainerBlue | 25 |
| 12 | Pucelle | US | 1996 | 42000 | 1600 | M | MShip3_RoroGreen | 30 |
| 13 | Pluto | UK | 1998 | 50000 | 2300 | L | LShip1_ContainerGreen | 30 |
| 14 | Caligula | NH | 1983 | 49000 | 2200 | M | MShip5_OilShip | 35 |
| 15 | Justinian | SK | 1991 | 60000 | 2600 | L | LShip4_OilTankerBlack | 40 |
| 1_0 | Storm | DE | 1938 | 12000 | 2000 | U_L | SubMag | 1 |
| 1_1 | Hurricane | US | 1940 | 15000 | 2200 | U_L | SubHan | 1 |
| 1_2 | Typhoon | JP | 1939 | 8000 | 1200 | U_M | SubTyphoon | 1 |
| 1_3 | Victor | IT | 1941 | 7000 | 900 | U_M | SubVictor | 1 |

Icons live under `/Game/ShipGraveyard/UI/mag/`.

## Hard Mode

A parallel table exists at `Data/HardMode/DT_Ship_Stats_HM`.
