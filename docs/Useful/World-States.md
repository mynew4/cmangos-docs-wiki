World states are used to set global world settings in the game, they're also used for map-specific variables and UI elements. Examples include arena season id, whether or not the arena season is active, battle status in battlegrounds and so on.

List of UI map icons:
![](http://images4.wikia.nocookie.net/__cb20100902055656/wowwiki/images/e/e1/Poiicons.png)

Global World States
-------------------

| ID   | Values            | UI Type  | Comment                                                    |
|------|-------------------|----------|------------------------------------------------------------|
| 2259 | Bool              | Map Icon | Naxxramas Invasion - Winterspring                          |
| 2260 | Bool              | Map Icon | Naxxramas Invasion - Azshara                               |
| 2261 | Bool              | Map Icon | Naxxramas Invasion - Blasted Lands                         |
| 2262 | Bool              | Map Icon | Naxxramas Invasion - Burning Steppes                       |
| 2263 | Bool              | Map Icon | Naxxramas Invasion - Tanaris Desert                        |
| 2264 | Bool              | Map Icon | Naxxramas Invasion - Eastern Plaguelands                   |
| 3801 | Bool              | Text     | Wintergrasp - is inactive (0: in progress, 1: not started) |
| 3802 | Bool              | Text     | Wintergrasp - Horde controlled                             |
| 3803 | Bool              | Text     | Wintergrasp - Alliance controlled                          |
| 3804 | WG Control Status | Map Icon | Wintergrasp - faction in control                           |
| 4354 | Time              | Timer    | Wintergrasp - start time                                   |

WG Control Status:

| Value | Icon Display |
|-------|--------------|
| 0     | Hidden       |
| 1     | Horde        |
| 2     | Alliance     |
| 3     | Contested    |

Zonewide World States
---------------------

### Warsong

| 1545 | Unk State  |          | Unknown - Alliance              |
|------|------------|----------|---------------------------------|
| 1546 | Unk State  |          | Unknown - Horde                 |
| 1581 | Int        | Counter  | Capture count - Alliance        |
| 1582 | Int        | Counter  | Capture count - Horde           |
| 1601 | Int        | Counter  | Capture count - maximum         |
| 2339 | Flag State | Map Icon | Silverwing Flag (Alliance)      |
| 2338 | Flag State | Map Icon | Warsong Flag (Horde)            |
| 4247 | Int        | Timer    | Timer enabled - Show/Hide timer |
| 4248 | Int        | Timer    | Time left                       |

Unk State:

| Value | Icon Display                |
|-------|-----------------------------|
| -1    | Flag on ground?             |
| 0     | Flag on base or respawning? |
| 1     | Flag on player?             |

Flag State:

| Value | Icon Display    |
|-------|-----------------|
| 1     | Flag on ground? |
| 2     | Flag on player? |

### Arathi Basin

| 1776 | Int  | Counter  | Resource count - Alliance        |
|------|------|----------|----------------------------------|
| 1777 | Int  | Counter  | Resource count - Horde           |
| 1780 | Int  | Counter  | Resource count - maximum         |
| 1955 | Int  | Counter  | Resource count - warning         |
| 1779 | Int  | Counter  | Base count - Alliance            |
| 1778 | Int  | Counter  | Base count - Horde               |
| 1842 | Bool | Map Icon | Stables - neutral                |
| 1767 | Bool | Map Icon | Stables - Alliance               |
| 1769 | Bool | Map Icon | Stables - Alliance contested     |
| 1768 | Bool | Map Icon | Stables - Horde                  |
| 1770 | Bool | Map Icon | Stables - Horde contested        |
| 1845 | Bool | Map Icon | Farm - neutral                   |
| 1772 | Bool | Map Icon | Farm - Alliance                  |
| 1774 | Bool | Map Icon | Farm - Alliance contested        |
| 1773 | Bool | Map Icon | Farm - Horde                     |
| 1775 | Bool | Map Icon | Farm - Horde contested           |
| 1846 | Bool | Map Icon | Blacksmith - neutral             |
| 1782 | Bool | Map Icon | Blacksmith - Alliance            |
| 1784 | Bool | Map Icon | Blacksmith - Alliance contested  |
| 1783 | Bool | Map Icon | Blacksmith - Horde               |
| 1785 | Bool | Map Icon | Blacksmith - Horde contested     |
| 1844 | Bool | Map Icon | Lumber Mill - neutral            |
| 1792 | Bool | Map Icon | Lumber Mill - Alliance           |
| 1794 | Bool | Map Icon | Lumber Mill - Alliance contested |
| 1793 | Bool | Map Icon | Lumber Mill - Horde              |
| 1795 | Bool | Map Icon | Lumber Mill - Horde contested    |
| 1843 | Bool | Map Icon | Gold Mine - neutral              |
| 1787 | Bool | Map Icon | Gold Mine - Alliance             |
| 1789 | Bool | Map Icon | Gold Mine - Alliance contested   |
| 1788 | Bool | Map Icon | Gold Mine - Horde                |
| 1790 | Bool | Map Icon | Gold Mine - Horde contested      |

### Alterac Valley

| 3127 | Int  | Counter  | Resource count - Alliance                   |
|------|------|----------|---------------------------------------------|
| 3128 | Int  | Counter  | Resource count - Horde                      |
| 2490 | Bool | Counter  | Show/Hide resource count - Alliance         |
| 2489 | Bool | Counter  | Show/Hide resource count - Horde            |
| 1326 | Bool | Map Icon | Stormpike Aid Station - Alliance            |
| 1325 | Bool | Map Icon | Stormpike Aid Station - Alliance contested  |
| 1328 | Bool | Map Icon | Stormpike Aid Station - Horde               |
| 1327 | Bool | Map Icon | Stormpike Aid Station - Horde contested     |
| 1335 | Bool | Map Icon | Stormpike Graveyard - Alliance              |
| 1333 | Bool | Map Icon | Stormpike Graveyard - Alliance contested    |
| 1336 | Bool | Map Icon | Stormpike Graveyard - Horde                 |
| 1334 | Bool | Map Icon | Stormpike Graveyard - Horde contested       |
| 1304 | Bool | Map Icon | Stoneheart Graveyard - Alliance             |
| 1302 | Bool | Map Icon | Stoneheart Graveyard - Alliance contested   |
| 1303 | Bool | Map Icon | Stoneheart Graveyard - Horde                |
| 1301 | Bool | Map Icon | Stoneheart Graveyard - Horde contested      |
| 1966 | Bool | Map Icon | Snowfall Graveyard - neutral                |
| 1343 | Bool | Map Icon | Snowfall Graveyard - Alliance               |
| 1341 | Bool | Map Icon | Snowfall Graveyard - Alliance contested     |
| 1344 | Bool | Map Icon | Snowfall Graveyard - Horde                  |
| 1342 | Bool | Map Icon | Snowfall Graveyard - Horde contested        |
| 1348 | Bool | Map Icon | Iceblood Graveyard - Alliance               |
| 1346 | Bool | Map Icon | Iceblood Graveyard - Alliance contested     |
| 1349 | Bool | Map Icon | Iceblood Graveyard - Horde                  |
| 1347 | Bool | Map Icon | Iceblood Graveyard - Horde contested        |
| 1339 | Bool | Map Icon | Frostwolf Graveyard - Alliance              |
| 1337 | Bool | Map Icon | Frostwolf Graveyard - Alliance contested    |
| 1340 | Bool | Map Icon | Frostwolf Graveyard - Horde                 |
| 1338 | Bool | Map Icon | Frostwolf Graveyard - Horde contested       |
| 1331 | Bool | Map Icon | Frostwolf Relief Hut - Alliance             |
| 1329 | Bool | Map Icon | Frostwolf Relief Hut - Alliance contested   |
| 1332 | Bool | Map Icon | Frostwolf Relief Hut - Horde                |
| 1330 | Bool | Map Icon | Frostwolf Relief Hut - Horde contested      |
| 1375 | Bool | Map Icon | Dunbaldar South Bunker - Alliance           |
| 1361 | Bool | Map Icon | Dunbaldar South Bunker - Alliance contested |
| 1378 | Bool | Map Icon | Dunbaldar South Bunker - Horde              |
| 1370 | Bool | Map Icon | Dunbaldar South Bunker - Horde contested    |
| 1374 | Bool | Map Icon | Dunbaldar North Bunker - Alliance           |
| 1362 | Bool | Map Icon | Dunbaldar North Bunker - Alliance contested |
| 1379 | Bool | Map Icon | Dunbaldar North Bunker - Horde              |
| 1371 | Bool | Map Icon | Dunbaldar North Bunker - Horde contested    |
| 1376 | Bool | Map Icon | Icewing Bunker - Alliance                   |
| 1363 | Bool | Map Icon | Icewing Bunker - Alliance contested         |
| 1380 | Bool | Map Icon | Icewing Bunker - Horde                      |
| 1372 | Bool | Map Icon | Icewing Bunker - Horde contested            |
| 1377 | Bool | Map Icon | Stoneheart Bunker - Alliance                |
| 1364 | Bool | Map Icon | Stoneheart Bunker - Alliance contested      |
| 1381 | Bool | Map Icon | Stoneheart Bunker - Horde                   |
| 1373 | Bool | Map Icon | Stoneheart Bunker - Horde contested         |
| 1390 | Bool | Map Icon | Iceblood Tower - Alliance                   |
| 1368 | Bool | Map Icon | Iceblood Tower - Alliance contested         |
| 1395 | Bool | Map Icon | Iceblood Tower - Horde                      |
| 1385 | Bool | Map Icon | Iceblood Tower - Horde contested            |
| 1389 | Bool | Map Icon | Tower Point - Alliance                      |
| 1367 | Bool | Map Icon | Tower Point - Alliance contested            |
| 1394 | Bool | Map Icon | Tower Point - Horde                         |
| 1384 | Bool | Map Icon | Tower Point - Horde contested               |
| 1388 | Bool | Map Icon | Frostwolf East - Alliance                   |
| 1366 | Bool | Map Icon | Frostwolf East - Alliance contested         |
| 1393 | Bool | Map Icon | Frostwolf East - Horde                      |
| 1383 | Bool | Map Icon | Frostwolf East - Horde contested            |
| 1387 | Bool | Map Icon | Frostwolf West - Alliance                   |
| 1365 | Bool | Map Icon | Frostwolf West - Alliance contested         |
| 1392 | Bool | Map Icon | Frostwolf West - Horde                      |
| 1382 | Bool | Map Icon | Frostwolf West - Horde contested            |
| 1360 | Bool | Map Icon | Mine north - neutral                        |
| 1358 | Bool | Map Icon | Mine north - Alliance                       |
| 1359 | Bool | Map Icon | Mine north - Horde                          |
| 1357 | Bool | Map Icon | Mine south - neutral                        |
| 1355 | Bool | Map Icon | Mine south - Alliance                       |
| 1356 | Bool | Map Icon | Mine south - Horde                          |

### Silithus

| ID   | Values | UI Type  | Comment                        |
|------|--------|----------|--------------------------------|
| 2313 | Int    | Counter  | Silithyst resources - Alliance |
| 2314 | Int    | Counter  | Silithyst resources - Horde    |
| 2317 | Int    | Counter  | Silithyst resources - maximum  |
| 2322 | Bool   | Map Icon | Sandworm - north               |
| 2323 | Bool   | Map Icon | Sandworm - south               |
| 2324 | Bool   | Map Icon | Sandworm - west                |
| 2325 | Bool   | Map Icon | Sandworm - east                |

### Eastern Plaguelands

| ID   | Values | UI Type  | Comment                                                      |
|------|--------|----------|--------------------------------------------------------------|
| 2327 | Int    | Counter  | Tower count - Alliance                                       |
| 2328 | Int    | Counter  | Tower count - Horde                                          |
| 2353 | Bool   | Map Icon | Plaguewood Tower - neutral                                   |
| 2368 | Bool   | Map Icon | Plaguewood Tower - Alliance progress                         |
| 2366 | Bool   | Map Icon | Plaguewood Tower - Alliance contested                        |
| 2370 | Bool   | Map Icon | Plaguewood Tower - Alliance                                  |
| 2367 | Bool   | Map Icon | Plaguewood Tower - Horde progress                            |
|      |        |          | Plaguewood Tower - Horde contested ... DOES NOT EXIST IN DBC |
| 2371 | Bool   | Map Icon | Plaguewood Tower - Horde                                     |
| 2352 | Bool   | Map Icon | Northpass Tower - neutral                                    |
| 2364 | Bool   | Map Icon | Northpass Tower - Alliance progress                          |
| 2362 | Bool   | Map Icon | Northpass Tower - Alliance contested                         |
| 2372 | Bool   | Map Icon | Northpass Tower - Alliance                                   |
| 2365 | Bool   | Map Icon | Northpass Tower - Horde progress                             |
| 2363 | Bool   | Map Icon | Northpass Tower - Horde contested                            |
| 2373 | Bool   | Map Icon | Northpass Tower - Horde                                      |
| 2361 | Bool   | Map Icon | Eastwall Tower - neutral                                     |
| 2357 | Bool   | Map Icon | Eastwall Tower - Alliance progress                           |
| 2359 | Bool   | Map Icon | Eastwall Tower - Alliance contested                          |
| 2354 | Bool   | Map Icon | Eastwall Tower - Alliance                                    |
| 2358 | Bool   | Map Icon | Eastwall Tower - Horde progress                              |
| 2360 | Bool   | Map Icon | Eastwall Tower - Horde contested                             |
| 2356 | Bool   | Map Icon | Eastwall Tower - Horde                                       |
| 2355 | Bool   | Map Icon | Crownguard Tower - neutral                                   |
| 2376 | Bool   | Map Icon | Crownguard Tower - Alliance progress                         |
| 2374 | Bool   | Map Icon | Crownguard Tower - Alliance contested                        |
| 2378 | Bool   | Map Icon | Crownguard Tower - Alliance                                  |
| 2377 | Bool   | Map Icon | Crownguard Tower - Horde progress                            |
| 2375 | Bool   | Map Icon | Crownguard Tower - Horde contested                           |
| 2379 | Bool   | Map Icon | Crownguard Tower - Horde                                     |
| 2426 | Bool   | Slider   | Capture point slider - enabled                               |
| 2427 | Int    | Slider   | Capture point slider - current value                         |
| 2428 | Int    | Slider   | Capture point slider - neutral percent                       |

### Hellfire Peninsula

| 2476 | Int  | Counter  | Tower count - Alliance                 |
|------|------|----------|----------------------------------------|
| 2478 | Int  | Counter  | Tower count - Horde                    |
| 2490 | Bool | Counter  | Show/Hide tower count - Alliance       |
| 2489 | Bool | Counter  | Show/Hide tower count - Horde          |
| 2485 | Bool | Map Icon | Broken Hill - neutral                  |
| 2483 | Bool | Map Icon | Broken Hill - Alliance                 |
| 2484 | Bool | Map Icon | Broken Hill - Horde                    |
| 2482 | Bool | Map Icon | Overlook - neutral                     |
| 2480 | Bool | Map Icon | Overlook - Alliance                    |
| 2481 | Bool | Map Icon | Overlook - Horde                       |
| 2472 | Bool | Map Icon | Stadium - neutral                      |
| 2471 | Bool | Map Icon | Stadium - Alliance                     |
| 2470 | Bool | Map Icon | Stadium - Horde                        |
| 2473 | Bool | Slider   | Capture point slider - enabled         |
| 2474 | Int  | Slider   | Capture point slider - current value   |
| 2475 | Int  | Slider   | Capture point slider - neutral percent |

### Zangarmarsh

| 2560 | Bool | Counter Icon | East Beacon - neutral                  |
|------|------|--------------|----------------------------------------|
| 2558 | Bool | Counter Icon | East Beacon - Alliance                 |
| 2559 | Bool | Counter Icon | East Beacon - Horde                    |
| 2557 | Bool | Counter Icon | West Beacon - neutral                  |
| 2555 | Bool | Counter Icon | West Beacon - Alliance                 |
| 2556 | Bool | Counter Icon | West Beacon - Horde                    |
| 2652 | Bool | Map Icon     | East Beacon - neutral                  |
| 2650 | Bool | Map Icon     | East Beacon - Alliance                 |
| 2651 | Bool | Map Icon     | East Beacon - Horde                    |
| 2646 | Bool | Map Icon     | West Beacon - neutral                  |
| 2644 | Bool | Map Icon     | West Beacon - Alliance                 |
| 2645 | Bool | Map Icon     | West Beacon - Horde                    |
| 2647 | Bool | Map Icon     | Twin Spire Ruins Graveyard - neutral   |
| 2648 | Bool | Map Icon     | Twin Spire Ruins Graveyard - Alliance  |
| 2649 | Bool | Map Icon     | Twin Spire Ruins Graveyard - Horde     |
| 2655 | Bool | Map Icon     | Flag ready - Alliance                  |
| 2658 | Bool | Map Icon     | Flag ready - Horde                     |
| 2656 | Bool | Map Icon     | Flag not ready - Alliance              |
| 2657 | Bool | Map Icon     | Flag not ready - Horde                 |
| 2527 | Bool | Slider       | Capture point slider - enabled         |
| 2528 | Int  | Slider       | Capture point slider - current value   |
| 2529 | Int  | Slider       | Capture point slider - neutral percent |

### Nagrand - Halaa

| 2491 | Int  | Counter      | Guards alive                           |
|------|------|--------------|----------------------------------------|
| 2493 | Int  | Counter      | Guards maximum                         |
| 2502 | Bool | Counter Icon | Halaa controlled - Alliance            |
| 2503 | Bool | Counter Icon | Halaa controlled - Horde               |
| 2671 | Bool | Map Icon     | Halaa controlled - neutral             |
| 2676 | Bool | Map Icon     | Halaa controlled - Alliance progress   |
| 2673 | Bool | Map Icon     | Halaa controlled - Alliance            |
| 2677 | Bool | Map Icon     | Halaa controlled - Horde progress      |
| 2672 | Bool | Map Icon     | Halaa controlled - Horde               |
| 2662 | Bool | Map Icon     | Wyvern north - Alliance neutral        |
| 2664 | Bool | Map Icon     | Wyvern north - Alliance                |
| 2762 | Bool | Map Icon     | Wyvern north - Horde neutral           |
| 2663 | Bool | Map Icon     | Wyvern north - Horde                   |
| 2670 | Bool | Map Icon     | Wyvern south - Alliance neutral        |
| 2669 | Bool | Map Icon     | Wyvern south - Alliance                |
| 2760 | Bool | Map Icon     | Wyvern south - Horde neutral           |
| 2668 | Bool | Map Icon     | Wyvern south - Horde                   |
| 2667 | Bool | Map Icon     | Wyvern west - Alliance neutral         |
| 2666 | Bool | Map Icon     | Wyvern west - Alliance                 |
| 2761 | Bool | Map Icon     | Wyvern west - Horde neutral            |
| 2665 | Bool | Map Icon     | Wyvern west - Horde                    |
| 2659 | Bool | Map Icon     | Wyvern east - Alliance neutral         |
| 2661 | Bool | Map Icon     | Wyvern east - Alliance                 |
| 2763 | Bool | Map Icon     | Wyvern east - Horde neutral            |
| 2660 | Bool | Map Icon     | Wyvern east - Horde                    |
| 2495 | Bool | Slider       | Capture point slider - enabled         |
| 2494 | Int  | Slider       | Capture point slider - current value   |
| 2497 | Int  | Slider       | Capture point slider - neutral percent |

### Terokkar Forest

| 2621 | Int  | Counter  | Tower count - Alliance                               |
|------|------|----------|------------------------------------------------------|
| 2622 | Int  | Counter  | Tower count - Horde                                  |
| 2620 | Bool | Multiple | Towers controlled - hide/show towers and tower count |
| 2508 | Bool | Timer    | Towers controlled - neutral                          |
| 2767 | Bool | Timer    | Towers controlled - Alliance                         |
| 2768 | Bool | Timer    | Towers controlled - Horde                            |
| 2512 | Bool | Timer    | Towers controlled - time left - minutes first digit  |
| 2510 | Bool | Timer    | Towers controlled - time left - minutes second digit |
| 2509 | Bool | Timer    | Towers controlled - time left - hours                |
| 2681 | Bool | Map Icon | West Tower - neutral                                 |
| 2683 | Bool | Map Icon | West Tower - Alliance                                |
| 2682 | Bool | Map Icon | West Tower - Horde                                   |
| 2686 | Bool | Map Icon | North Tower - neutral                                |
| 2684 | Bool | Map Icon | North Tower - Alliance                               |
| 2685 | Bool | Map Icon | North Tower - Horde                                  |
| 2690 | Bool | Map Icon | East Tower - neutral                                 |
| 2688 | Bool | Map Icon | East Tower - Alliance                                |
| 2689 | Bool | Map Icon | East Tower - Horde                                   |
| 2696 | Bool | Map Icon | South East Tower - neutral                           |
| 2694 | Bool | Map Icon | South East Tower - Alliance                          |
| 2695 | Bool | Map Icon | South East Tower - Horde                             |
| 2693 | Bool | Map Icon | South Tower - neutral                                |
| 2691 | Bool | Map Icon | South Tower - Alliance                               |
| 2692 | Bool | Map Icon | South Tower - Horde                                  |
| 2623 | Bool | Slider   | Capture point slider - enabled                       |
| 2625 | Int  | Slider   | Capture point slider - current value                 |
| 2624 | Int  | Slider   | Capture point slider - neutral percent               |

### The Eye of the Storm

| 2749 | Int        | Counter  | Resource count - Alliance              |
|------|------------|----------|----------------------------------------|
| 2750 | Int        | Counter  | Resource count - Horde                 |
| 2752 | Int        | Counter  | Tower count - Alliance                 |
| 2753 | Int        | Counter  | Tower count - Horde                    |
| 2722 | Bool       | Map Icon | Blood Elf Tower - neutral              |
| 2723 | Bool       | Map Icon | Blood Elf Tower - Alliance             |
| 2735 | Bool       | Map Icon | Blood Elf Tower - Alliance conflict    |
| 2724 | Bool       | Map Icon | Blood Elf Tower - Horde                |
| 2736 | Bool       | Map Icon | Blood Elf Tower - Horde conflict       |
| 2725 | Bool       | Map Icon | Fel Reaver Ruins - neutral             |
| 2726 | Bool       | Map Icon | Fel Reaver Ruins - Alliance            |
| 2739 | Bool       | Map Icon | Fel Reaver Ruins - Alliance conflict   |
| 2727 | Bool       | Map Icon | Fel Reaver Ruins - Horde               |
| 2740 | Bool       | Map Icon | Fel Reaver Ruins - Horde conflict      |
| 2728 | Bool       | Map Icon | Mage Tower - neutral                   |
| 2730 | Bool       | Map Icon | Mage Tower - Alliance                  |
| 2741 | Bool       | Map Icon | Mage Tower - Alliance conflict         |
| 2729 | Bool       | Map Icon | Mage Tower - Horde                     |
| 2742 | Bool       | Map Icon | Mage Tower - Horde conflict            |
| 2731 | Bool       | Map Icon | Draenei Ruins - neutral                |
| 2732 | Bool       | Map Icon | Draenei Ruins - Alliance               |
| 2738 | Bool       | Map Icon | Draenei Ruins - Alliance conflict      |
| 2733 | Bool       | Map Icon | Draenei Ruins - Horde                  |
| 2737 | Bool       | Map Icon | Draenei Ruins - Horde conflict         |
| 2757 | Bool       | Map Icon | Netherstorm Flag - ready               |
| 2769 | Flag State | Map Icon | Netherstorm Flag - Alliance            |
| 2770 | Flag State | Map Icon | Netherstorm Flag - Horde               |
| 2718 | Bool       | Slider   | Capture point slider - enabled         |
| 2719 | Int        | Slider   | Capture point slider - current value   |
| 2720 | Int        | Slider   | Capture point slider - neutral percent |

Flag State:

| Value | Icon Display    |
|-------|-----------------|
| 1     | Flag on ground? |
| 2     | Flag on player? |

### Isle of Quel'Danas

| ID   | Values | UI Type  | Comment                                       |
|------|--------|----------|-----------------------------------------------|
| 3414 | Bool   | Map Icon | Sun's Reach Armory - enemy                    |
| 3415 | Bool   | Map Icon | Sun's Reach Armory - Shattered Sun Offensive  |
| 3416 | Bool   | Map Icon | Sun's Reach Harbor - enemy                    |
| 3417 | Bool   | Map Icon | Sun's Reach Harbor - Shattered Sun Offensive  |
| 3418 | Bool   | Map Icon | Sun's Reach Sanctum - enemy                   |
| 3419 | Bool   | Map Icon | Sun's Reach Sanctum - Shattered Sun Offensive |

### Grizzly Hills - Venture Bay

| 3466 | Bool | Slider | Capture point slider - enabled         |
|------|------|--------|----------------------------------------|
| 3467 | Int  | Slider | Capture point slider - current value   |
| 3468 | Int  | Slider | Capture point slider - neutral percent |

### Wintergrasp

| ID   | Values       | UI Type  | Comment                                |
|------|--------------|----------|----------------------------------------|
| 3680 | Int          | Counter  | Vehicle count - Alliance               |
| 3490 | Int          | Counter  | Vehicle count - Horde                  |
| 3681 | Int          | Counter  | Vehicle maximum count - Alliance       |
| 3491 | Int          | Counter  | Vehicle maximum count - Horde          |
| 3710 | Bool         | Counter  | Show/Hide counters                     |
| 3700 | WG GO Status | Map Icon | Temple Point                           |
| 3701 | WG GO Status | Map Icon | Sunken Ring Point                      |
| 3702 | WG GO Status | Map Icon | Southwest Point                        |
| 3703 | WG GO Status | Map Icon | Southeast Point                        |
| 3704 | WG GO Status | Map Icon | Shadowsight Tower                      |
| 3705 | WG GO Status | Map Icon | Winters Edge Tower                     |
| 3706 | WG GO Status | Map Icon | Flamewatch Tower                       |
| 3773 | WG GO Status | Map Icon | Fortress                               |
| 3763 | WG GO Status | Map Icon | Fortress Gate                          |
| 3698 | WG GO Status | Map Icon | Fortress Workshop - west               |
| 3699 | WG GO Status | Map Icon | Fortress Workshop - east               |
| 3711 | WG GO Status | Map Icon | Fortress Tower - north west            |
| 3712 | WG GO Status | Map Icon | Fortress Tower - north east            |
| 3713 | WG GO Status | Map Icon | Fortress Tower - south west            |
| 3714 | WG GO Status | Map Icon | Fortress Tower - south east            |
| 3749 | WG GO Status | Map Icon | Fortress Wall - 1                      |
| 3750 | WG GO Status | Map Icon | Fortress Wall - 2                      |
| 3751 | WG GO Status | Map Icon | Fortress Wall - 3                      |
| 3752 | WG GO Status | Map Icon | Fortress Wall - 4                      |
| 3753 | WG GO Status | Map Icon | Fortress Wall - 5                      |
| 3754 | WG GO Status | Map Icon | Fortress Wall - 6                      |
| 3755 | WG GO Status | Map Icon | Fortress Wall - 7                      |
| 3756 | WG GO Status | Map Icon | Fortress Wall - 8                      |
| 3757 | WG GO Status | Map Icon | Fortress Wall - 9                      |
| 3758 | WG GO Status | Map Icon | Fortress Wall - 10                     |
| 3759 | WG GO Status | Map Icon | Fortress Wall - 11                     |
| 3760 | WG GO Status | Map Icon | Fortress Wall - 12                     |
| 3761 | WG GO Status | Map Icon | Fortress Wall - 13                     |
| 3762 | WG GO Status | Map Icon | Fortress Wall - 14                     |
| 3764 | WG GO Status | Map Icon | Fortress Wall - 15                     |
| 3765 | WG GO Status | Map Icon | Fortress Wall - 16                     |
| 3766 | WG GO Status | Map Icon | Fortress Wall - 17                     |
| 3767 | WG GO Status | Map Icon | Fortress Wall - 18                     |
| 3768 | WG GO Status | Map Icon | Fortress Wall - 19                     |
| 3769 | WG GO Status | Map Icon | Fortress Wall - 20                     |
| 3770 | WG GO Status | Map Icon | Fortress Wall - 21                     |
| 3771 | WG GO Status | Map Icon | Fortress Wall - 22                     |
| 3772 | WG GO Status | Map Icon | Fortress Wall - 23                     |
| 3779 | Bool         | Map Icon | PvP activity - A1                      |
| 3778 | Bool         | Map Icon | PvP activity - A2                      |
| 3777 | Bool         | Map Icon | PvP activity - A3                      |
| 3775 | Bool         | Map Icon | PvP activity - B1                      |
| 3774 | Bool         | Map Icon | PvP activity - B2                      |
| 3776 | Bool         | Map Icon | PvP activity - B3                      |
| 3748 | Bool         | Map Icon | PvP activity - C1                      |
| 3729 | Bool         | Map Icon | PvP activity - C2                      |
| 3744 | Bool         | Map Icon | PvP activity - C3                      |
| 3723 | Bool         | Map Icon | PvP activity - C4                      |
| 3739 | Bool         | Map Icon | PvP activity - C5                      |
| 3726 | Bool         | Map Icon | PvP activity - C6                      |
| 3788 | Bool         | Map Icon | PvP activity - D1                      |
| 3790 | Bool         | Map Icon | PvP activity - D2                      |
| 3797 | Bool         | Map Icon | PvP activity - D3                      |
| 3747 | Bool         | Map Icon | PvP activity - E1                      |
| 3730 | Bool         | Map Icon | PvP activity - E2                      |
| 3743 | Bool         | Map Icon | PvP activity - E3                      |
| 3725 | Bool         | Map Icon | PvP activity - E4                      |
| 3740 | Bool         | Map Icon | PvP activity - E5                      |
| 3727 | Bool         | Map Icon | PvP activity - E6                      |
| 3737 | Bool         | Map Icon | PvP activity - E7                      |
| 3796 | Bool         | Map Icon | PvP activity - F1                      |
| 3793 | Bool         | Map Icon | PvP activity - F2                      |
| 3746 | Bool         | Map Icon | PvP activity - F3                      |
| 3731 | Bool         | Map Icon | PvP activity - F4                      |
| 3799 | Bool         | Map Icon | PvP activity - G1                      |
| 3745 | Bool         | Map Icon | PvP activity - G2                      |
| 3792 | Bool         | Map Icon | PvP activity - G3                      |
| 3742 | Bool         | Map Icon | PvP activity - G4                      |
| 3724 | Bool         | Map Icon | PvP activity - G5                      |
| 3741 | Bool         | Map Icon | PvP activity - G6                      |
| 3728 | Bool         | Map Icon | PvP activity - G7                      |
| 3738 | Bool         | Map Icon | PvP activity - G8                      |
| 3794 | Bool         | Map Icon | PvP activity - G9                      |
| 3795 | Bool         | Map Icon | PvP activity - H1                      |
| 3791 | Bool         | Map Icon | PvP activity - H2                      |
| 3798 | Bool         | Map Icon | PvP activity - H3                      |
| 3501 | Bool         | Slider   | Capture point slider - enabled         |
| 3502 | Int          | Slider   | Capture point slider - current value   |
| 3508 | Int          | Slider   | Capture point slider - neutral percent |

WG GO Status:

| Value | Icon Display         |
|-------|----------------------|
| 0     | Hidden               |
| 1     | Neutral              |
| 2     | Damaged              |
| 3     | Destroyed            |
| 4     | Horde                |
| 5     | Horde - Damaged      |
| 6     | Horde - Destroyed    |
| 7     | Alliance             |
| 8     | Alliance - Damaged   |
| 9     | Alliance - Destroyed |

Wintergrasp Gameobject Locations - Walls and PvP activities:
![](http://imageshack.us/a/img692/3582/wintergrasppvpactivityl.jpg)
