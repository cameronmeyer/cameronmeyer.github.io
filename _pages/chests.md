---
permalink: /chests/
layout: default

title: Chests
description: Welcome to the chests page.
---
{% assign path = "/assets/images/projects/Chests/" %}

{% include spacer.html amount="1.5rem" %}

# Treasure Chests

---

<div class="content flex flex-column">
	<video class="border border-radius-lg" autoplay muted controls loop>
		<source src="{{path}}EldrenChest.mp4" type="video/mp4">
	</video>      
</div>

{% include spacer.html amount="1.5rem" %}

In *Wayfinder* players will encounter a variety of treasure chests during their journey. I was fortunately tasked with the
implementation and polish of several of these chests. While their visuals may vary greatly, all chests generally required 
custom setups that included the following:
- Animations, sounds, and visual effects all synced up with timelines
- Animated material properties synced with other effects
- Blueprint logic to execute all component parts, handle state changes, and award loot

---

[//]: # --- BOSS CHEST --- # :[\\]

{% capture block_content %}
### BOSS AND MYTHIC CHESTS

These chests are awarded for defeating bosses and completing mythic-level hunts. 
As the largest and possibly the most difficult chest to obtain in *Wayfinder*, mythic chests
appear the most threatening, as though they hold a great treasure within.

Here, each of the idle-state visual effects needed to be disabled at different times. The smoke emitting from
the dragon's eyes is disabled in sync with the purple material emissive on the eyes and mouth/chest interior.
{% endcapture %}

{% capture block_video %}
{{path}}BossChest.mp4
{% endcapture %}

{% include block.html content=block_content video=block_video %}

{% include spacer.html amount="1.5rem" %}





[//]: # --- ELDREN CHEST --- # :[\\]

{% capture block_content %}
### ELDREN CHESTS

Eldren chests can be found in the Crucible; the gorge-like world region. A technology of an advanced race of beings, these chests
strike a balance between mysticism and futurism in their design. 

Within the central orb of the chest, I animated a multitude of material properties to give the impression of an energy source
surging with power and dissipating as it presents its reward to the player.
{% endcapture %}

{% capture block_video %}
{{path}}GorgeChest.mp4
{% endcapture %}

{% include block.html content=block_content video=block_video video_first=true %}

{% include spacer.html amount="1.5rem" %}





[//]: # --- RUINS CHEST --- # :[\\]

{% capture block_content %}
### RUINS CHESTS

The Ruins are *Wayfinder*'s first 'Lost Zone' region, a system of dungeons for players to explore.
As such, the chests found within these halls preserve ancient treasures from another time. 

With its complex emissive panning and moving components, the Ruins chest resembles fine craftsmanship
lost to time. Each component is controlled separately and disabled at the right moment when the chest
is unlocked. 
{% endcapture %}

{% capture block_video %}
{{path}}RuinsChest.mp4
{% endcapture %}

{% include block.html content=block_content video=block_video %}

{% include spacer.html amount="0.5rem" %}





[//]: # --- MINES CHEST --- # :[\\]

{% capture block_content %}
### MINES CHESTS

In *Wayfinder*, godsblood is a key power source extracted from underground veins.
That fluid flows through this gritty, forged chest.

As the chest opens, the godsblood drains from the chest. The liquid level in pipes on either side
goes down, and the chest loses its lustrous green emissive once the player has looted from it.
{% endcapture %}

{% capture block_video %}
{{path}}MinesChest.mp4
{% endcapture %}

{% include block.html content=block_content video=block_video video_first=true %}

{% include spacer.html amount="0.5rem" %}





[//]: # --- REAVERWOODS CHEST --- # :[\\]

{% capture block_content %}
### REAVERWOODS CHESTS

Chests from the Reaverwoods have a handcrafted feel to them, seemingly modeled after creatures
killed for survival out in the wilderness. These chests bring a bit of warmth to a harsh, frozen
region of the world. 

Once opened, the primal essence of the chest dissipates as the antlers on either side detatch
and fall, and the emissives of the face and chest interior fade.
{% endcapture %}

{% capture block_video %}
{{path}}ReaverwoodsChest.mp4
{% endcapture %}

{% include block.html content=block_content video=block_video %}

{% include spacer.html amount="0.5rem" %}

---

<div class="content flex flex-column">
	<video class="border border-radius-lg" autoplay muted controls loop>
		<source src="{{path}}AllChests.mp4" type="video/mp4">
	</video>      
</div>

{% include spacer.html amount="1.5rem" %}

Special thanks to [Jasmin Habezai-Fekri](https://www.artstation.com/curlscurly), 
[Eleanore Falck](https://www.artstation.com/eleanore_falck),
[Mateo Chilla](https://www.artstation.com/mateochilla),
and [Alex Iveroth](https://www.artstation.com/alexiveroth) for
helping to bring these platforms to life!

{% include spacer.html amount="1.5rem" %}