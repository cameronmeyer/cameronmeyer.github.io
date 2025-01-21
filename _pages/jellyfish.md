---
permalink: /jellyfish/
layout: default

title: Jellyfish
description: Welcome to the jellyfish page.
---

# Jellyfish Platforms

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





[//]: # --- JELLYFISH ELEVATOR --- # :[\\]

{% capture block1_content %}
# TESTING OUT MARKDOWN

Here is some sample text. Might be *italics*, **bold**, or ***BOTH***!

- Multiplayer/Replication Support
	- Lower bound offset cap
	- Visuals and hitboxes identical between players
{% endcapture %}

{% capture block1_video %}
{{path}}JellyfishElevator.mp4
{% endcapture %}

{% include block.html content=block1_content video=block1_video %}





{% include spacer.html amount="1.5rem" %}





[//]: # --- JELLYFISH MULTIPLAYER 1 --- # :[\\]

{% capture block2_content %}
# MULTIPLAYER!

Some text about Jellyfish! I will write actually quite a lot of text here because I want to see what happens
when we have a lot going on and how the page elements will decide to space themselves out.
{% endcapture %}

{% capture block2_video %}
{{path}}JellyfishMultiplayerSpectator.mp4
{% endcapture %}

{% include block.html content=block2_content video=block2_video video_first=true %}





{% include spacer.html amount="1.5rem" %}





[//]: # --- JELLYFISH MULTIPLAYER 2 --- # :[\\]

{% capture block3_content %}
# Section Header!

Some text about Jellyfish! I will write actually quite a lot of text here because I want to see what happens
when we have a lot going on and how the page elements will decide to space themselves out.
{% endcapture %}

{% capture block3_video %}
{{path}}JellyfishMultiplayerSpectator2.mp4
{% endcapture %}

{% include block.html content=block3_content video=block3_video %}





{% include spacer.html amount="1.5rem" %}





[//]: # --- JELLYFISH MULTIPLAYER GAMEPLAY --- # :[\\]

{% capture block4_content %}
# GAMEPLAY!

Some text about Jellyfish! I will write actually quite a lot of text here because I want to see what happens
when we have a lot going on and how the page elements will decide to space themselves out.
{% endcapture %}

{% capture block4_video %}
{{path}}JellyfishMultiplayerGameplay.mp4
{% endcapture %}

{% include block.html content=block4_content video=block4_video video_first=true %}





{% include spacer.html amount="1.5rem" %}