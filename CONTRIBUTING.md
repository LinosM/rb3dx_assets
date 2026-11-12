# Resouces and documentation

We have a bit of documentation on Google Docs. Keep in mind that things are evolving rapidly.
* [[Porting basics]](https://docs.google.com/document/d/16hRGfKVZlf0QR6v0r4YlS0LUob0jrQWG7t24oGc2jSc/edit?usp=sharing) - Setting up required software, weight transferring, and prefab creation.
* [[Rigging physics]](https://docs.google.com/document/d/1yyMzfm5VM13iQwq6ZiZR2_jIbWkCW1JVwiTnyjYKz1E) - Rigging physics for hair, tails, and body accessories.
* [[Texture work]](https://docs.google.com/document/d/18GR9iqTFdVj28rMl1XkU-VqxaMVPuqQHd4ti61T9LRc) - Making the most out of your textures, replicating materials, and optimizations.

# Contributing Guidelines
Anyone is free to add models, but in order to add your character to this repo, please make sure that it meets the following requirements:

## Weights and rig
* Every single polygon in your model should have weights assigned in at least one vertex group (don't ship exploding vertices).
* All basic rotations (fingers, arms, legs, neck, and spine) work properly, with no visible "candy-wrapping" around bones.
* The bones on the face are weight painted accordingly (don't ship models with lipsync killed-off if the geometry allows for it).

## Physics
Physics are not required, but if you do include them:
* Give the affected areas natural resting poses (don't ship hair going straight down into the body, nor tails going straight up, for example).
* Give the affected areas proper fallback weights for those venue shots without physics enabled (this can be a combination of head, neck, and spine weights for really long hair, or just a max influence pelvis weight for a tail).
* Make sure the affected areas don't jump around too abruptly with every physics reset (every camera shot, for example).

## Textures and optimization
* **DO NOT** use `2048px` or higher resolution textures under any circumstance.
* **DO NOT** leave unused textures in your Milo.
* **DO NOT** leave duplicate textures in any of your materials.
* Any flat colored texture you're required to use should have a `4x4` resolution.
* The maximum allowed poly count for any prefab in this repo is `60,000`.
* The final, uncompressed file size of your Milo should be a maximum of `5MB` for both platforms.

## Other
* **DO NOT** intentionally obfuscate your submissions by breaking the milo file.
	* This applies to stuff like messing up the EOF bits.
	* Doing this prevents maintainers from properly reviewing your stuff as well as other contribuitors from learning autonomously by using your work as reference.

## Preferred naming convention
* BandCharDesc
	* prefab_`[SOURCE_MATERIAL]`_`[CHARACTER_NAME]`
	* **Example**: `prefab_fn_fennix`

* Earrings
	* `[SOURCE_MATERIAL]`\_`[CHARACTER_NAME]`.milo_`[PLATFORM]`
	* **Example**:
		* `fn_fennix.milo_ps3`
		* `fn_fennix.milo_xbox`

## Preparing for shipping
* **DO NOT** use any uppercase in the filenames, especially in `.milo` files. Your file will either not load or cause issues (thumbnails not working).
* Test your characters on Xbox 360 (or Xenia) and PS3 (or RPCS3) before submitting.
* Add your characters to the [[locale file]](dx/locale/dx_locale_updates_chars.dta).
	* There's an approx. limit of around 23 characters. If you go over, it will get cut off.
* Add an image for your character so people can easily see who your character is when scrolling the list.
	* It's recommended to use Blender so you can pose your characters. [[Here's a template]](https://drive.google.com/file/d/1XfmRamPMQ-OyWE1ttEtZr_lLBBcXIqI9/view?usp=sharing) for that.
	* To use in-game images, use [[Nautilus]](https://github.com/trojannemo/Nautilus) to extract the image via Save File Image Editor.
	* You can use external images, just make sure they are properly aligned to the [[character select screen template (links to a message on the MiloHax Discord)]](https://discord.com/channels/961352072140324924/1392297525045891183/1526150841072095384) .
	* The game's thumbnails are `256`x`512`.
	* Convert images using [[this setup by Linos (links to a message on the MiloHax Discord)]](https://discord.com/channels/961352072140324924/1392297525045891183/1504960254658478150)

## Good practices
* Only create a PR when you think your prefab is ready for review, or mark your PR as _draft_ if you intend to make changes to it.
* **DO NOT** submit untested changes to your PR, it reflects poorly on your submission and wastes the time of the volunteering maintainers.
* **DO** try to communicate with others if you have issues or suggestions, whether it's through here or through the [[MiloHax Discord]](https://discord.gg/milohax).
* We recommend still uploading your files to [[GameBanana]](https://gamebanana.com/mods/games/18558) for visibility.