# Resources and Documentation
We have a bit of documentation on Google Docs. Keep in mind that things are evolving rapidly.
* [[Porting Basics]](https://docs.google.com/document/d/16hRGfKVZlf0QR6v0r4YlS0LUob0jrQWG7t24oGc2jSc/edit?usp=sharing) - Setting up required software, weight transferring, and prefab creation.
* [[Rigging Physics]](https://docs.google.com/document/d/1yyMzfm5VM13iQwq6ZiZR2_jIbWkCW1JVwiTnyjYKz1E) - Rigging physics for hair, tails, and body accessories.
* [[Texture Work]](https://docs.google.com/document/d/18GR9iqTFdVj28rMl1XkU-VqxaMVPuqQHd4ti61T9LRc) - Making the most out of your textures, replicating materials, and optimizations.

If you want to contribute to the documentation itself, either send an edit suggestion/comment or use the [[MiloHax Discord]](https://discord.gg/milohax). Every bit helps!

# Contributing Guidelines
Anyone is free to submit models! However, we have some standards in place to avoid problems. This is a 2010 game made for 2005 consoles, after all!

## Weights and Rig
* Every single polygon in your model should have weights assigned in at least one vertex group. This is to avoid exploding vertices.
* All basic rotations (fingers, arms, legs, neck, and spine) should work properly. Avoid unnatural flexing as much as possible.
* The bones on the face are weight painted accordingly. If the model has geometry for lipsync, use it!

## Physics
Physics are **not** required, but if you do include them, make sure:
* The physics bones have natural resting poses. Don't ship hair going straight down into the body, nor tails going straight up, for example.
* Any part with physics has fallback weights. This is because some camera angles disable physics. You can use a combination of head, neck, and spine weights for really long hair, or just a max influence pelvis weight for a tail.
* Any physics bits don't jump too abruptly when physics reset (usually when cam angles switch).

## Textures and Optimization
* **DO NOT** use `2048px` or higher resolution textures under any circumstance.
* **DO NOT** leave unused textures in your Milo.
* **DO NOT** leave duplicate textures in any of your materials.
* Any flat colored texture you're required to use should have a `4x4` resolution.
* The maximum allowed poly count for any prefab in this repo is `60,000`. For reference, average Rock Band 3 is around `25,000` to `30,000` polys.
* The final, uncompressed file size of your Milo should be a maximum of `5MB` for both platforms.

## Other
* **DO NOT** obfuscate your submissions by breaking the `.milo` file.
	* We can't review your stuff if we can't open it!
   	* This also prevents anyone else from learning from your models.
  	* This applies to stuff like messing up the EOF bits.

## Preferred Naming Convention
* `BandCharDesc` file (located in `_ark/char/custom_prefabs`)
	* prefab_`[SOURCE]`_`[CHARACTER_NAME]`
	* **Example**: `prefab_fn_fennix`

* `earrings` file (located in `_ark/char/main/earrings/[gender]/gen`)
	* `[SOURCE]`\_`[CHARACTER_NAME]`.milo_`[PLATFORM]`
	* **Example**:
		* `fn_fennix.milo_ps3`
		* `fn_fennix.milo_xbox`

* Portrait file (located in `_ark/char/prefab/images/gen`)
	* prefab_`[SOURCE]`\_`[CHARACTER_NAME]`\_keep.bmp\_`[PLATFORM]`
	* **Example**:
		* `prefab_fn_fennix_keep.bmp_ps3`
		* `prefab_fn_fennix_keep.bmp_xbox`

## Pre-Shipping Checklist
- [ ] Make sure there's no uppercase characters in the filenames, especially in `.milo` files. Your file will either not load or have other issues!
- [ ] Test your characters on Xbox 360 (or Xenia) and PS3 (or RPCS3) before submitting.
- [ ] Add your characters to the [[locale file]](dx/locale/dx_locale_updates_chars.dta).
	* There's an approx. limit of around 23 characters. If you go over, it will get cut off.
- [ ] Add an image for your character so people can easily see who your character is when scrolling the list.
	* It's recommended to use Blender so you can freely pose your character for the portrait. [[Here's a template]](https://drive.google.com/file/d/1XfmRamPMQ-OyWE1ttEtZr_lLBBcXIqI9/view?usp=sharing) for that.
	* To use in-game images, use [[Nautilus]](https://github.com/trojannemo/Nautilus) to extract the image via Save File Image Editor.
	* You can use external images, just make sure they are properly aligned to the [[character select screen template (links to a message on the MiloHax Discord)]](https://discord.com/channels/961352072140324924/1392297525045891183/1526150841072095384) .
	* The game's thumbnails are `256`x`512`.
	* Convert images using [[this setup by Linos (links to a message on the MiloHax Discord)]](https://discord.com/channels/961352072140324924/1392297525045891183/1504960254658478150).
   	* Do *NOT* add mipmaps to your portraits. 

## Good practices
* Only create pull requests when your character is ready for review! Don't use pull requests for version control. This just clutters things up.
* **DO NOT** submit untested changes in your pull request! This wastes volunteers' time.
* **DO** try to communicate with others if you have issues or suggestions, whether it's through here or through the [[MiloHax Discord]](https://discord.gg/milohax).
* We recommend still uploading your files to [[GameBanana]](https://gamebanana.com/mods/games/18558) for visibility.
