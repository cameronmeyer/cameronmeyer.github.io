---
permalink: /interactables/
layout: default

title: Interactables
description: Welcome to the plants page.
---



# Hello Interactables

This is a page about plants.

- Eldren Key/Cache:
    - Custom emissive anim on cache
    - Synced with key insertion via timeline to showcase activation
    - Collision updates as key is removed/added and forcefield activates around cache
- Flashbang Mushrooms:
    - Idle pulsing
    - Custom anim graph
    - Shader animation (idle and activated)
- Hallucinogenic Mushrooms:
    - Shader animation when activated
    - Custom anim graph

---

{% assign path = "/assets/images/projects/Plants/" %}

<div class="ignore content-wrapper">
    <div class="content flex flex-column items-center">
        <video class="border-plain overflow-hidden w-full mb-5" style="border-radius: .5rem" autoplay muted controls loop>
            <source src="{{path}}EldrenCache.mp4" type="video/mp4">
        </video>
		<video class="border-plain overflow-hidden w-full mb-5" style="border-radius: .5rem" autoplay muted controls loop>
            <source src="{{path}}HazardMushroom.mp4" type="video/mp4">
        </video>
		<video class="border-plain overflow-hidden w-full mb-5" style="border-radius: .5rem" autoplay muted controls loop>
            <source src="{{path}}HazardMushroomTall.mp4" type="video/mp4">
        </video>
		<video class="border-plain overflow-hidden w-full mb-5" style="border-radius: .5rem" autoplay muted controls loop>
            <source src="{{path}}HallucinogenicPlant.mp4" type="video/mp4">
        </video>
        <video class="border-plain overflow-hidden w-full mb-5" style="border-radius: .5rem" autoplay muted controls loop>
            <source src="{{path}}HallucinogenicPlantGameplay.mp4" type="video/mp4">
        </video>
    </div>
</div>