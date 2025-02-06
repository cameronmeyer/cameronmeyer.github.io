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
### FISH SHADER

shader: 
- fairly simple
- generate a sine wave with control over frequency and amplitude control
	- input to sine wave is called CurrentPhase, set in code
- use the sine wave to offset quad UVs so the tail can flick back and forth
- the offset sine UVs are applied to the quad with a mask, so the head is stationary while the tail moves

we had to put some logic in code because in order to change tail frequency, the sine input must be dependant on the previous frame input. 
adjusting the frequency directly in a timeline causes stutter and errattic behavior. keeping a cumulative phase value allows for smooth transitions

code:
- each frame we determine our state (not turning, left turn, right turn)
- if our current phase + (deltaTime * frequency) >= default phase (in other words, are we safe to adjust phase without stutter?)
	- reduce the phase so we don't go off to infinity (i.e. going from 2pi to 0, removing a whole rotation but maintaining the sine value)
- else
	- (default behavior) increment currentPhase by deltaTime * frequency
- set the material parameter
{% endcapture %}

{% capture block_image %}
{{path}}FishShader.png
{% endcapture %}

{% include image_block.html content=block_content image=block_image image_first=true %}

{% include spacer.html amount="1.5rem" %}

---

[//]: # --- CARD BREAKDOWN --- # :[\\]

## CARD BREAKDOWN

{% include spacer.html amount="0.5rem" %}

{% capture block_content %}
### CARD COMPONENTS

- cards are assembled with several component parts
- this allowed us to easily iterate on specific card components
- also allows for easier data population
- card data is stored as a scriptable object and then populated into card prefabs, each card is based off a parent prefab instead
	of having its own
{% endcapture %}

{% capture block_video %}
{{path}}CardBreakdown.mp4
{% endcapture %}

{% include block.html content=block_content video=block_video %}

{% include spacer.html amount="1.5rem" %}



{% capture block_content %}
### SCRIPTABLE OBJECTS

- card scriptable objects are a uniform way to organize card data
- each field can be adjusted per card
- icons, materials, colors, and text are stored here for each card
- there is a parent card scriptable object with multiple children for each card type
	- special npc
	- villager
	- fruit
	- tool
- cards are populated at runtime
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




[//]: # --- CARD MOVEMENT --- # :[\\]

{% capture block_content %}
### CARD GAMEPLAY/JUICE/MOVEMENT

- cards have multiple states
	- on board
		- in play
		- in deck or discard
	- in hand
		- hovered
		- unhovered
		- selected (floating)
- goal of juicy, good-feeling interactions with cards
- nothing happens too stiffly
- highlighted cards straighten and enlarge for readability
- cards in hand can be reorganized
- fanned cards in hand reposition when a card is selected or placed back in hand
{% endcapture %}

{% capture block_video %}
{{path}}Cards.mp4
{% endcapture %}

{% include block.html content=block_content video=block_video %}

{% include spacer.html amount="1.5rem" %}





---





[//]: # --- CREDITS --- # :[\\]

Special thanks to [Syd Roberts](https://www.artstation.com/sydroberts) for her Elmer illustration, and to
[Ryan Polasky](https://ryanpolasky.carrd.co/) for composing the music.