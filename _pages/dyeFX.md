---
permalink: /dyeableVFX/
layout: default

title: Dyeable VFX
description: Welcome to the dyeable vfx page.
---
{% assign path = "/assets/images/projects/DyeVFX/" %}

{% include spacer.html amount="1.5rem" %}

# Dyeable Visual Effects

---

<div class="content flex flex-column">
	<video class="border border-radius-lg" autoplay muted controls loop>
		<source src="{{path}}dyevfx_4k.mp4" type="video/mp4">
	</video>      
</div>

{% include spacer.html amount="1.5rem" %}

In Wayfinder, one of the primary methods of player customization and self expression is through the dyes system.
While exploring, players may collect dye swatches as inventory items. Each swatch is a color gradient that can
be applied to a character's cosmetics. I was tasked with expanding this system beyond dying meshes, to allow for
dyeable visual effects too. 

It was imperative that dyeable VFX be seamlessly integrated into the existing dyes system. Not only are our
Niagara particles affected by the same gradient textures as dyeing a mesh, but during gameplay they are applied
via the same menus as well. This system applies to both weapons and character-attached VFX.

--- 

[//]: # --- GAMEPLAY --- # :[\\]

{% capture block_content %}
### USE IN GAME

Eldren caches spawn occasionally across the land of the Crucible. They are timed challenges for the player with
two main components: a key to collect, and a cache to place it in. If a player can connect both within the allotted
time window, they will be granted some loot for their efforts.

The key is a large crystalline hexagonal prism with emissives and VFX to draw the player in. Once obtained, a miniaturized
version will float behind the player as they transport it to the cache. The cache is a hub for the key, with a hexagonal
channel to place it in. The key rotates and slides into place, alighting emissive lines on the cache. Then, the whole cache 
base glows and the VFX grow more intense as the cache has been fully activated, ready to reward the player.
{% endcapture %}

{% capture block_video %}
{{path}}DyeRevenantKyros.mp4
{% endcapture %}

{% capture block_video2 %}
{{path}}DyeHeroicKyros.mp4
{% endcapture %}

{% include block.html content=block_content video=block_video video2=block_video2 %}

{% include spacer.html amount="1.5rem" %}