---
permalink: /chests/
layout: default

title: Chests
description: Welcome to the chests page.
---



# Hello Chests

This is a page about chests.

{% assign path = "/assets/images/projects/Chests/" %}


<div class="ignore content-wrapper">
    <div class="content flex flex-column items-center">
        <video class="border-plain overflow-hidden w-full mb-5" style="border-radius: .5rem" autoplay muted controls loop>
            <source src="{{path}}{{AllChests.mp4}}" type="video/mp4">
        </video>
        <video class="border-plain overflow-hidden w-full mb-5" style="border-radius: .5rem" autoplay muted controls loop>
            <source src="{{path}}{{BossChest.mp4}}" type="video/mp4">
        </video>
        <video class="border-plain overflow-hidden w-full mb-5" style="border-radius: .5rem" autoplay muted controls loop>
            <source src="{{path}}{{GorgeChest.mp4}}" type="video/mp4">
        </video>
        <video class="border-plain overflow-hidden w-full mb-5" style="border-radius: .5rem" autoplay muted controls loop>
            <source src="{{path}}{{MinesChest.mp4}}" type="video/mp4">
        </video>
        <video class="border-plain overflow-hidden w-full mb-5" style="border-radius: .5rem" autoplay muted controls loop>
            <source src="{{path}}{{RuinsChest.mp4}}" type="video/mp4">
        </video>
        <video class="border-plain overflow-hidden w-full mb-5" style="border-radius: .5rem" autoplay muted controls loop>
            <source src="{{path}}{{ReaverwoodsChest.mp4}}" type="video/mp4">
        </video>
    </div>
</div>
