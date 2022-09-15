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
  - [Space Combat](#space-combat)
  - [Ground Combat](#ground-combat)
    - [Generals](#generals)
    - [Defence Armies](#defence-armies)
    - [Assault Armies](#assault-armies)
    - [Occupation Armies](#occupation-armies)
    - [Event Armies](#event-armies)
  - [Artifacts](#artifacts)
  - [Starbase Buildings](#starbase-buildings)
    - [Changed Starbase Buildings](#changed-starbase-buildings)
      - [Crew Quarters / Crew Gestation Chambers / Service Umbilicals](#crew-quarters--crew-gestation-chambers--service-umbilicals)
      - [Resource Silo](#resource-silo)
      - [Nebula Refinery](#nebula-refinery)
      - [Listening Post](#listening-post)
      - [Offworld Trading Company](#offworld-trading-company)
      - [Hyperlane Registrar](#hyperlane-registrar)
      - [Deep Space Black Site](#deep-space-black-site)
      - [Curator Think Tank](#curator-think-tank)
      - [Trader Proxy Office](#trader-proxy-office)
      - [Command Center](#command-center)
      - [Transit Hub](#transit-hub)
      - [Disruption Field Generator](#disruption-field-generator)
      - [Hydroponics Bay](#hydroponics-bay)
      - [Shroud Beacon](#shroud-beacon)
      - [Naval Logistics Offices](#naval-logistics-offices)
    - [New Starbase Buildings](#new-starbase-buildings)
      - [Star Patrol Office](#star-patrol-office)

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

## Space Combat

The default Stellaris space combat AI displays some "selfish" behaviours. By default it aggressively tries to conquer as many systems as it can, while neglecting defence and allies. This often results in the AI winning battles, but ultimately losing the war due to war goals.

For example, in a defensive war, the defender's allied AI is only interested in taking its claims on the attacker.  Unfortunately, this causes two problems:
- Defenders and attackers enter a race to see who can take their claimed systems first.  If they are different systems, the war stalemates until war exhaustion force ends the war.
- Because the defender's allied AI is only interested in its claims, it does not care about defending its ally's systems.  The defender is often stuck on its own.  If the claimed systems are taken, both defender and their allies lose the war.

To try and mitigate this, I have implemented a shakeup of how the AI prioritises space combat. This is fundamentally incompatible with other space combat AI mods, such as Starnet.

The new space combat AI behaviour priority is:

- Reclaim our occupied planets.
- Defend our own invaded territory.
- Defend our allies invaded territory.
- Prioritise attacks along our border.
- Prioritise attacks along allies border.
- Prioritise attacks along conquered border.
- Prioritise attacks in neutral space.
- Defend our own territory.
- Defend our allies territory.
- Defend conquered territory.

When selecting targets, the new priority order is

- Enemy Fleets
- Enemy Starbases
- Systems with Planets
- All other systems.

The logic being fleets are what win wars, so they need to go first, and starbases make fleets, so they should go next.

Space Combat AI is a mixture of decision weights (I can tweak those) and hardcoded AI choices (I can't change those), and at the time of writing, I have not completely worked out the interactions between the two. I have observed that the "Defense" goal makes the AI defend, even if no attacks are incoming - which is not ideal.

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

## Artifacts

Without the Rubicator relic, artifacts are very difficult to acquire. Regular (Non-gestalt) empires now have a new option to buy artifacts from private collectors. These come at inflated prices, but do offer a way to continue acquiring them into the late game. If the AI has a surplus of resources, and less than 50 artifacts, they may purchase them as well.

## Starbase Buildings

With the addition of Orbital Rings, it's now possible to have more starbase buildings in each system. I have created several new buildings, and selectively edited a few vanilla buildings to provide the player with more options.

### Changed Starbase Buildings

#### Crew Quarters / Crew Gestation Chambers / Service Umbilicals

| Cost | Time | Upkeep | Orbital Ring |
| ---- | ---- | ------ | ------------ |
|   25   | 180 | 0 | **Yes** |

**Changes**

- Reduced building cost
- No upkeep
- Now provides 2 Naval capacity.

#### Resource Silo

| Cost | Time | Upkeep | Orbital Ring |
| ---- | ---- | ------ | ------------ |
|   50   | 180 | 0 | **No** |

**Changes**

- No longer able to build on Orbital Rings
- AI will no longer try building this in systems with colonies.
- Starts with 5000 storage. Can add 5000 more via tech.

#### Nebula Refinery

| Cost | Time | Upkeep | Orbital Ring |
| ---- | ---- | ------ | ------------ |
|   200   | 360 | 3 | **Yes** |

**Changes**

- Will now also produce 1 Volatile Mote with Mote Stabilization technology.
- Will now also produce 1 Rare Crystal with Rare Crystal Mining technology.

#### Listening Post

| Cost | Time | Upkeep | Orbital Ring |
| ---- | ---- | ------ | ------------ |
|   100   | 360 | 2 | **No** |

**Changes**

- +3 Sensor Range
- +6 Hyperlane detection Range
- +2 Trade Protection Range
- +1 Trade Protection

#### Offworld Trading Company

| Cost | Time | Upkeep | Orbital Ring |
| ---- | ---- | ------ | ------------ |
|   100   | 360 | 0 | **No** |

**Changes**

- +10% Trade for all colonies in the system.
- AI can now build at chokepoints

#### Hyperlane Registrar

| Cost | Time | Upkeep | Orbital Ring |
| ---- | ---- | ------ | ------------ |
|   100   | 180 | 2 | **No** |

**Changes**

- +2 Trade Collection Range
- AI can now build outside of chokepoints

#### Deep Space Black Site

| Cost | Time | Upkeep | Orbital Ring |
| ---- | ---- | ------ | ------------ |
|   100   | 360 | 2 | **No** |

**Changes**

- -10% Crime for all colonies in the system.
- AI will no longer try building this in systems without colonies.

#### Curator Think Tank

| Cost | Time | Upkeep | Orbital Ring |
| ---- | ---- | ------ | ------------ |
|   100   | 360 | 2 | **No** |

**Changes**

- +10 Research

#### Trader Proxy Office

| Cost | Time | Upkeep | Orbital Ring |
| ---- | ---- | ------ | ------------ |
|   100   | 360 | 0 | **No** |

**Changes**

- +10 Trade to the station with Unchained Knowledge resolution level 3 or above

#### Command Center

| Cost | Time | Upkeep | Orbital Ring |
| ---- | ---- | ------ | ------------ |
|   500   | 360 | 5 | **Yes** |

**Changes**

- +1 Starbase Capacity

#### Transit Hub

| Cost | Time | Upkeep | Orbital Ring |
| ---- | ---- | ------ | ------------ |
|   100   | 180 | 3 | **No** |

**Changes**

- No longer able to build on Orbital Rings.
- AI won't build it unless it has free jobs, free housing, or unemployed pops.

#### Disruption Field Generator

**Changes**

- Can no longer build in pulsar systems. Pulsars disable shields, so this is useless there.
- Construction aborted if the system contains a Communications Jammer (bugfix)

#### Hydroponics Bay

**Changes**

- Drastically reduce AI weight if they don't use food.
- Drastically reduce AI weight if they are producing food and have a massive (10,000+) stockpile.

#### Shroud Beacon

**Changes**

- AI much less likely to build this in the same sector as Shroudwalkers

#### Naval Logistics Offices

### New Starbase Buildings

**Changes**

- AI can now build these on Orbital Rings.

#### Star Patrol Office

| Cost | Time | Upkeep | Orbital Ring |
| ---- | ---- | ------ | ------------ |
|   200   | 360 | 3 | **No** |

**Requirements**

- Max 1 per system.
- Starbase must have at least 1 Hanger Bay
- Not a gestalt empire.

**Effects**

- Adds 5 trade protection for the Star Patrol office, and 5 trade protection for each hanger in the starbase. (Maximum of 35 trade protection)
- Adds 2 trade protection range for the Star Patrol office, and 1 trade protection range for each hanger in the starbase. (Maximum of 8 trade protection range)

**Description**

Non-gestalt empires can build a Star Patrol Office on any starbase with a hanger. This will extend both the range, and value of its anti-piracy protection. These starbases, when not in a system with colonies, or next to another empire will be known as Star Patrol Base.
