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

- wayfinder has large open biomes/levels
- our studio is small
- need for automated perf testing to track stats over time
- needed to be able to call out specific areas (camera angles) to investigate for bottlenecks

--- 

<img class="border-plain border-radius-md mb-5" src="{{path}}FolderContents.png" alt="FolderContents.png" />
<img class="border-plain border-radius-md mb-5" src="{{path}}PerfReport.png" alt="PerfReport.png" />

[//]: # --- GAMEPLAY --- # :[\\]

{% capture block_content %}
### TOOL STRUCTURE

- auto perf tool hooks into unreal's automation test framework (found within the session frontend?)
- the test reads data from tables to determine test parameters
	- test setting table
		- minimum realtime to wait for stabilization
		- minimum frame count to wait for stabilization
		- sampling duration
		- sampling frame count
		- window size/resolution
		- quality settings
	- maps table
		- map name
		- enabled in testing menu?
- perf cams are placed around levels that need testing
	- should be hand-placed, ideally from angles that players are likely to actually see in game
	- these cameras have a special PerfCam tag
	- cameras are not loaded in build, only in test environment
- when test executes:
	- iterate through all the cameras
		- record data
			- camera name
			- avg fps
			- avg game thread time (ms?)
			- avg render thread time (ms?)
			- avg gpu thread time (ms?)
		- screenshot
	- write output to file
		- version
		- date
		- map
		- resolution
		- camera table

- usefulness:
	- easy evaluation of performance targets
	- as many or as few cameras as you'd like
	- data + camera location indicates specific areas for bottlenecks
	- screenshots obviously show what is being rendered in a specific location so we can go track things down

{% endcapture %}

{% include block.html content=block_content %}

{% include spacer.html amount="1.5rem" %}