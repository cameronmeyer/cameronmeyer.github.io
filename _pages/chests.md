---
permalink: /chests/
layout: default

title: Chests
description: Welcome to the chests page.
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

{% assign path = "/assets/images/projects/Chests/" %}

---

<div class="ignore content-wrapper">
    <div class="content flex flex-column items-center">
        <video class="border-plain overflow-hidden w-full mb-5" style="border-radius: .5rem" autoplay muted controls loop>
            <source src="{{path}}AllChests.mp4" type="video/mp4">
        </video>
        <video class="border-plain overflow-hidden w-full mb-5" style="border-radius: .5rem" autoplay muted controls loop>
            <source src="{{path}}BossChest.mp4" type="video/mp4">
        </video>
        <video class="border-plain overflow-hidden w-full mb-5" style="border-radius: .5rem" autoplay muted controls loop>
            <source src="{{path}}GorgeChest.mp4" type="video/mp4">
        </video>
        <video class="border-plain overflow-hidden w-full mb-5" style="border-radius: .5rem" autoplay muted controls loop>
            <source src="{{path}}EldrenChest.mp4" type="video/mp4">
        </video>
        <video class="border-plain overflow-hidden w-full mb-5" style="border-radius: .5rem" autoplay muted controls loop>
            <source src="{{path}}MinesChest.mp4" type="video/mp4">
        </video>
        <video class="border-plain overflow-hidden w-full mb-5" style="border-radius: .5rem" autoplay muted controls loop>
            <source src="{{path}}RuinsChest.mp4" type="video/mp4">
        </video>
        <video class="border-plain overflow-hidden w-full mb-5" style="border-radius: .5rem" autoplay muted controls loop>
            <source src="{{path}}ReaverwoodsChest.mp4" type="video/mp4">
        </video>
    </div>
</div>
