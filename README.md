# BoxedDataPack
Advancement Datapack for Boxed Addon

Download the latest `BoxedDataPack.zip` from the [Releases page](../../releases/latest) and place it in your world's `datapacks/` folder.

## Minecraft version

This pack is for **Minecraft 26.3** (data pack format 121). It will not load on older versions: the game changed how advancements, recipes and tags are written, and the folder names, several times since the pack was first made for 1.20.

The pack adds:

* 347 advancements in eleven tabs of their own (building, caving, collection, combat, exploration, forestry, livestock, nether structures, ocean, redstone and villages),
* 68 more in the game's own tabs,
* its own versions of 98 of the game's advancements, and
* 240 recipes, most of which replace the game's own.

## What changed in the move to 26.3

Every file was converted to the new format and kept its name, so anything that refers to an advancement by name still works. A few things could not be carried over as they were:

* **Raids.** The game no longer has the "voluntary exile" trigger, so `village/start_raid` and `village/dimension_raid` now use the game's own test: killing a raider that wears the ominous banner.
* **Banner patterns.** `nether_structures/piglin_banner` no longer checks for the snout pattern, only that the item is a banner. `village/ominous_banner` still checks the pattern, rewritten for the way banners are saved now; this has not been tried in game.
* **Explorer maps.** `exploration/buy_map` no longer checks which marker the map has.
* **Icons.** Icons that showed a player head, a map colour or a damaged item now show the plain item.
* **Recipes that never existed.** Sixteen wool recipe advancements named recipes the pack never had. Those references are gone, because the game now refuses to start if a recipe is missing.
* **New tags.** `bentobox:dyeable_glasses` was named by sixteen recipes but was missing, so those recipes did not work before. It is there now. `bentobox:music_discs` and `bentobox:chest_boats` take the place of things the game removed, and there are two damage type tags that advancements named but the pack lacked.

The pack's own versions of the game's advancements are the ones written for 1.20. Where the game has since added to an advancement, for example new biomes or mobs, the pack's version does not have the addition.

## Checking the pack

The workflow checks the files against JSON schemas. That catches mistakes in shape, but only a server can say whether the pack loads: start a 26.3 server with the pack in `world/datapacks` and look for `Errors in element` in the log. A pack with a mistake in a recipe stops the server from starting.
