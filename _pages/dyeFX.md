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
<div class="content flex flex-column">
	<video class="border border-radius-lg" autoplay muted controls loop>
		<source src="{{path}}DyeRevenantKyros.mp4" type="video/mp4">
	</video>
	<video class="border border-radius-lg mt-6" autoplay muted controls loop>
		<source src="{{path}}DyeHeroicKyros.mp4" type="video/mp4">
	</video>    
</div>

{% include spacer.html amount="1.5rem" %}

[//]: # --- TECH STRUCTURE --- # :[\\]
{% capture block_content %}
## PROCESS FOR DYEING

### CODE
When an item equipped on the player is updated, it checks whether it should dye. First, it determines whether it is a weapon or cosmetic,
as each should not share the same applied dyes. Then, it gathers all Niagara components on the item, and if those components have the
appropriate tags applied, we will mark the component as dyeable.

When actually applying dyes to the Niagara component, we check that the user actually changed the appropriate dye channel. Specifically,
when the 'Emissive' dye channel is set, that is the dye texture used for VFX as well. We then load the dye texture into memory and set 
a Niagara texture variable to reference this dye texture.

### NIAGARA SYSTEMS
Each dyeable Niagara system has an exposed user parameter that keeps track of the applied dye texture. Each emmitter in that system
should have their renderer set up with a material parameter binding. This links the dye texture parameter in the material with the 
dye texture parameter in the Niagara system. 

A dye texture is **always** applied to our dyable Niagara systems as a result, so we set the default texture to be fully transparent.
This way, there is no color gradient for the material to sample if no dye is applied.

### MATERIALS
The Niagara emitter materials contain a material function `MF_VFX_Dye`. This function interpolates between the
particle's original color and the dye texture color (after it has been affected by offsets, clamps, etc. that help sample our gradient
texture as desired). The alpha, or the interpolation value, for the lerp is obtained by multiplying the alpha of the dye texture with a
dye mask that ensures we are dying only the correct areas on our particle texture. Since our default dye texture is fully transparent,
when no dye is applied the lerp's interpolation value is 0, and the material function will simply return the original particle color.

Particle materials may use whatever custom logic they want to define how dyes should sample the gradient and map to the particle.
As long as the material passes that into the `MF_VFX_Dye` material function, we can plug that node's output into the material's
emissive channel. 
{% endcapture %}

{% include block.html content=block_content %}

{% include spacer.html amount="1.5rem" %}