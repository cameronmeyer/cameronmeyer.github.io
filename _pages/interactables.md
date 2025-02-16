---
permalink: /interactables/
layout: default

title: Interactables
description: Welcome to the plants page.
---
{% assign path = "/assets/images/projects/Interactables/" %}

{% include spacer.html amount="1.5rem" %}

<h1 class="text-center lg:text-left">
	Interactables
</h1>

---

The world of *Wayfinder* is packed full of objects for players to interact with. I had the pleasure of
implementing many of these items, primarily in the late-game 'Crucible' region and for player customizable housing.

---

[//]: # --- ELDREN CACHE --- # :[\\]

{% capture block_content %}
### ELDREN CACHE

Eldren caches spawn occasionally across the land of the Crucible. They are timed challenges for the player with
two main components: a key to collect, and a cache to place it in. If a player can connect both within the allotted
time window, they will be granted loot for their efforts.

The key is a large crystal prism with emissives and VFX to draw the player in. The cache is a hub for the key, with a
hexagonal channel to place it. The key rotates and slides into place, enabling emissives on the cache. The cache's
base glows and its VFX grow more intense as the cache has been fully activated, ready to reward the player.
{% endcapture %}

{% capture block_video %}
{{path}}EldrenCache.mp4
{% endcapture %}

{% include block.html content=block_content video=block_video %}

{% include spacer.html amount="1.5rem" %}





[//]: # --- HAZARD MUSHROOMS --- # :[\\]

{% capture block_content %}
### HAZARD MUSHROOMS

The hazardous mushrooms found in *Wayfinder*'s *Crucible* region spew spores and residue that obscure the player's vision. They 
have a slow idle emissive pulse that warns players to stay away. But if the player gets too close, the mushroom will animate to 
shoot out its residue before going dark and dormant, unable to repeatedly harm the player. 
{% endcapture %}

{% capture block_video %}
{{path}}HazardMushroom.mp4
{% endcapture %}

{% capture block_video2 %}
{{path}}HazardMushroomGameplay.mp4
{% endcapture %}

{% include block.html content=block_content video=block_video video2=block_video2 video_first=true %}

{% include spacer.html amount="1.5rem" %}





[//]: # --- HALLUCINOGENIC MUSHROOMS --- # :[\\]

{% capture block_content %}
### HALLUCINOGENIC MUSHROOMS

Small patches of hallucinogenic mushrooms are also commonly found in *The Crucible*. Getting too close to one of these will 
spawn spores, dust, and even fish that distract and cloud the player's view. This etherial plant will only give players
visions once before they fade in color and then remain dormant.
{% endcapture %}

{% capture block_video %}
{{path}}HallucinogenicPlant.mp4
{% endcapture %}

{% capture block_video2 %}
{{path}}HallucinogenicPlantGameplay.mp4
{% endcapture %}

{% include block.html content=block_content video=block_video video2=block_video2 %}

{% include spacer.html amount="0.5rem" %}





[//]: # --- AVALA'S FLOWERS --- # :[\\]

{% capture block_content %}
### AVALA'S FLOWERS

During the quest *'The Cut'*, *Seeker Avala* requests the player to craft fertilizer for sick plants found in *The Crucible*. 
The player can find wilted, sickly looking flowers to help revive. Once fertilized, the plants spring back to life,
regaining their color and posture.
{% endcapture %}

{% capture block_video %}
{{path}}AvalaFlowers.mp4
{% endcapture %}

{% include block.html content=block_content video=block_video video_first=true %}

{% include spacer.html amount="0.5rem" %}





[//]: # --- DOORS AND WINDOWS --- # :[\\]

{% capture block_content %}
### DOORS AND WINDOWS

In *Wayfinder*, players can own and decorate their own apartment. Not only that, but players can visit each others' apartments too. 
By default, the apartments are completely void of any furniture and decor, although they do have some permanent fixtures--doors and 
windows. 

Designed to bring just a bit more interactivity to their homes, doors and windows may open and close as the player pleases. 

For ease of navigation, doors can open in either direction, and they will always self-close whenever the player is far enough away.
If in multiplayer, doors cannot be opened into a player on the other side. Similarly, if a door is opened, it will not self-close 
until all players are out of its range. 

If somehow a player manages to open a door or window into another player, we apply a knockback force on that player to prevent clipping.
{% endcapture %}

{% capture block_video %}
{{path}}DoorsAndWindows.mp4
{% endcapture %}

{% capture block_video2 %}
{{path}}DoorsAndWindowsMultiplayer.mp4
{% endcapture %}

{% include block.html content=block_content video=block_video video2=block_video2 %}

{% include spacer.html amount="0.5rem" %}





[//]: # --- CRITICAL ROLE --- # :[\\]

{% capture block_content %}
### CRITICAL ROLE GAMEBOARDS

*Wayfinder*'s first DLC bundle is a partnership with *Critical Role*, bringing skins of their popular characters into the game, as well as 
Dungeons and Dragons inspired props. Among other things, this included a DnD game board depicting a battle, and a tray of dice. 

When interacted with, the battle board will randomly choose an animation of a battle sequence to play out with all the game pieces. The 
dice trays can spawn with multiple dice configurations once placed in an apartment. Once rolled, the dice tray uses flashy visual effects to
display a random result from a D20.
{% endcapture %}

{% capture block_video %}
{{path}}CriticalRole.mp4
{% endcapture %}

{% capture block_video2 %}
{{path}}CriticalRoleMultiplayer.mp4
{% endcapture %}

{% include block.html content=block_content video=block_video video2=block_video2 video_first=true %}

{% include spacer.html amount="0.5rem" %}


---

{% include spacer.html amount="1.5rem" %}

Special thanks to [Eleanore Falck](https://www.artstation.com/eleanore_falck),
[Rebecca McManamy](https://www.rebeccamcmanamy.com/), [Ryan Cullum](https://www.ryanmakingthings.com),
[Brittany Rojas](https://www.artstation.com/brittanyhein3d),
and [Dave Sullivan](https://davesullivanonline.ca/) for helping to bring these interactables to life!

{% include spacer.html amount="1.5rem" %}