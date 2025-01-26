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

The world of *Wayfinder* is packed full of objects for players to interact with. I had the pleasure of
implementing many of these items, primarily in the late-game 'Crucible' region and for player customizable housing.

---

[//]: # --- ELDREN CACHE --- # :[\\]

{% capture block_content %}
### ELDREN CACHE

Eldren caches spawn occasionally across the land of the Crucible. They are timed challenges for the player with
two main components: a key to collect, and a cache to place it in. If a player can connect both within the allotted
time window, they will be granted some loot for their efforts.

The key is a large crystalline hexagonal prism with emissives and VFX to draw the player in. Once obtained, a miniaturized
version will float behind the player as they transport it to the cache. The cache is a hub for the key, with a hexagonal
channel to place it in. The key rotates and slides into place, alighting emissive lines on the cache. Then, the whole cache 
base glows and the VFX grow more intense as the cache has been fully activated, ready to reward the player.
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