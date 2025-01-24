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

In *Wayfinder*... blah blah blah chests!!

---

[//]: # --- BOSS CHEST --- # :[\\]

{% capture block_content %}
### BOSS AND MYTHIC CHESTS

These chests are the same for defeating bosses and completing mythic hunts. 

In their idle state, the jellyfish are capable of:
- Bobbing
- Rotating
- Pulsing
- Jiggling

The internal values controlling these behaviors are all randomized between platform instances, so no two
platforms will sync up their movement in an unnatural way.
{% endcapture %}

{% capture block1_video %}
{{path}}BossChest.mp4
{% endcapture %}

{% include block.html content=block_content video=block1_video %}

{% include spacer.html amount="1.5rem" %}





[//]: # --- ELDREN CHEST --- # :[\\]

{% capture block1_content %}
### ELDREN CHESTS

These living platforms also react to the player! When player lands on them, the platforms:
- Push downward and rebound to their original positions
- Surface jiggle and emissive pulse
- Play fungal spore VFX and otherworldly sound effects
{% endcapture %}

{% capture block1_video %}
{{path}}GorgeChest.mp4
{% endcapture %}

{% include block.html content=block1_content video=block1_video video_first=true %}

{% include spacer.html amount="1.5rem" %}





[//]: # --- RUINS CHEST --- # :[\\]

{% capture block2_content %}
### RUINS CHESTS

Since *Wayfinder* supports online co-op play, the jellyfish platforms needed to be able to support 
network replication to clients. It was critical that the jellyfish platforms match *exactly* between
party members to avoid potential de-sync issues from differences in collision or placement of the
platforms. 

There were some notable challenges in implementing multiplayer support:
- Idle movement variables needed to be randomized per floating platform, but set from the host for all clients to match
- The jellyfish's organic, non-symmetrical shape required the collision mesh to move exactly in step with the visuals
- The vertical rebound from the player landing on the jellyfish needed a maximum offset in case party members repeatedly jumped on it
{% endcapture %}

{% capture block2_video %}
{{path}}RuinsChest.mp4
{% endcapture %}

{% include block.html content=block2_content video=block2_video %}

{% include spacer.html amount="0.5rem" %}





[//]: # --- MINES CHEST --- # :[\\]

{% capture block2_content %}
### MINES CHESTS

Since *Wayfinder* supports online co-op play, the jellyfish platforms needed to be able to support 
network replication to clients. It was critical that the jellyfish platforms match *exactly* between
party members to avoid potential de-sync issues from differences in collision or placement of the
platforms. 

There were some notable challenges in implementing multiplayer support:
- Idle movement variables needed to be randomized per floating platform, but set from the host for all clients to match
- The jellyfish's organic, non-symmetrical shape required the collision mesh to move exactly in step with the visuals
- The vertical rebound from the player landing on the jellyfish needed a maximum offset in case party members repeatedly jumped on it
{% endcapture %}

{% capture block2_video %}
{{path}}MinesChest.mp4
{% endcapture %}

{% include block.html content=block2_content video=block2_video video_first=true %}

{% include spacer.html amount="0.5rem" %}





[//]: # --- REAVERWOODS CHEST --- # :[\\]

{% capture block2_content %}
### REAVERWOODS CHESTS

Since *Wayfinder* supports online co-op play, the jellyfish platforms needed to be able to support 
network replication to clients. It was critical that the jellyfish platforms match *exactly* between
party members to avoid potential de-sync issues from differences in collision or placement of the
platforms. 

There were some notable challenges in implementing multiplayer support:
- Idle movement variables needed to be randomized per floating platform, but set from the host for all clients to match
- The jellyfish's organic, non-symmetrical shape required the collision mesh to move exactly in step with the visuals
- The vertical rebound from the player landing on the jellyfish needed a maximum offset in case party members repeatedly jumped on it
{% endcapture %}

{% capture block2_video %}
{{path}}ReaverwoodsChest.mp4
{% endcapture %}

{% include block.html content=block2_content video=block2_video %}

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

[//]: # --- EVENTUALLY... DELETE BELOW! --- # :[\\]

---

# Hello Chests

This is a page about chests. It's a very good page. It will discuss the following:
- All Chests:
	- Boss Chest
    - Ruins Chest
        - Shader animation - ball rotation (or was that animated?) and panning emissive on parts of mesh
    - Mines Chest
        - Shader animation - liquid draining
    - Reaverwoods Chest
    - Eldren Chest
        - Shader animation - orb activating/dispersing
- Features:
    - synced animations, sounds, and vfx with timelines
    - custom shader animation
    - custom anim graph
    - done with BP logic
