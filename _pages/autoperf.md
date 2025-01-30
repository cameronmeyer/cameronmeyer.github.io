---
permalink: /autoperf/
layout: default

title: Auto Perf
description: Welcome to the automated performance tool page.
---
{% assign path = "/assets/images/projects/AutoPerf/" %}

{% include spacer.html amount="1.5rem" %}

# Automated Performance Testing

---

## Demo Video

{% include spacer.html amount="0.5rem" %}

<div class="content flex flex-column">
	<video class="border border-radius-lg" autoplay muted controls loop>
		<source src="{{path}}AutoPerf.mp4" type="video/mp4">
	</video>      
</div>

{% include spacer.html amount="0.5rem" %}

*Note: Demo video has been sped up for demonstration purposes.*

{% include spacer.html amount="1.5rem" %}

*Wayfinder*'s overland levels are expansive biomes for players to explore. For our relatively small studio size to stay efficient, 
we needed a more automated approach to tracking performance over time. From this data, we also needed to be able to call out 
specific areas to investigate further for bottlenecks.

--- 

<div class="content flex flex-column align-items-center justify-items-center">
	<img class="border-plain border-radius-md mb-5" style="width: 65%" src="{{path}}FolderContents.png" alt="FolderContents.png" />
	<img class="border-plain border-radius-md mb-5" style="width: 65%" src="{{path}}PerfReport.png" alt="PerfReport.png" />
</div>

[//]: # --- GAMEPLAY --- # :[\\]

{% capture block_content %}
### TOOL STRUCTURE

The Auto Perf tool hooks into Unreal Engine's automation test framework, allowing us to launch it with the click of a button.
The test reads from data tables to determine the performance test's parameters, including:
- Minimum duration to wait for the game to stabilize before sampling performance
- Sampling duration
- Window resolution of test
- Global quality setting presets
- Which maps allow for performance testing

Cameras are hand-placed around levels, ideally showing angles that players are likely to encounter in game. Each camera has an 
actor tag applied to it, identifying it as relevant to performance testing. These cameras only exist in the test environment, not
in official builds.

When the test executes, we iterate through each camera, taking a screenshot and recording the following data:
- Camera name
- Average FPS
- Average game thread time (in ms)
- Average render thread time (in ms)
- Average GPU thread time (in ms)

After all data has been collected, we write the output to a new file that has additional information, such as:
- Build version
- Date of test
- Map name
- Resolution captured
- ...and all data from the cameras

Leveraging automated testing was extremely useful for the *Wayfinder* team, as it allowed for easy evaluation of our performance targets.
We could place as many cameras as needed, and from referencing the collected data and the screenshots, we could investigate areas 
experiencing slowdowns. 

{% endcapture %}

{% include block.html content=block_content %}

{% include spacer.html amount="1.5rem" %}