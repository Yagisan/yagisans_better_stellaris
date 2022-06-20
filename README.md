# Yagisan's Better Stellaris

![GitHub all releases](https://img.shields.io/github/downloads/Yagisan/yagisans_better_stellaris/total?logo=GitHub&style=for-the-badge)![GitHub issues](https://img.shields.io/github/issues/Yagisan/yagisans_better_stellaris?logo=GitHub&style=for-the-badge)![Discord](https://img.shields.io/discord/958710541017317397?label=Yagisan%27s%20Discord&logo=discord&style=for-the-badge)

| [![patreon](assets/images/become_a_patron_button.png)](https://patreon.com/yagisan) | [![ko-fi](assets/images/support_on_kofi_button.png)](https://ko-fi.com/yagisan) | [![Discord Banner 2](https://discordapp.com/api/guilds/958710541017317397/widget.png?style=banner2)](https://discord.gg/rB5RFgHhUD) |
| ----------------------------------------------------------------------------------- | ------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------- |

- [Yagisan's Better Stellaris](#yagisans-better-stellaris)
  - [Jobs](#jobs)
    - [AI Empires](#ai-empires)
    - [Player Empires](#player-empires)
  - [Habitability](#habitability)
  - [Anomalies](#anomalies)
    - [Respawning](#respawning)
  - [Warfare](#warfare)
    - [War Exhaustion](#war-exhaustion)
  - [Ground Combat](#ground-combat)
    - [Generals](#generals)
    - [Defence Armies](#defence-armies)
    - [Assault Armies](#assault-armies)
    - [Occupation Armies](#occupation-armies)
    - [Event Armies](#event-armies)

## Jobs

The Stellaris AI appears to be somewhat lazy in making sure it's pops are in the most efficient job. To give it a helping hand we force it to re-evaluate jobs a bit more often. Once every two years **or** when loading a save game, we will scan for all AI empires, and flag them to be checked.

As a result pops tend to gradually end up in the most "optimal" job for them based on Stellaris or mod weightings. This does rely on Stellaris and/or the mod added job to have correctly set up their weightings.

### AI Empires

Each empire will be scheduled randomly between 10 and 180 days from the event firing. Already scheduled empires will be skipped. Once it is time to check the empire, each planet will be scheduled randomly between 0 and 90 days from the event firing.

This will allow all AI empires to complete re-evaluating jobs within 270 days of the initial event, and if the Stellaris random number generator is suitably random, not at the same time, so there won't be a noticeable lag spike.

### Player Empires

Player empires will be checked on the 28th day of each year. There's no delay for checking a player empire, as even in multiplayer, there's usually far less of them - and I want to minimise a confusing UI issue that occurs when moving pops around. Stellaris updates the UI instantly when firing pops. It updates at the end of the month when hiring pops.

## Habitability

Habitability doesn't matter much in base Stellaris. I have tweaked it to matter much more in the early game. Habitability has been reduced on primary planets to 70%, on secondary planets to 50%, and on tertiary planets to 10%. This will all be eventually mitigated by vanilla habitability technologies.

In addition, I have reduced the habitability spawn odds down to 30% to make habitable worlds much more valuable. Finally I have adjusted moon spawning sizes to always be smaller than planets, and to have a smaller overall size. The smallest moons will be size 8, and the largest size 12, while the smallest planets are size 12, and the largest are size 25.

Finally, for the purposes of habitability, pops with a Relic world preference will consider an Ecumenopolis a primary planet, and vice versa.

## Anomalies

In the base game, you eventually run out of anomalies, and your science ships become much less useful. By respawning anomalies scientists can continue to level up, and science ships can continue to be useful, throughout the game.

### Respawning

Each year the game will now attempt to respawn anomalies, provided their spawn conditions are met. These can respawn anywhere in the galaxy, in both player and AI controlled space.

The respawn system will attempt to respawn all Vanilla anomalies, and if you own the respective DLC, All Distant Stars Story Pack and Federations anomalies. The vanilla uplift anomalies will respawn too, but have been configured to have 1/5 the chance of regular anomalies.

Each attempt at respawning an anomaly has an 85% chance of success.

The specific spawn rates are:

- Every year, try to respawn 1 anomaly.
- Every second year, try to respawn 4 anomalies.
- Every fifth year, try to respawn 10 anomalies.

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

| Defence Army      | Vanilla |  Modded |
| ----------------- | ------: | ------: |
| Army Damage       |     1.5 |    1.50 |
| Morale Damage     |         |    1.00 |
| Collateral Damage |     0.0 |    0.00 |
| War Exhaustion    |     0.0 |    0.50 |
| Health            |    1.25 |    1.50 |
| Morale            |    1.25 |    1.50 |
| Pop Species       | Organic | Organic |

| Undead Defence Army | Vanilla |  Modded |
| ------------------- | ------: | ------: |
| Army Damage         |     1.5 |    1.50 |
| Morale Damage       |    1.75 |    2.00 |
| Collateral Damage   |     0.0 |    0.00 |
| War Exhaustion      |     0.0 |    0.10 |
| Health              |    1.75 |    1.50 |
| Morale              |  Immune |  Immune |
| Pop Species         | Organic | Organic |

| Robotic Defence Army | Vanilla | Modded |
| -------------------- | ------: | -----: |
| Army Damage          |     1.0 |   2.20 |
| Morale Damage        |     1.0 |   1.00 |
| Collateral Damage    |     0.0 |   0.00 |
| War Exhaustion       |     0.0 |   0.25 |
| Health               |    1.25 |   1.75 |
| Morale               |  Immune | Immune |
| Pop Species          |   Robot |  Robot |

| Drone Grid        |      Vanilla |       Modded |
| ----------------- | -----------: | -----------: |
| Army Damage       |         1.10 |         2.20 |
| Morale Damage     |          1.0 |         1.00 |
| Collateral Damage |          0.0 |         0.00 |
| War Exhaustion    |          0.0 |         0.25 |
| Health            |         1.10 |         1.75 |
| Morale            |       Immune |       Immune |
| Pop Species       | Machine Unit | Machine Unit |

| Offspring Defence Army | Vanilla |  Modded |
| ---------------------- | ------: | ------: |
| Army Damage            |    1.75 |    1.75 |
| Morale Damage          |    1.30 |    1.30 |
| Collateral Damage      |     0.0 |    0.00 |
| War Exhaustion         |     0.0 |    0.25 |
| Health                 |    2.00 |    2.00 |
| Morale                 |  Immune |  Immune |
| Pop Species            | Organic | Organic |

### Assault Armies

| Assault Army      |      Vanilla |       Modded |
| ----------------- | -----------: | -----------: |
| Army Damage       |          1.0 |         2.00 |
| Morale Damage     |          1.0 |         1.00 |
| Collateral Damage |          1.0 |         1.00 |
| War Exhaustion    |          1.0 |         1.00 |
| Health            |          1.0 |         1.00 |
| Morale            |          1.0 |         1.25 |
| Cost              | 100 Minerals | 100 Minerals |
| Time              |           90 |           90 |
| Upkeep            |     1 Energy |     1 Energy |
| Pop Species       |      Organic |      Organic |

| Slave Army        |     Vanilla |      Modded |
| ----------------- | ----------: | ----------: |
| Army Damage       |         1.0 |        1.00 |
| Morale Damage     |        0.75 |        0.50 |
| Collateral Damage |         1.5 |        1.50 |
| War Exhaustion    |         0.5 |        0.10 |
| Health            |           1 |        1.00 |
| Morale            |        0.75 |        0.50 |
| Cost              | 50 Minerals | 50 Minerals |
| Time              |          60 |          45 |
| Upkeep            |  0.5 Energy |  0.5 Energy |
| Pop Species       |     Organic |     Organic |

| Clone Army        |     Vanilla |      Modded |
| ----------------- | ----------: | ----------: |
| Army Damage       |         1.0 |        1.75 |
| Morale Damage     |             |        1.00 |
| Collateral Damage |        1.25 |        1.25 |
| War Exhaustion    |         0.5 |        0.25 |
| Health            |         1.0 |        1.00 |
| Morale            |         1.0 |        1.00 |
| Cost              | 75 Minerals | 75 Minerals |
| Time              |          30 |          30 |
| Upkeep            | 0.75 Energy | 0.75 Energy |
| Pop Species       |     Organic |     Organic |

| Robotic Army      |      Vanilla |       Modded |
| ----------------- | -----------: | -----------: |
| Army Damage       |          1.0 |         2.20 |
| Morale Damage     |          1.0 |         1.00 |
| Collateral Damage |          1.5 |         0.75 |
| War Exhaustion    |          0.5 |         0.25 |
| Health            |          2.0 |         1.50 |
| Morale            |       Immune |       Immune |
| Cost              | 150 Minerals | 150 Minerals |
| Time              |           90 |           90 |
| Upkeep            |   1.5 Energy |   1.5 Energy |
| Pop Species       |      Robotic |      Robotic |

| Psionic Army      |      Vanilla |       Modded |
| ----------------- | -----------: | -----------: |
| Army Damage       |          2.0 |         3.00 |
| Morale Damage     |          1.5 |         2.00 |
| Collateral Damage |          0.5 |         0.50 |
| War Exhaustion    |          3.0 |         1.25 |
| Health            |         1.75 |         1.75 |
| Morale            |          2.5 |         2.00 |
| Cost              | 250 Minerals | 250 Minerals |
| Time              |          120 |          120 |
| Upkeep            |   2.5 Energy |   2.5 Energy |
| Pop Species       |      Organic |      Organic |

| Xenomorph Army    |      Vanilla |       Modded |
| ----------------- | -----------: | -----------: |
| Army Damage       |          2.0 |         4.00 |
| Morale Damage     |          2.0 |         1.50 |
| Collateral Damage |          5.0 |         3.00 |
| War Exhaustion    |         0.25 |         0.20 |
| Health            |          2.0 |         2.00 |
| Morale            |       Immune |       Immune |
| Cost              | 200 Minerals | 200 Minerals |
| Time              |          100 |          100 |
| Upkeep            |     2 Energy |     2 Energy |
| Pop Species       |      Organic |      Organic |

| Gene Warrior Army |      Vanilla |       Modded |
| ----------------- | -----------: | -----------: |
| Army Damage       |          2.0 |         4.00 |
| Morale Damage     |          1.0 |         1.00 |
| Collateral Damage |         0.75 |         0.75 |
| War Exhaustion    |          3.0 |         1.50 |
| Health            |          2.5 |         2.50 |
| Morale            |          2.5 |         3.00 |
| Cost              | 300 Minerals | 300 Minerals |
| Time              |          150 |          150 |
| Upkeep            |     3 Energy |     3 Energy |
| Pop Species       |      Organic |      Organic |

| Hunter-Killer Army |      Vanilla |       Modded |
| ------------------ | -----------: | -----------: |
| Army Damage        |          1.0 |         2.20 |
| Morale Damage      |          1.0 |         1.00 |
| Collateral Damage  |          2.0 |         0.75 |
| War Exhaustion     |          0.5 |         0.25 |
| Health             |          1.0 |         1.50 |
| Morale             |       Immune |       Immune |
| Cost               | 100 Minerals | 100 Minerals |
| Time               |           90 |           90 |
| Upkeep             |     1 energy |     1 energy |
| Pop Species        |        Robot |        Robot |

| Battle Frame      |      Vanilla |       Modded |
| ----------------- | -----------: | -----------: |
| Army Damage       |          1.5 |         3.00 |
| Morale Damage     |          1.5 |         1.25 |
| Collateral Damage |          2.0 |         1.25 |
| War Exhaustion    |          1.0 |         0.75 |
| Health            |          2.5 |         2.20 |
| Morale            |       Immune |       Immune |
| Cost              | 200 Minerals | 200 Minerals |
| Time              |          120 |          120 |
| Upkeep            |     2 Energy |     2 Energy |
| Pop Species       |        Robot |        Robot |

| Mega-Warform      |      Vanilla |       Modded |
| ----------------- | -----------: | -----------: |
| Army Damage       |          4.0 |         5.00 |
| Morale Damage     |          1.5 |         1.50 |
| Collateral Damage |          4.0 |         2.00 |
| War Exhaustion    |          4.0 |         1.50 |
| Health            |          6.0 |         6.00 |
| Morale            |       Immune |       Immune |
| Cost              | 800 Minerals | 800 Minerals |
| Time              |          500 |          500 |
| Upkeep            |     8 Energy |     8 Energy |
| Pop Species       |        Robot |        Robot |

| Undead Army       |     Vanilla |      Modded |
| ----------------- | ----------: | ----------: |
| Army Damage       |         1.0 |        1.75 |
| Morale Damage     |        1.75 |        2.00 |
| Collateral Damage |        1.25 |        1.25 |
| War Exhaustion    |         0.5 |        0.10 |
| Health            |         1.0 |        1.00 |
| Morale            |      Immune |      Immune |
| Cost              |  100 Energy |  100 Energy |
| Time              |          60 |          30 |
| Upkeep            | 0.75 Energy | 0.75 Energy |
| Pop Species       |     Organic |     Organic |

### Occupation Armies

| Occupation Army   | Vanilla |  Modded |
| ----------------- | ------: | ------: |
| Army Damage       |     1.5 |    1.50 |
| Morale Damage     |         |    1.00 |
| Collateral Damage |     0.0 |    0.00 |
| War Exhaustion    |     0.0 |    0.50 |
| Health            |    1.25 |    1.50 |
| Morale            |    1.25 |    1.50 |
| Pop Species       | Organic | Organic |

| Robotic Occupation Army | Vanilla | Modded |
| ----------------------- | ------: | -----: |
| Army Damage             |     1.0 |   2.20 |
| Morale Damage           |     1.0 |   1.00 |
| Collateral Damage       |     0.0 |   0.00 |
| War Exhaustion          |     0.0 |   0.25 |
| Health                  |    1.25 |   1.75 |
| Morale                  |  Immune | Immune |
| Pop Species             |   Robot |  Robot |

| Machine Occupation Army |      Vanilla |       Modded |
| ----------------------- | -----------: | -----------: |
| Army Damage             |         1.10 |         2.20 |
| Morale Damage           |          1.0 |         1.00 |
| Collateral Damage       |          0.0 |         0.00 |
| War Exhaustion          |          0.0 |         0.25 |
| Health                  |         1.10 |         1.75 |
| Morale                  |       Immune |       Immune |
| Pop Species             | Machine Unit | Machine Unit |

### Event Armies

| Rebel Army    | Vanilla | Modded |
| ------------- | ------: | -----: |
| Army Damage   |     0.5 |   1.00 |
| Morale Damage |         |   0.50 |
| Health        |     0.5 |   1.00 |
| Morale        |     1.0 |   1.20 |

| Rebel Slave Army | Vanilla | Modded |
| ---------------- | ------: | -----: |
| Army Damage      |     0.8 |   1.00 |
| Morale Damage    |         |   0.50 |
| Health           |     0.8 |   0.90 |
| Morale           |    1.80 |   1.00 |

| Primitive Army | Vanilla | Modded |
| -------------- | ------: | -----: |
| Army Damage    |     0.1 |   0.20 |
| Morale Damage  |         |   0.20 |
| Health         |     0.5 |   0.50 |
| Morale         |    0.80 |   0.80 |

| Industrial Army | Vanilla | Modded |
| --------------- | ------: | -----: |
| Army Damage     |     0.4 |   0.90 |
| Morale Damage   |         |   0.40 |
| Health          |     0.5 |   0.70 |
| Morale          |    0.80 |   0.80 |

| Post-Atomic Army | Vanilla | Modded |
| ---------------- | ------: | -----: |
| Army Damage      |     0.6 |   1.00 |
| Morale Damage    |         |   0.50 |
| Health           |       1 |   1.00 |
| Morale           |       1 |   1.00 |

| Subterranean Industrial Army | Vanilla | Modded |
| ---------------------------- | ------: | -----: |
| Army Damage                  |     0.4 |   0.90 |
| Morale Damage                |         |   0.40 |
| Health                       |     0.5 |   0.70 |
| Morale                       |    0.80 |   0.80 |

| Subterranean Post-Atomic Army | Vanilla | Modded |
| ----------------------------- | ------: | -----: |
| Army Damage                   |     0.6 |   1.00 |
| Morale Damage                 |         |   0.50 |
| Health                        |       1 |   1.00 |
| Morale                        |       1 |   1.00 |

| Mutant Horror Army | Vanilla | Modded |
| ------------------ | ------: | -----: |
| Army Damage        |     1.5 |   3.00 |
| Morale Damage      |     1.5 |   1.50 |
| Health             |       2 |   2.00 |
| Morale             |  Immune | Immune |

| Swarm Army    | Vanilla | Modded |
| ------------- | ------: | -----: |
| Army Damage   |     1.5 |   4.00 |
| Morale Damage |     1.5 |   2.00 |
| Health        |       2 |   1.50 |
| Morale        |  Immune | Immune |

| Rampaging Tree Army | Vanilla | Modded |
| ------------------- | ------: | -----: |
| Army Damage         |     1.0 |   2.00 |
| Morale Damage       |     1.0 |   0.50 |
| Health              |     1.0 |   1.25 |
| Morale              |  Immune | Immune |

| Enraged Colonist Army | Vanilla | Modded |
| --------------------- | ------: | -----: |
| Army Damage           |     0.5 |   1.00 |
| Morale Damage         |         |   0.75 |
| Health                |     0.5 |   1.00 |
| Morale                |  Immune | Immune |

| Pre-Space Ketling Army | Vanilla | Modded |
| ---------------------- | ------: | -----: |
| Army Damage            |     0.6 |   0.90 |
| Morale Damage          |         |   0.40 |
| Health                 |     1.0 |   0.70 |
| Morale                 |     1.0 |   0.80 |

| Titanic Life Army |      Vanilla |       Modded |
| ----------------- | -----------: | -----------: |
| Army Damage       |          3.0 |         4.00 |
| Morale Damage     |          2.0 |         1.00 |
| Collateral Damage |          3.0 |         3.00 |
| War Exhaustion    |          2.0 |         1.00 |
| Health            |          5.0 |         5.00 |
| Morale            |          3.0 |         3.00 |
| Cost              | 300 Minerals | 300 Minerals |
| Time              |           90 |           90 |
| Upkeep            |     1 Energy |     1 Energy |

| Azizian Army      |                Vanilla |                 Modded |
| ----------------- | ---------------------: | ---------------------: |
| Army Damage       |                    3.0 |                   4.00 |
| Morale Damage     |                    2.0 |                   2.00 |
| Collateral Damage |                        |                   2.00 |
| War Exhaustion    |                        |                   1.00 |
| Health            |                    5.0 |                   5.00 |
| Morale            |                    2.0 |                   2.00 |
| Cost              | 250 Minerals 50 energy | 250 Minerals 50 energy |
| Time              |                     90 |                     90 |
| Upkeep            |               1 Energy |               1 Energy |

| Titanic Guardian Army | Vanilla | Modded |
| --------------------- | ------: | -----: |
| Army Damage           |     2.0 |   4.00 |
| Morale Damage         |     3.0 |   1.00 |
| Health                |     8.0 |   5.00 |
| Morale                |     3.0 |   3.00 |

| Shroud Army       | Vanilla |   Modded |
| ----------------- | ------: | -------: |
| Army Damage       |     5.0 |     6.00 |
| Morale Damage     |     2.0 |     2.00 |
| Collateral Damage |         |     1.00 |
| War Exhaustion    |     5.0 |     2.00 |
| Health            |     7.0 |    10.00 |
| Morale            |  Immune |   Immune |
| Upkeep            |         | 1 Energy |

| Gray Nanite Army  | Vanilla |   Modded |
| ----------------- | ------: | -------: |
| Army Damage       |    10.0 |     8.00 |
| Morale Damage     |     6.0 |     3.00 |
| Collateral Damage |     5.0 |     5.00 |
| War Exhaustion    |     4.0 |     4.00 |
| Health            |    18.0 |    14.00 |
| Morale            |  Immune |   Immune |
| Upkeep            |         | 1 Energy |

| Care Defensive Protocols | Vanilla | Modded |
| ------------------------ | ------: | -----: |
| Army Damage              |     4.0 |   5.00 |
| Morale Damage            |     1.5 |   1.50 |
| Collateral Damage        |     4.0 |   2.00 |
| War Exhaustion           |     4.0 |   1.50 |
| Health                   |     6.0 |   6.00 |
| Morale                   |  Immune | Immune |

| Sentinels     | Vanilla | Modded |
| ------------- | ------: | -----: |
| Army Damage   |     4.0 |   5.00 |
| Morale Damage |     5.0 |   5.00 |
| Health        |     7.0 |   6.00 |
| Morale        |  Immune | Immune |

| Cybrex Warform    |    Vanilla |     Modded |
| ----------------- | ---------: | ---------: |
| Army Damage       |        5.0 |       6.00 |
| Morale Damage     |        2.0 |       2.00 |
| Collateral Damage |        5.0 |       2.00 |
| War Exhaustion    |        4.0 |       1.00 |
| Health            |        7.0 |       9.00 |
| Morale            |     Immune |     Immune |
| Cost              | 250 Alloys | 250 Alloys |
| Time              |        500 |        500 |
| Upkeep            |   8 Energy |   8 Energy |
| Pop Species       |      Robot |      Robot |

| Imperial Legions  |      Vanilla |       Modded |
| ----------------- | -----------: | -----------: |
| Army Damage       |          2.5 |         2.50 |
| Morale Damage     |          1.0 |         1.00 |
| Collateral Damage |         0.75 |         0.75 |
| War Exhaustion    |          3.0 |         2.00 |
| Health            |          3.0 |         3.00 |
| Morale            |          3.0 |         3.00 |
| Cost              | 300 Minerals | 300 Minerals |
| Time              |          150 |          150 |
| Upkeep            |     3 Energy |     3 Energy |

| Ice Armies    | Vanilla | Modded |
| ------------- | ------: | -----: |
| Army Damage   |     1.5 |   2.00 |
| Morale Damage |     1.5 |   1.50 |
| Health        |     2.0 |   2.00 |
| Morale        |  Immune | Immune |
