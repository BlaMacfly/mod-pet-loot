# Module: Pet Loot (Bananas)

<p align="center">
  <img src="icon.png" alt="Pet Loot (Bananas)" width="246" height="246">
</p>

This is a module for [AzerothCore](https://www.azerothcore.org).

It allows the vanity pet **Bananas** (ID 23234) to act as an immersive auto-loot assistant for the player.

## Features
- **Visual Movement**: The pet physically runs to the location of the killed creature before looting.
- **Looting Animation**: Upon reaching the corpse, the pet plays a "Loot" animation (emote) for immersion.
- **Auto-Loot**: Items and gold are automatically handled using AzerothCore native loot systems, including inventory validation, quest requirements, unique item checks, group loot rules, and gold sharing.
- **Distance Check**: The pet only loots if the player is within a configurable distance from the corpse (default: 50 yards).
- **Stability**: Uses `Player::StoreLootItem` to ensure compatibility with unique items, bag space, and quest requirements.
- **Group Loot Support**: Fully respects AzerothCore group loot rules (Free For All, Group Loot, Need Before Greed, Master Loot, Round-Robin). The pet automatically triggers the appropriate loot system exactly once, shares gold correctly between nearby group members, and leaves active loot rolls and master-loot distributions fully managed by the core.
- **Safe Group Roll Handling**: Prevents duplicate Need/Greed or Master Loot rolls when players manually open the corpse after the pet has already initialized the loot.
- **Configurable**: You can enable/disable the module, change the Pet ID, and adjust the looting radius via the config file.

## Requirements
- AzerothCore (latest version)
- A player with the pet **Bananas** (Entry 23234) summoned.

## Installation
1. Place the `mod-pet-loot` directory into your `modules/` folder.
2. Recompile your AzerothCore project.
3. Apply the SQL file provided in the `sql/` directory (if not done automatically).
4. Copy `conf/mod_pet_loot.conf.dist` to `conf/mod_pet_loot.conf`.
5. Enjoy!

## Configuration
- `PetLoot.Enable`: Enable/Disable the module.
- `PetLoot.PetId`: The NPC ID of the looting pet (default: 23234).
- `PetLoot.Radius`: Maximum distance for looting (default: 50.0 yards).

## License
Released under the [GNU AGPL v3 license](LICENSE).
