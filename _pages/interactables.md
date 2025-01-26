---
permalink: /interactables/
layout: default

title: Interactables
description: Welcome to the plants page.
---
{% assign path = "/assets/images/projects/Interactables/" %}

{% include spacer.html amount="1.5rem" %}

# Interactables

---

In *Wayfinder* players will encounter a variety of treasure chests during their journey. I was fortunately tasked with the
implementation and polish of several of these chests. While their visuals may vary greatly, all chests generally required 
custom setups that included the following:
- Animations, sounds, and visual effects all synced up with timelines
- Animated material properties synced with other effects
- Blueprint logic to execute all component parts, handle state changes, and award loot

---

[//]: # --- ELDREN CACHE --- # :[\\]

{% capture block_content %}
### ELDREN CACHE

- Custom emissive anim on cache
- Synced with key insertion via timeline to showcase activation
- Collision updates as key is removed/added and forcefield activates around cache
{% endcapture %}

{% capture block_video %}
{{path}}EldrenCache.mp4
{% endcapture %}

{% include block.html content=block_content video=block_video %}

{% include spacer.html amount="1.5rem" %}





[//]: # --- HAZARD MUSHROOMS --- # :[\\]

{% capture block_content %}
### HAZARD MUSHROOMS

- Idle pulsing
- Custom anim graph
- Shader animation (idle and activated)
{% endcapture %}

{% capture block_video %}
{{path}}HazardMushroom.mp4
{% endcapture %}

{% capture block_video2 %}
{{path}}HazardMushroomTall.mp4
{% endcapture %}

{% include block.html content=block_content video=block_video video2=block_video2 video_first=true %}

{% include spacer.html amount="1.5rem" %}





[//]: # --- HALLUCINOGENIC PLANTS --- # :[\\]

{% capture block_content %}
### HALLUCINOGENIC PLANTS

- Shader animation when activated
- Custom anim graph
{% endcapture %}

{% capture block_video %}
{{path}}HallucinogenicPlant.mp4
{% endcapture %}

{% capture block_video2 %}
{{path}}HallucinogenicPlantGameplay.mp4
{% endcapture %}

{% include block.html content=block_content video=block_video video2=block_video2 %}

{% include spacer.html amount="0.5rem" %}





[//]: # --- AVALA FLOWERS --- # :[\\]

{% capture block_content %}
### AVALA FLOWERS

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





[//]: # --- DOORS AND WINDOWS --- # :[\\]

{% capture block_content %}
### DOORS AND WINDOWS

In *Wayfinder*, godsblood is a key power source extracted from underground veins.
That fluid flows through this gritty, forged chest.

As the chest opens, the godsblood drains from the chest. The liquid level in pipes on either side
goes down, and the chest loses its lustrous green emissive once the player has looted from it.
{% endcapture %}

{% capture block_video %}
{{path}}MinesChest.mp4
{% endcapture %}

{% include block.html content=block_content video=block_video %}

{% include spacer.html amount="0.5rem" %}





[//]: # --- CRITICAL ROLE --- # :[\\]

{% capture block_content %}
### CRITICAL ROLE GAMEBOARD

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


---

{% include spacer.html amount="1.5rem" %}

Special thanks to [Eleanore Falck](https://www.artstation.com/eleanore_falck),
Rebecca McManamy, Ryan Cullum, Brittany Rojas, and Dave Sullivan for helping to bring these platforms to life!

{% include spacer.html amount="1.5rem" %}