---
permalink: /animalcrossingTCG/
layout: default

title: Animal Crossing TCG
description: Welcome to the ACTCG page.
---
{% assign path = "/assets/images/projects/ACTCG/" %}

{% include spacer.html amount="1.5rem" %}

# Animal Crossing: The Trading Card Game

---

<div class="content flex flex-column"> 
	<div class="border border-radius-lg">
		<div style="padding:56.25% 0 0 0; position:relative;">
			<iframe src="https://player.vimeo.com/video/927455719?badge=0&amp;autopause=0&amp;player_id=0&amp;app_id=58479" frameborder="0" allow="autoplay; fullscreen; picture-in-picture; clipboard-write; encrypted-media" style="position:absolute;top:0;left:0;width:100%;height:100%;" title="ACTCG Mockup Showcase">
			</iframe>
		</div>
	</div>
</div>

{% include spacer.html amount="0.5rem" %}

Since the Nintendo DS era, Animal Crossing has been one of my favorite game franchises. When my teammate [Katie Sauter](https://www.artstation.com/katiesauter)
approached me about creating a virtual trading card game inspired by the series, I knew I couldn't resist.

Our Animal Crossing TCG is styled after the *New Horizons* series entry. We aimed to stay faithful to the source material while supporting TCG gameplay and 
optimizing assets to support low-spec devices. 

You can view our project repository [here](https://github.com/Kaitlz/ACTCG_Unity).





---





[//]: # --- FISH --- # :[\\]

## FISH

{% include spacer.html amount="0.5rem" %}

{% capture block_content %}
### FISH

To help the environment feel more lively, I implemented a fish to swim around the river. In an attempt to create an optimized asset
in a short timeframe, I developed the fish as a shader applied to a quad.

This fish only needed to look believeable swimming around the river--it did not need fancy movement logic for a dynamic fishing
gameplay experience. So, the quad was simply animated in a loop to swim about the river. 

The timeline controlled not only the quad transform, but also how quicky the fish was swimming (tail frequency), how hard it was
swimming (tail amplitude), and when it would create surface ripples from water displacement.
{% endcapture %}

{% capture block_video %}
{{path}}Fish.mp4
{% endcapture %}

{% capture block_video2 %}
{{path}}FishTimeline.mp4
{% endcapture %}

{% include block.html content=block_content video=block_video video2=block_video2 %}

{% include spacer.html amount="1.5rem" %}




{% capture block_content %}
The fish shader is fairly simple. We generate a sine wave with parameters for frequency and amplitude. We use the sine wave to offset the
quad's UVs so the tail can move back and forth. These offset UVs are applied to the quad with a mask that allows the tail to move while
the head stays still.

When setting the frequency of a sine wave directly, the function adjusts relative to its origin point. So if we're sampling the sine function
at a non-zero time value, animating the frequency will cause erratic behavior as the output traverses many peaks and troughs of the sine function.
To prevent this, we keep track of the wave's current phase. 

Each frame's input to the sine function depends on the previous frame's value to achieve a smooth result. We increment the current phase by
`(deltaTime * frequency)`. Whenever the current phase maps to an output beyond one period of the sine function, we subtract by one period to 
prevent an infinitely increasing phase.
{% endcapture %}

{% capture block_image %}
{{path}}FishShader.png
{% endcapture %}

<div class="content">
    <div class="block border border-radius-lg flex flex-row">
        <div>
			<h3>FISH SHADER</h3>
			<div class="block-media">
				<img class="border-plain border-radius-md" src="{{ block_image }}" />
			</div>
			<div class="block-content" markdown="1">{{ block_content }}</div>
            <div class="block-content-mobile" markdown="1">{{ block_content }}</div>
		</div>
	</div>
</div>

{% include spacer.html amount="1.5rem" %}





---





[//]: # --- CARD BREAKDOWN --- # :[\\]

## CARD BREAKDOWN

{% include spacer.html amount="0.5rem" %}

{% capture block_content %}
### CARD COMPONENTS

Our TCG's playing cards are assembled from several component parts. Constructing cards this way allows for easy swapping of patterns, icons, and text
that can be populated from card data. Each card's data is stored as a scriptable object and then populated into a basic card prefab at runtime.
{% endcapture %}

{% capture block_video %}
{{path}}CardBreakdown.mp4
{% endcapture %}

{% include block.html content=block_content video=block_video %}

{% include spacer.html amount="1.5rem" %}



{% capture block_content %}
### SCRIPTABLE OBJECTS

Scriptable objects provide a uniform way to organize card data. Each exposed field can be assigned per card, storing what 
icons, materials, colors, and text that card should use. 

The base card scriptable object contains general data applicable to all card types such as color scheme, name, and type. 
Each card type then inherits from the base object to support additional, type-specific data, like species and birthday
information for `Villager` cards, or happiness point values for `Fruit` cards.
{% endcapture %}

{% capture block_image %}
{{path}}CardSO.png
{% endcapture %}

{% include image_block.html content=block_content image=block_image image_first=true %}

{% include spacer.html amount="1.5rem" %}





---





[//]: # --- PARALLAX --- # :[\\]

## PARALLAX

{% include spacer.html amount="0.5rem" %}

{% capture block_content %}
### PARALLAX SHADER

The logic to add parallax elements to a shader is  quite simple. Relative to the camera view direction, we can adjust
how strong the parallax effect is along the X and Y directions. We also apply scaling and offset to the mesh UVs and 
add them to the parallax intensity `Vector2`.

By creating our parallax UVs this way, we can call this logic repeatedly as a subgraph of our shader. Each of our
cards in the game supports up to five parallax elements on their material, each with unique scale, offset, and 
parallax intensity settings. With some fine tuning, we can present multiple layers of depth that feel natural to
the player.
{% endcapture %}

{% capture block_image %}
{{path}}ParallaxShader.png
{% endcapture %}

{% include image_block.html content=block_content image=block_image %}

{% include spacer.html amount="1.5rem" %}




{% capture block_content %}
### PARALLAX DEMO

To demonstrate the parallax shader in action, these videos show just the character portrait section of a playing card.

Above is the finalized version of this portrait. To sell the effect of juggling on a highwire, we lock the character
in place with a parallax intensity of zero. Each of the juggling balls moves as though they are being thrown toward the
player, with the closest of the balls having the greatest parallax intensity. The background moves in the opposite 
direction of the juggling balls, showcasing its distance from the viewer.

Below demonstrates controls we have to place each parallax element within the portrait and adjust how they will move
relative to the viewer.
{% endcapture %}

{% capture block_video %}
{{path}}PietroTilt.mp4
{% endcapture %}

{% capture block_video2 %}
{{path}}PietroPlacement.mp4
{% endcapture %}

{% include block.html content=block_content video=block_video video2=block_video2 video_first=true %}

{% include spacer.html amount="1.5rem" %}




---




[//]: # --- CARD INTERACTIVITY --- # :[\\]

{% capture block_content %}
### CARD INTERACTIVITY

When developing card interaction logic, I aimed for polished movement. Specifically, I didn't want the game to feel 'stiff' to interact with.

Before implementation, I identified the possible states a card could be placed in:
- On game board:
	- In play
	- In deck or discard
- In hand:
	- Hovered
	- Unhovered
	- Currently selected (clicked)

To add polish and improve the player experience, I implemented the following behaviors:
- Highlighted cards straighten and enlarge for readability
- Cards in hand can be reordered
- Fanned cards in hand reposition when a card is selected/dragged away or placed back in hand
- Selected cards tilt in the direction they're moving toward as they are dragged across the board
{% endcapture %}

{% capture block_video %}
{{path}}Cards.mp4
{% endcapture %}

{% include block.html content=block_content video=block_video %}

{% include spacer.html amount="1.5rem" %}





---





[//]: # --- CREDITS --- # :[\\]

Thank you to my teammate [Katie Sauter](https://www.artstation.com/katiesauter) for developing the concept and the environment. 

Additional thanks to [Syd Roberts](https://www.artstation.com/sydroberts) for her Elmer illustration, and to
[Ryan Polasky](https://ryanpolasky.carrd.co/) for composing the music.

{% include spacer.html amount="1.5rem" %}