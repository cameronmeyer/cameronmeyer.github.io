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
### PROCESS FOR DYEING

- since the system relies on component tags to work, the niagara systems are expected to be contained inside a BP. below, we are retreiving a spawned component on the player and checking its components
- on 'ApplyItemEffects' (I think this is basically when something on your character updates)
	- if the item that updated is a weapon (identified by a 'root dye slot name')	
		- get all niagara components
		- if niagara component exists, has a vfx dye tag, and a weapon dye tag, keep track of component for dyeing
	- else
		- get all niagara components
		- if niagara component exists, has a vfx dye tag, and a ARMOR dye tag, keep track of component for dyeing (mutually exclusive with weapon)
- on 'ApplyDyesToNiagaraComponent'
	- check that user actually changed the appropriate dye channel (the emissive channel, also affects meshes)
	- load the dye texture
	- set niagara texture variable to the dye texture
- MF_VFX_Dye values:
	- original color (lerp between this and new colors based on other passed values)
	- color strength
	- gradient offset strength, offset bias, and mask
	- gradient clamp min/max
	- dye parameter texture object
- MF_VFX_Dye logic:
	- we lerp between the original color and the dye texture (with offsets, clamps, etc. applied to sample the curve as desired)
	- the ALPHA for this lerp multiplies the alpha of the dye texture with our dye mask
	- a dye texture is ALWAYS applied with our material binding, and the default dye texture is blank/transparent, so by default the MF will return the original color from the lerp 
- VFX materials can have whatever custom logic they want for vfx dyes
	- materials simply use the MF (above), setting the floats and passing in the original undyed state
	- output gets plugged into material emissive
- each dyeable niagara system has a 'DyeTex' exposed user parameter
	- each EMITTER's renderer in the niagara system must have a material parameter binding set up
	- binds the material parameter (DyeParam) to the niagara variable (DyeTex)

{% endcapture %}

{% capture block_video %}
{{path}}DyeRevenantKyros.mp4
{% endcapture %}

{% capture block_video2 %}
{{path}}DyeHeroicKyros.mp4
{% endcapture %}

{% include block.html content=block_content video=block_video video2=block_video2 %}

{% include spacer.html amount="1.5rem" %}