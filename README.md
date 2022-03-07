# Yagisan's Better Stellaris

## Warfare

### War Exhaustion

Overall, War Exhaustion is an interesting mechanic. However some aspects of warfare, don't seem to impact it as much as I feel they should, and it does grow slowly, making reduction bonuses not really useful. The rate of war exhaustion grows has been buffed, with defensive armies now contributing towards it, and overall armies losses now being worth more. Planetary occupation is worth more, so now taking planets is worth it.

| War Exhaustion Related Defines  | Vanilla | Modded |
| ------------------------------- | ------: | -----: |
| WAR_EXHAUSTION_ARMY_KILLED_MULT |    0.25 |   0.50 |
| OCCUPATION_POP_VALUE            |     0.1 |   0.30 |


## Ground Combat

Ground combat in Stellaris is rather lacking by default. In theory it should be a vital part of conquest, but instead feels inconsequential. These changes seek to make ground combat a more strategic, and useful part of the game.

### Generals

In vanilla Stellaris, Generals are functionally useless. Their traits are lackluster at best, and they die far too quickly, with a 5% chance per army death. To make them more useful, their experience rate gain has been buffed, and their chance of dying has been nerfed. However, their traits still remain fairly lackluster.

| Leader - General Related Defines                      | Vanilla | Modded |
| ----------------------------------------------------- | ------: | -----: |
| LEADER_GENERAL_GROUND_COMBAT_BASE_EXPERIENCE          |     100 |    200 |
| LEADER_GENERAL_GROUND_COMBAT_EXPERIENCE_SCALE         |     2.5 |    4.0 |
| LEADER_GENERAL_GROUND_COMBAT_ARMIES_KILLED_CONVERSION |    0.25 |   0.50 |
| GENERAL_DEATH_CHANCE                                  |    0.05 |   0.01 |

### Defence Armies

| Defense Army      | Vanilla |  Modded |
| ----------------- | ------: | ------: |
| Army Damage       |     1.5 |     1.5 |
| Morale Damage     |         |     0.5 |
| Collateral Damage |     0.0 |     0.0 |
| War Exhaustion    |     0.0 |     0.5 |
| Health            |    1.25 |     1.0 |
| Morale            |    1.25 |     1.5 |
| Pop Species       | Organic | Organic |

| Undead Defense Army | Vanilla |  Modded |
| ------------------- | ------: | ------: |
| Army Damage         |     1.5 |     1.5 |
| Morale Damage       |    1.75 |     2.0 |
| Collateral Damage   |     0.0 |     0.0 |
| War Exhaustion      |     0.0 |     0.1 |
| Health              |    1.75 |     1.5 |
| Morale              |  Immune |  Immune |
| Pop Species         | Organic | Organic |

| Robotic Defense Army | Vanilla | Modded |
| -------------------- | ------: | -----: |
| Army Damage          |     1.0 |    2.0 |
| Morale Damage        |     1.0 |    1.0 |
| Collateral Damage    |     0.0 |    0.0 |
| War Exhaustion       |     0.0 |   0.25 |
| Health               |    1.25 |   1.25 |
| Morale               |  Immune | Immune |
| Pop Species          |   Robot |  Robot |

| Drone Grid        |      Vanilla |       Modded |
| ----------------- | -----------: | -----------: |
| Army Damage       |         1.10 |          2.0 |
| Morale Damage     |          1.0 |          1.0 |
| Collateral Damage |          0.0 |          0.0 |
| War Exhaustion    |          0.0 |         0.25 |
| Health            |         1.10 |         1.25 |
| Morale            |       Immune |       Immune |
| Pop Species       | Machine Unit | Machine Unit |

### Assault Armies

| Assault Army      |      Vanilla | Modded |
| ----------------- | -----------: | -----: |
| Army Damage       |          1.0 |
| Morale Damage     |          1.0 |
| Collateral Damage |          1.0 |
| War Exhaustion    |          1.0 |
| Health            |          1.0 |
| Morale            |          1.0 |
| Cost              | 100 Minerals |
| Time              |           90 |
| Upkeep            |     1 Energy |
| Pop Species       |      Organic |

| Slave Army        |     Vanilla | Modded |
| ----------------- | ----------: | -----: |
| Army Damage       |         1.0 |
| Morale Damage     |        0.75 |
| Collateral Damage |         1.5 |
| War Exhaustion    |         0.5 |
| Health            |           1 |
| Morale            |        0.75 |
| Cost              | 50 Minerals |
| Time              |          60 |
| Upkeep            |  0.5 Energy |
| Pop Species       |     Organic |

| Clone Army        |     Vanilla | Modded |
| ----------------- | ----------: | -----: |
| Army Damage       |         1.0 |
| Morale Damage     |             |
| Collateral Damage |        1.25 |
| War Exhaustion    |         0.5 |
| Health            |         1.0 |
| Morale            |         1.0 |
| Cost              | 75 Minerals |
| Time              |          30 |
| Upkeep            | 0.75 Energy |
| Pop Species       |     Organic |

| Robotic Army      |      Vanilla | Modded |
| ----------------- | -----------: | -----: |
| Army Damage       |          1.0 |
| Morale Damage     |          1.0 |
| Collateral Damage |          1.5 |
| War Exhaustion    |          0.5 |
| Health            |          2.0 |
| Morale            |       Immune |
| Cost              | 150 Minerals |
| Time              |           90 |
| Upkeep            |   1.5 Energy |
| Pop Species       |      Robotic |

| Psionic Army      |      Vanilla | Modded |
| ----------------- | -----------: | -----: |
| Army Damage       |          2.0 |
| Morale Damage     |          1.5 |
| Collateral Damage |          0.5 |
| War Exhaustion    |          3.0 |
| Health            |         1.75 |
| Morale            |          2.5 |
| Cost              | 250 Minerals |
| Time              |          120 |
| Upkeep            |   2.5 Energy |
| Pop Species       |      Organic |

| Xenomorph Army    |      Vanilla | Modded |
| ----------------- | -----------: | -----: |
| Army Damage       |          2.0 |
| Morale Damage     |          2.0 |
| Collateral Damage |          5.0 |
| War Exhaustion    |         0.25 |
| Health            |          2.0 |
| Morale            |       Immune |
| Cost              | 200 Minerals |
| Time              |          100 |
| Upkeep            |     2 Energy |
| Pop Species       |      Organic |

| Gene Warrior Army |      Vanilla | Modded |
| ----------------- | -----------: | -----: |
| Army Damage       |          2.0 |
| Morale Damage     |          1.0 |
| Collateral Damage |         0.75 |
| War Exhaustion    |          3.0 |
| Health            |          2.5 |
| Morale            |          2.5 |
| Cost              | 300 Minerals |
| Time              |          150 |
| Upkeep            |     3 Energy |
| Pop Species       |      Organic |

| Hunter-Killer Army |      Vanilla | Modded |
| ------------------ | -----------: | -----: |
| Army Damage        |          1.0 |
| Morale Damage      |          1.0 |
| Collateral Damage  |          2.0 |
| War Exhaustion     |          0.5 |
| Health             |          1.0 |
| Morale             |       Immune |
| Cost               | 100 Minerals |
| Time               |           90 |
| Upkeep             |     1 energy |
| Pop Species        |        Robot |

| Battle Frame      |      Vanilla | Modded |
| ----------------- | -----------: | -----: |
| Army Damage       |          1.5 |
| Morale Damage     |          1.5 |
| Collateral Damage |          2.0 |
| War Exhaustion    |          1.0 |
| Health            |          2.5 |
| Morale            |       Immune |
| Cost              | 200 Minerals |
| Time              |          120 |
| Upkeep            |     2 Energy |
| Pop Species       |        Robot |

| Mega-Warform      |      Vanilla | Modded |
| ----------------- | -----------: | -----: |
| Army Damage       |          4.0 |
| Morale Damage     |          1.5 |
| Collateral Damage |          4.0 |
| War Exhaustion    |          4.0 |
| Health            |          6.0 |
| Morale            |       Immune |
| Cost              | 800 Minerals |
| Time              |          500 |
| Upkeep            |     8 Energy |
| Pop Species       |        Robot |

| Undead Army       |     Vanilla | Modded |
| ----------------- | ----------: | -----: |
| Army Damage       |         1.0 |
| Morale Damage     |        1.75 |
| Collateral Damage |        1.25 |
| War Exhaustion    |         0.5 |
| Health            |         1.0 |
| Morale            |      Immune |
| Cost              |  100 Energy |
| Time              |          60 |
| Upkeep            | 0.75 Energy |
| Pop Species       |     Organic |
