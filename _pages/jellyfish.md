---
permalink: /jellyfish/
layout: default

title: Jellyfish
description: Welcome to the jellyfish page.
---

{% include spacer.html amount="1.5rem" %}

# Jellyfish Platforms

---

<div class="content flex flex-column">
	<video class="border border-radius-lg" autoplay muted controls loop>
		<source src="{{path}}JellyfishMultiplayerGameplay.mp4" type="video/mp4">
	</video>      
</div>

This is a page about jellyfish platforms. It's a very good page. It will discuss the following:
- Idle activity
	- Bobbing
	- Rotating
	- Pulsing
	- Jiggling
- Reactivity
	- VFX
	- Emissive pulse
	- Wobble
	- Bounce
- Multiplayer/Replication Support
	- Lower bound offset cap
	- Visuals and hitboxes identical between players

---

{% assign path = "/assets/images/projects/Jellyfish/" %}


[//]: # --- JELLYFISH IDLING --- # :[\\]

{% capture block_content %}
### IDLE ACTIVITY

Since these platforms are based on real, living creatures, I wanted to ensure they felt *alive* even when the
player wasn't interacting with them. However, this idle behavior needed to be subtle enough that it would not
interfere with the level platforming elements. 

You will see the idle jellyfish:
- Bobbing
- Rotating
- Pulsing
- Jiggling
{% endcapture %}

{% capture block_video %}
/assets/images/jellyfish.mp4
{% endcapture %}

{% include block.html content=block_content video=block_video %}





{% include spacer.html amount="1.5rem" %}





[//]: # --- REACTIVITY --- # :[\\]

{% capture block1_content %}
### REACTIVITY

These platforms respond to the player landing on them! The visual feedback includes:
- VFX
- Emissive pulse
- Wobble
- Bounce
{% endcapture %}

{% capture block1_video %}
{{path}}JellyfishElevator.mp4
{% endcapture %}

{% include block.html content=block1_content video=block1_video video_first=true %}





{% include spacer.html amount="1.5rem" %}





[//]: # --- JELLYFISH MULTIPLAYER 1 --- # :[\\]

{% capture block2_content %}
### MULTIPLAYER!

Some text about Jellyfish! I will write actually quite a lot of text here because I want to see what happens
when we have a lot going on and how the page elements will decide to space themselves out.

The platforms work well with multiplayer and replication to clients! Here's how:
- Lower bound offset cap
- Visuals and hitboxes identical between players
{% endcapture %}

{% capture block2_video %}
{{path}}JellyfishMultiplayerSpectator.mp4
{% endcapture %}

{% capture block2_video2 %}
{{path}}JellyfishMultiplayerSpectator2.mp4
{% endcapture %}

{% include block.html content=block2_content video=block2_video video2=block2_video2 %}





{% include spacer.html amount="1.5rem" %}