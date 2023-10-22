# Yagisan's Better Stellaris

![GitHub all releases](https://img.shields.io/github/downloads/Yagisan/yagisans_better_stellaris/total?logo=GitHub&style=for-the-badge)![GitHub issues](https://img.shields.io/github/issues/Yagisan/yagisans_better_stellaris?logo=GitHub&style=for-the-badge)![Discord](https://img.shields.io/discord/958710541017317397?label=Yagisan%27s%20Discord&logo=discord&style=for-the-badge)

| [![patreon](assets/images/become_a_patron_button.png)](https://patreon.com/yagisan) | [![ko-fi](assets/images/support_on_kofi_button.png)](https://ko-fi.com/yagisan) | [![Discord Banner 2](https://discordapp.com/api/guilds/958710541017317397/widget.png?style=banner2)](https://discord.gg/rB5RFgHhUD) |
| ----------------------------------------------------------------------------------- | ------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------- |

- [Yagisan's Better Stellaris](#yagisans-better-stellaris)
  - [Required DLC.](#required-dlc)
  - [Jobs](#jobs)
    - [AI Empires](#ai-empires)
    - [Player Empires](#player-empires)
  - [Habitability](#habitability)
  - [Space Expansion](#space-expansion)
  - [Anomalies](#anomalies)
    - [Respawning](#respawning)
  - [Archaeological Sites](#archaeological-sites)
    - [Respawning](#respawning-1)
  - [Warfare](#warfare)
    - [Espionage](#espionage)
    - [War Exhaustion](#war-exhaustion)
  - [Space Combat](#space-combat)
  - [Ground Combat](#ground-combat)
    - [Relic Capture](#relic-capture)
    - [Generals](#generals)
    - [Defence Armies](#defence-armies)
    - [Assault Armies](#assault-armies)
    - [Occupation Armies](#occupation-armies)
    - [Event Armies](#event-armies)
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
  - [Starbase Types](#starbase-types)
    - [Shipyards](#shipyards)
    - [Anchorages](#anchorages)
    - [Trading Hubs](#trading-hubs)
    - [Fortress / Bastion Systems](#fortress--bastion-systems)
    - [Star Patrol Offices](#star-patrol-offices)
    - [Listening Posts](#listening-posts)
  - [Megastructures](#megastructures)
    - [Gateways](#gateways)

## Required DLC.

As the Project has grown, and begun to utilise more and more new systems, introduced with DLC, Paradox Policy requires that those feature remain behind a DLC gate. Where possible features that require DLC are gated to simply not run if you are missing that DLC.

- Distant Stars Story Pack
  - Anomalies - Will disable these if not available
- Federations Expansion
  - Anomalies - Will disable these if not available
- Nemesis Expansion
  - AI Espionage - General
- First Contact Story Pack
  - AI Espionage - Primitives
  - Starbase Types - Cloaking

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

In addition, I have reduced the habitability spawn odds down to 30% to make habitable worlds much more valuable. Finally I have adjusted moon spawning sizes to always be smaller than planets, and to have a smaller overall size. The smallest moons will be size 8, and the largest size 12, while the smallest planets are size 15, and the largest are size 25.

Finally, for the purposes of habitability, pops with a Relic world preference will consider an Ecumenopolis a primary planet, and vice versa.

## Space Expansion

In vanilla, the AI can jump multiple systems when building starbases. This can result in a lot of exclaves and the AI potentially being unable to defend or reinforce them. The AI has now been prevented from building exclaves outside of war.

| Space Expansion Related Defines | Vanilla | Modded |
| ------------------------------- | ------: | -----: |
| MAX_EXPANSION_DISTANCE          |       2 |      1 |
| MAX_EXPANSION_DISTANCE_SUBJECT  |       2 |      1 |

## Anomalies

In the base game, you eventually run out of anomalies, and your science ships become much less useful. By respawning anomalies scientists can continue to level up, and science ships can continue to be useful, throughout the game.

**These can respawn from the Base Game, Distant Stars Story Pack, and the Federations Expansion. Missing DLC will be skipped.**

### Respawning

Each year the game will now attempt to respawn anomalies, provided their spawn conditions are met. These can respawn anywhere in the galaxy, in both player and AI controlled space.

The respawn system will attempt to respawn all Vanilla anomalies, and if you own the respective DLC, All Distant Stars Story Pack and Federations anomalies.

Each attempt at respawning an anomaly has an 85% chance of success.

The specific spawn rates are:

- Every year, try to respawn 1 anomaly.
- Every second year, try to respawn 4 anomalies.
- Every fifth year, try to respawn 10 anomalies.

## Archaeological Sites

In the base game, completed archaeological sites remain on the map. This causes accessibility issue when there are multiple archaeological sites in the same system. Now, 1 year after any site is fully excavated, the archaeological site will be removed.

In the base game, you eventually run out of archaeological sites, and your science ships become much less useful. By respawning archaeological sites scientists can continue to level up, and science ships can continue to be useful, throughout the game.

**These can respawn from the Base Game, all DLC, and any mods that add archaeological sites.**

### Respawning

Every 5 years the game will now attempt to respawn archaeological sites, provided their spawn conditions are met. These can respawn anywhere in the galaxy, in both player and AI controlled space.

The respawn system will attempt to respawn all archaeological sites that indicate that they can exist multiple times. This includes DLC and mod added archaeological sites.

Each attempt at respawning an archaeological sites has an 85% chance of success.

The specific spawn rate is:

- Every fifth year, try to respawn 3 archaeological sites.

## Warfare

### Espionage

This system is underutilised in vanilla, and seems to have a few bugs still in it (The AI likes to re-assign envoys a bit too often). Only a few espionage options are in vanilla (most require the Nemesis DLC).

Espionage targeting has now been completely reworked. The new targeting system for the AI is:

- It will prioritise rivals, crisis, and neighbouring empires.
- It will spy on an overlord or subject when loyalty is negative.
- It will **not** spy on an overlord or subject when loyalty is high.
- It will deprioritise inferior or pathetic empires, if there are better options.
- It will prevent deployment if the maximum possible infiltration level is too low.
- It will aggressively prioritise empires at war with it.
- It will aggressively prioritise empires that have terrible relations with it.
- It will not deploy an envoy if it already has one located there. (This prevents the AI from shuffling its envoys and making them useless.)

In vanilla Stellaris, the AI does actually attempt some espionage, but it's very unfocused, and only does a limited selection of operations. These are, in order of highest priority, to lowest:

- Lure the Kaleidoscope
- Acquire Asset
- Steal Technology
- Gather Information

Lure the Kaleidoscope is its highest weighted pick, followed by Acquire Asset. Gather Information and Steal Technology are unfocused, and are basically wasted picks, if the AI picks them. It would happily steal technology from someone that is technologically inferior to it.

In Yagisan's Better Stellaris, I have refined targeting of operations, increased the number of available operation options, and set about weighting them from highest priority, to lowest, as follows:

- Consume Star / Crisis Beacon / Lure the Kaleidoscope
- Arm Privateers
- Imperium: Target Seditionists / Imperium: Weaken Imperial Authority / Imperium: - Spark Rebellion
- Sabotage Starbase / Acquire Asset*
- Steal Technology
- Smear Campaign
- Spark Diplomatic Incident / Extort Favors / Sleeper Cells
- Gather Information
- These operations do have additional conditions involved, such as being rivals, or at war, depending on which operations being used. Acquire Asset is automatically deprioritised when infiltration is at maximum level.

Acquire Asset has also been buffed. Now each asset also adds 0.1 infiltration speed. This results in more frequent use the various operations.

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
- Reclaim allies occupied planets.
- Prioritise attacks along conquered border.
- Prioritise attacks along our border.
- Prioritise attacks along allies border.
- Defend our own invaded territory.
- Defend our allies invaded territory.
- Defend our own territory.
- Defend our allies territory.
- Defend conquered territory.
- Prioritise attacks in neutral space.

When selecting targets, the new priority order is

- Enemy Fleets
- Enemy Starbases
- Systems with Planets
- All other systems.

The logic being fleets are what win wars, so they need to go first, and starbases make fleets, so they should go next.

Space Combat AI is a mixture of decision weights (I can tweak those) and hardcoded AI choices (I can't change those), and at the time of writing, I have not completely worked out the interactions between the two. I have observed that the "Defense" goal makes the AI defend, even if no attacks are incoming - which is not ideal.

## Ground Combat

Ground combat in Stellaris is rather lacking by default. In theory it should be a vital part of conquest, but instead feels inconsequential. These changes seek to make ground combat a more strategic, and useful part of the game.

### Relic Capture

In vanilla Stellaris, if you have the Ancient Relics DLC there is a chance that, if you have a specific civic, when you conquer the capital world of an empire, you will take a random relic from them. Unfortunately, this event is actually broken and does not work. As a result, when empires are conquered, the relics they have are lost from the game.

Now, in Yagisan's Better Stellaris, if a playable empire (including the AI) successfully conquers the capital world of an empire, they will capture all relics that empire has. Notably this does not include Fallen Empires, Awakened Empires, or the Crisis. Relics can still be lost if an empire is conquered by one of these empires. Yes, this does mean the AI can loot your relics.

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
| Army Damage       |          3.0 |         5.00 |
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
| Army Damage           |     2.0 |   5.00 |
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
| Army Damage       |        5.0 |       8.00 |
| Morale Damage     |        2.0 |       2.00 |
| Collateral Damage |        5.0 |       4.00 |
| War Exhaustion    |        4.0 |       4.00 |
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

| Giant Undead Army | Vanilla | Modded |
| ----------------- | ------: | -----: |
| Army Damage       |     3.0 |   5.00 |
| Morale Damage     |     3.0 |   3.00 |
| Collateral Damage |     3.5 |    3.5 |
| War Exhaustion    |     0.5 |    0.5 |
| Health            |     7.0 |   7.00 |
| Morale            |  Immune | Immune |

| Mercenary Army    |  Vanilla |   Modded |
| ----------------- | -------: | -------: |
| Army Damage       |      1.1 |     2.10 |
| Morale Damage     |      1.0 |     1.00 |
| Collateral Damage |      2.5 |      2.5 |
| War Exhaustion    |      0.5 |      0.5 |
| Health            |      1.0 |      1.0 |
| Morale            |      0.5 |      0.5 |
| Upkeep            | 2 Energy | 2 Energy |

| Mechanized Mercenary Army |  Vanilla |   Modded |
| ------------------------- | -------: | -------: |
| Army Damage               |      2.2 |     3.00 |
| Morale Damage             |      1.0 |     1.00 |
| Collateral Damage         |      3.0 |      3.0 |
| War Exhaustion            |      0.5 |      0.5 |
| Health                    |      1.8 |      1.8 |
| Morale                    |      1.0 |      1.0 |
| Upkeep                    | 5 Energy | 5 Energy |

| Crystal Kraken | Vanilla | Modded |
| -------------- | ------: | -----: |
| Army Damage    |    35.0 |   30.0 |
| Morale Damage  |    50.0 |   50.0 |
| Health         |    55.0 |   75.0 |
| Morale         |  Immune | Immune |

| Subterranean Invasion Defense Force | Vanilla | Modded |
| ----------------------------------- | ------: | -----: |
| Army Damage                         |     0.8 |    1.0 |
| Morale Damage                       |         |    0.5 |
| Health                              |     1.0 |    1.0 |
| Morale                              |     1.0 |    1.0 |

| New World Order Defense Force |  Vanilla |   Modded |
| ----------------------------- | -------: | -------: |
| Army Damage                   |      0.1 |      0.1 |
| Morale Damage                 |      0.1 |      0.1 |
| Health                        |     20.0 |     20.0 |
| Morale                        |      6.0 |      6.0 |
| Upkeep                        | 1 Energy | 1 Energy |

| New World Order Offensive Army |  Vanilla |   Modded |
| ------------------------------ | -------: | -------: |
| Army Damage                    |      0.1 |      0.1 |
| Morale Damage                  |      0.1 |      0.1 |
| Health                         |     20.0 |     20.0 |
| Morale                         |      6.0 |      6.0 |
| Upkeep                         | 1 Energy | 1 Energy |

## Starbase Buildings

With the addition of Orbital Rings, it's now possible to have more starbase buildings in each system. I have created several new buildings, and selectively edited a few vanilla buildings to provide the player with more options.

### Changed Starbase Buildings

#### Crew Quarters / Crew Gestation Chambers / Service Umbilicals

| Cost | Time | Upkeep | Orbital Ring |
| ---- | ---- | ------ | ------------ |
| 25   | 180  | 0      | **Yes**      |

**Changes**

- Reduced building cost
- No upkeep
- Now provides 2 Naval capacity.

#### Resource Silo

| Cost | Time | Upkeep | Orbital Ring |
| ---- | ---- | ------ | ------------ |
| 50   | 180  | 0      | **No**       |

**Changes**

- No longer able to build on Orbital Rings
- AI will no longer try building this in systems with colonies.
- Starts with 5000 storage. Can add 5000 more via tech.

#### Nebula Refinery

| Cost | Time | Upkeep | Orbital Ring |
| ---- | ---- | ------ | ------------ |
| 200  | 360  | 3      | **Yes**      |

**Changes**

- Will now also produce 1 Volatile Mote with Mote Stabilization technology.
- Will now also produce 1 Rare Crystal with Rare Crystal Mining technology.

#### Listening Post

| Cost | Time | Upkeep | Orbital Ring |
| ---- | ---- | ------ | ------------ |
| 100  | 360  | 2      | **No**       |

**Changes**

- +3 Sensor Range
- +6 Hyperlane detection Range
- +2 Trade Protection Range
- +1 Trade Protection

#### Offworld Trading Company

| Cost | Time | Upkeep | Orbital Ring |
| ---- | ---- | ------ | ------------ |
| 100  | 360  | 0      | **No**       |

**Changes**

- +10% Trade for all colonies in the system.
- AI can now build at chokepoints

#### Hyperlane Registrar

| Cost | Time | Upkeep | Orbital Ring |
| ---- | ---- | ------ | ------------ |
| 100  | 180  | 2      | **No**       |

**Changes**

- +2 Trade Collection Range
- AI can now build outside of chokepoints

#### Deep Space Black Site

| Cost | Time | Upkeep | Orbital Ring |
| ---- | ---- | ------ | ------------ |
| 100  | 360  | 2      | **No**       |

**Changes**

- -10% Crime for all colonies in the system.
- AI will no longer try building this in systems without colonies.

#### Curator Think Tank

| Cost | Time | Upkeep | Orbital Ring |
| ---- | ---- | ------ | ------------ |
| 100  | 360  | 2      | **No**       |

**Changes**

- +10 Research

#### Trader Proxy Office

| Cost | Time | Upkeep | Orbital Ring |
| ---- | ---- | ------ | ------------ |
| 100  | 360  | 0      | **No**       |

**Changes**

- +10 Trade to the station with Unchained Knowledge resolution level 3 or above

#### Command Center

| Cost | Time | Upkeep | Orbital Ring |
| ---- | ---- | ------ | ------------ |
| 500  | 360  | 5      | **Yes**      |

**Changes**

- +1 Starbase Capacity

#### Transit Hub

| Cost | Time | Upkeep | Orbital Ring |
| ---- | ---- | ------ | ------------ |
| 100  | 180  | 3      | **No**       |

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

**Changes**

- AI can now build these on Orbital Rings.

### New Starbase Buildings

#### Star Patrol Office

| Cost | Time | Upkeep | Orbital Ring |
| ---- | ---- | ------ | ------------ |
| 200  | 360  | 3      | **No**       |

**Requirements**

- Max 1 per system.
- Starbase must have at least 1 Hanger Bay
- Not a gestalt empire.

**Effects**

- Adds 5 trade protection for the Star Patrol office, and 5 trade protection for each hanger in the starbase. (Maximum of 35 trade protection)
- Adds 2 trade protection range for the Star Patrol office, and 1 trade protection range for each hanger in the starbase. (Maximum of 8 trade protection range)

**Description**

Non-gestalt empires can build a Star Patrol Office on any starbase with a hanger. This will extend both the range, and value of its anti-piracy protection. These starbases, when not in a system with colonies, or next to another empire will be known as Star Patrol Base.

## Starbase Types

Existing starbase types have been modified to build several previously player only buildings for the AI. Additional starbase types have been created for specific roles. Starbase placement logic has been changed to account for political stances between empires.

Once critical buildings have been built on a starbase, building slots permitting, they will attempt to prioritise special buildings such as the Curator Think Tank, Deep Space Black Site, or Black Hole Observatory, before choosing generic useful buildings.

### Shipyards

Shipyards will be the first priority if an empire has no other ship building capacity. They will prioritise a Fleet Academy / Battle Simulators, Crew Quarters / Crew Gestation Chambers / Service Umbilicals, Titan Yards, Colossus Yards, and Dragon Hatcheries.

### Anchorages

These are now a much more economically focused starbase. They will prioritise a Naval Logistics Office, Deep Space Black Site, Transit Hub, and Command Centre. Once all priority buildings are built they will attempt to exploit all special buildings before falling back to generic useful buildings.

### Trading Hubs

These will try to place themselves over capital planets, and avoid being near other trade hubs, or locations cut off from the empire. They will prioritise an Offworld Trading Company, Hyperlane Registrar, Deep Space Black Site, and Transit Hub. Once all priority buildings are built they will attempt to exploit all special buildings before falling back to generic useful buildings.

### Fortress / Bastion Systems

They will try to build themselves in chokepoints near threats. Threat logic is complex but basically, if they don't like you, or want your territory, they are a threat. They will prioritise an Offspring Outlook, Communications Jammer, and Command Centre. Once all priority buildings are built they will attempt to exploit all special buildings before falling back to generic defence buildings.

### Star Patrol Offices

They will try to build themselves in chokepoints, on a trade route, and avoid building near other Star Patrol Offices. Being an anti-piracy base, they will build exclusively hanger bays, and they will avoid building near threats, and will not build in systems with Colonies. They will prioritise a Star Patrol Office, an Offspring Outlook, Communications Jammer, and Command Centre. Once all priority buildings are built they will attempt to exploit all special buildings before falling back to generic defence buildings.

### Listening Posts

They will build themselves next to neighbouring empires, prioritising hostile one, and avoid building near other Listening Posts. They will prioritise a Listening Post, an Offspring Outlook, Communications Jammer, Command Centre and Target Uplink Computer. Once all priority buildings are built they will attempt to exploit all special buildings before falling back to generic defence buildings.

## Megastructures

### Gateways

Once the AI learns to build gateways, they become very indiscriminate about it. This results in both gateway spam, and lag, as the AI needs to path find though many additional gateways.

To lesson the spam, but still make gateways useful, we now limit AI gateways to 1 per sector. This limit will apply even if the gateway is disabled or ruined. If possible the AI will prefer to build the gateway over its sector capital, while respecting vanilla restriction (no gateway in an adjacent sector, starbase is the required level)

It also attempts to show gateways on the map.
