---
permalink: /jellyfish/
layout: default

title: Jellyfish
description: Welcome to the jellyfish page.
---
{% assign path = "/assets/images/projects/Jellyfish/" %}

{% include spacer.html amount="1.5rem" %}

<h1 class="text-center lg:text-left">
	Jellyfish Platforms
</h1>

---

<div class="content flex flex-column">
	<video class="border border-radius-lg" autoplay muted controls loop>
		<source src="{{path}}JellyfishMultiplayerGameplay.mp4" type="video/mp4">
	</video>      
</div>

{% include spacer.html amount="1.5rem" %}

In *Wayfinder*'s Crucible world region, the mystical jungle-like environment is broken up by steep changes in elevation
that compose a large gorge. To bridge some of these gaps and provide the player with more traversal options, we created
floating platforms. The platforms' visuals land somewhere between a living jellyfish that entices the player to approach,
and a large mossy rock, to communicate that the player may stand on them.

---

[//]: # --- JELLYFISH IDLING --- # :[\\]

{% capture block_content %}
### IDLE ACTIVITY

Since these platforms are based on living creatures, I wanted to ensure they felt *alive* even when the
player wasn't directly interacting with them. However, this idle behavior needed to be subtle enough that
it would not interfere with the level platforming elements. 

In their idle state, the jellyfish are capable of:
- Bobbing
- Rotating
- Pulsing
- Jiggling

The internal values controlling these behaviors are all randomized between platform instances, so no two
platforms will sync up their movement in an unnatural way.
{% endcapture %}

{% include block.html content=block_content video="/assets/images/projects/jellyfish.mp4" %}

{% include spacer.html amount="1.5rem" %}





[//]: # --- REACTIVITY --- # :[\\]

{% capture block1_content %}
### REACTIVITY

These living platforms also react to the player! When player lands on them, the platforms:
- Push downward and rebound to their original positions
- Surface jiggle and emissive pulse
- Play fungal spore VFX and otherworldly sound effects
{% endcapture %}

{% capture block1_video %}
{{path}}JellyfishElevator.mp4
{% endcapture %}

{% include block.html content=block1_content video=block1_video video_first=true %}

{% include spacer.html amount="1.5rem" %}





[//]: # --- JELLYFISH MULTIPLAYER 1 --- # :[\\]

{% capture block2_content %}
### MULTIPLAYER SUPPORT

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
{{path}}JellyfishMultiplayerSpectator.mp4
{% endcapture %}

{% capture block2_video2 %}
{{path}}JellyfishMultiplayerSpectator2.mp4
{% endcapture %}

{% include block.html content=block2_content video=block2_video video2=block2_video2 %}

{% include spacer.html amount="0.5rem" %}

---

Special thanks to [Eleanore Falck](https://www.artstation.com/eleanore_falck) and [Will Santos](https://www.wesantos.com/) for
helping to bring these platforms to life!

{% include spacer.html amount="1.5rem" %}