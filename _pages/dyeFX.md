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

[//]: # --- TECH STRUCTURE --- # :[\\]
{% capture block_content %}
# PROCESS FOR DYEING

### CODE
Each cosmetic on the player determines whether it should dye by checking if it has Niagara components with a tag marking it as dyeable.
When the player applies a dye to the ***Emissive*** dye channel of their cosmetics, we apply that dye gradient texture to our VFX. 

### NIAGARA SYSTEMS
Each dyeable Niagara system has an exposed user parameter that keeps track of the applied dye texture set in code. Each emmitter in that
system should have their renderer set up with a material parameter binding, linking the material texture parameter with the Niagara
texture parameter. We don't want a color gradient texture if no dye is applied by the player, so the default dye texture is fully transparent.

### MATERIALS
The Niagara emitter materials interpolate between a particle's original color and the dye texture colors we want to sample. If there is no
dye applied, we simply maintain the original particle color. Particle materials each have custom logic for sampling the dye gradient and
applying new color to the particle.
{% endcapture %}

{% capture block_video %}
{{path}}DyeRevenantKyros.mp4
{% endcapture %}

{% capture block_video2 %}
{{path}}DyeHeroicKyros.mp4
{% endcapture %}

{% include block.html content=block_content video=block_video video2=block_video2 %}

{% include spacer.html amount="2rem" %}