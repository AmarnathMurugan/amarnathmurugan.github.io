---
layout: page
title: Manhole
dates: Mar 2020 - Dec 2021
description: Award-winning real-time animated short film
img: /assets/img/projects/manhole/thumbnail.jpg #3:2
importance: 1
category: work
---

<div class="row" style="text-align:center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="/assets/img/projects/manhole/manhole_poster.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

'Manhole' is an animated short film that depicts the struggles of manual scavengers, a marginalized group in India who clean dangerous sewers and manholes with barely any protective equipment. 

We created the movie during Epic Game's [Shorts India Program](https://www.unrealengine.com/en-US/blog/watch-the-top-projects-from-the-shorts-india-program), where top studios in the country competed to make a film in 3 months with funding and mocap studio access provided by Epic. Our team, however, was an odd one out. We were a group of independent artists who hadn't worked on a 3D film before. Despite this handicap, we emerged **third** in the competition, winning $15k. 'Manhole' was also one of the 72 films from over 1300 submissions screened at the prestigious **Annecy Film Festival**. <br>

<div class="embed-container" style="text-align:center">
  <iframe
      src="https://www.youtube.com/embed/NYyHxQjr3Z8"
      width="700"
      height="400"
      frameborder="0"
      allowfullscreen="true">
  </iframe>
</div>
<div class="caption">
    Manhole - Short Film Trailer
</div>

As the film's **Technical Director** and **Producer**, I tackled some interesting technical and logistical challenges to help create a short with a real-time workflow and distributed team, where almost all the members were using a game engine for the first time. 
 <br><br>  

### Pre-Production

We started pre-production in 2020, intending to make a real-time VR film. The co-director, Abishek Verma — after winning a national award for his 2D animated film 'Machar Jhol' — spent two years studying the plight of manual scavengers and pitched the project to our lab; due to our research experience in storytelling for VR. As we had no funding when the project started, all the core members volunteered their time to complete pre-production.

To reduce the rendering time and have the experience running in VR, I worked with the directors to scope the screenplay and with the artists to decide the ideal level design, poly count, and texel density. We originally intended to have a toon-shaded look, and I wrote a custom shader in unity with the lighting pass implemented from scratch. This allowed me to expose parameters related to toon shading and implement cross-hatching in the shadows.


<div class="row" style="text-align:center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="/assets/img/projects/manhole/toon.gif" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Initial experiment with cross-hatched toon shader
</div>

<div class="row" style="text-align:center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="/assets/img/projects/manhole/toon1.gif" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Shading test with character in sewer
</div>

I textured the dirt layer on the character and the manhole in the above image. Furthermore, the sludge layer was another custom shader driving the vertex offset of a plane with multiple alpha-blended PBR textures. 

A big challenge with making a VR film is that we can't have too many cuts. The animation for each character had to be one single clip, and we needed to see the pre-viz without needing a VR headset to provide easier feedback. Furthermore, the character positions had to be planned well to allow a good vantage point for the viewer to see all the action. The team first created a 2D animatic that shows the timing and position. Based on the 2D version, our animator created playblasts in Maya depicting the character movements and interactions. 

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="/assets/img/projects/manhole/animatic2d.gif" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="/assets/img/projects/manhole/animatic3d.gif" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    2D & 3D Animatic
</div>

<br>  

### Production

With the pre-production completed, our team was actively seeking funding to start production in 2021. However, due to COVID, that proved to be difficult. We later found out about Epic Game's Shorts India Program, but the participants had to be invited by the Epic team. Fortunately, I was an active member of the game development community in India and was an invited speaker at events conducted by the same team. I promptly contacted them and set up a call to pitch our project. Our pre-production work earned us an invite, with a week left before the competition began.

The requirements of the program imposed new challenges. The submission had to be a non-VR film with a lesser runtime than the one indicated by our screenplay. Moreover, we switched game engines, and instead of toon-shading, we decided to go with PBR. We also created more custom 3D models and captured more motion and face data than other teams, which made production even more challenging.

##### Enter the Manhole

The scenes where the protagonist is inside the sewer are crucial. It shows the conditions in which a manual scavenger works, and it is imperative for this part to be impactful. Two elements in the scene contribute to this. First, the sludge within the sewer must seem disgusting. Second, as the character interacts with the sludge, his skin must become grimier. 

I used [FluidNinja Live](https://www.unrealengine.com/marketplace/en-US/product/fluidninja-live), to get a realistic water surface that's also interactive. Then changed the shading and physics parameters to make the sludge look right. 

<video width="100%" preload="auto" muted autoplay loop class="img-fluid rounded z-depth-1">
    <source src="/assets/img/projects/manhole/fluid.mp4" type="video/mp4"/>
</video>
<div class="caption">
    Initial fluid interaction test
</div>

With the shading out of the way, I implemented buoyancy for the garbage floating on the water's surface. FluidNinja exposes velocity and density buffers, which I saved in a render texture and sampled in a blueprint to have the garbage move correctly on the surface. Next, I added static junk on the sides, whose vertices are offset in Z based on the density buffer to make them rise and fall with the water. 

<video width="100%" preload="auto" muted autoplay loop class="img-fluid rounded z-depth-1">
    <source src="/assets/img/projects/manhole/fluidpenul.mp4" type="video/mp4"/>    
</video>
<div class="caption">
    Fluid without reactive garbage
</div>
<video width="100%" preload="auto" muted autoplay loop class="img-fluid rounded z-depth-1">
    <source src="/assets/img/projects/manhole/finalsludge.mp4" type="video/mp4"/>
</video>
<div class="caption">
    Fluid with garbage, as shown in the film
</div>

The next part was shading the character after he interacted with the sludge. For wetness, I modified the metahuman skin shader's specularity and roughness values based on a texture I painted in Quixel Mixer that marks the location of droplets. I also created another texture that demarcates the areas where water drips and combined it with an animated Perlin noise in the shader. I then use this to modify the normals and specular values to render animated dripping water on skin. My approach was based on a [technique](https://www.youtube.com/watch?v=tvBIqPHaExQ&t=1112s) from The Last of Us 2. Next, I added a dirt layer on the skin. I painted two textures that act as masks for the dirt and used them to modify the base albedo. Before changing the base color, I used a parameter that interpolates between clear skin and the two textures to gradually increase the character's griminess. 

<video width="100%" preload="auto" muted autoplay loop class="img-fluid rounded z-depth-1">
    <source src="/assets/img/projects/manhole/watershader.mp4" type="video/mp4"/>    
</video>
<div class="caption">
    Water dripping test
</div>

<video width="100%" preload="auto" muted autoplay loop class="img-fluid rounded z-depth-1">
    <source src="/assets/img/projects/manhole/finalskin.mp4" type="video/mp4"/>    
</video>
<div class="caption">
    End result of grime shader
</div>

##### Animation

On the day of mocap, we had three hours to capture close to fifty shots. The studio had just one actor, while some of our shots required three characters to interact simultaneously. To further complicate matters, we had an underwater scene, and the actor had to be suspended on a crane at the end of the session. Managing all this through zoom was incredibly challenging. We had to prioritize shots on the spot and art direct only the important ones. 


<video width="100%" preload="auto" muted autoplay loop class="img-fluid rounded z-depth-1">
    <source src="/assets/img/projects/manhole/mocap.mp4" type="video/mp4"/>
</video>
<div class="caption">
    Mocap session
</div>

We received the mocap data less than a month before the deadline, which was noisier than expected. Unfortunately, we didn't have an animator onboarded by then. I spent the next three weeks trying to recruit animators. Most freelancers worked full-time with our competitors, making the process more difficult. When I finally onboarded an artist, we had issues with Unreal-Maya roundtripping for metahumans that precluded them from contributing. Fortunately, I negotiated a deal with [Apple Arts Studio](https://www.appleartsstudios.com/), who offered to clean up the raw mocap data at a much lower price, as they sympathized with the cause central to our project. <br><br>

<div class="row" style="text-align:center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="/assets/img/projects/manhole/mocapjitter.gif" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="/assets/img/projects/manhole/mocapclean.gif" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    [Left] Original Data               [Right] Cleaned Mocap data
</div>

I had to solve two more issues with the cleaned-up raw data in hand. First, the data had to be retargeted to our metahuman character. We had almost an hour of mocap data with each clip saved at 30 fps, so the time it took to retarget a single clip was very high due to the number of keyframes. I solved this by writing an editor script that automated retargeting for all the imported 
clips. Second, the differences in the dimensions of our character and the actor introduced self-penetrations after retargeting. Additionally, recording three characters with one actor meant the gaze directions and hand positions were wrong when interacting. After considering the time we had left, we figured the best approach would be to use Unreal's metahuman control rig and do this pass of the cleanup within the engine. One of the design students from our lab was able to quickly pick up unreal and make these modifications. 

The next part was facial capture. We used Unreal's Live Link Face app on an iPhone and attached the device to a makeshift mocap helmet created using bamboo, a selfie stick, and a bicycle helmet. We also had to do further cleanup on this data, which considerably increased the person-hours needed to complete the film.

<video width="100%" preload="auto" muted autoplay loop class="img-fluid rounded z-depth-1">
    <source src="/assets/img/projects/manhole/facecap.mp4" type="video/mp4"/>
</video>
<div class="caption">
    Face Capture session
</div>

Apart from character animation, we had a scene that needed a rope to be animated. I used Unreal's Cable component to create a physics-based rope and set up hidden colliders in the scene to art direct the deformations. Furthermore, the rope had a bucket attached at the end, so that model was set as a constraint, and I keyframed its transform to get the result we wanted.


##### Environment Assets

The story occurs in a busy fictional street in Delhi, with the midday heat beating down on the protagonists. We onboarded [Deckor](https://deckor.co/), an Architecture Visualization company, to handle the asset creation. Their artists went to the streets of Delhi and collected tons of references to create the assets used in the film. I set the expected poly count and texture size for the assets based on their proximity to the virtual cameras and provided feedback on increasing their realism. After the artists completed level building, I did one more pass of level design to meet the artistic requirements set by the directors.


<video width="100%" preload="auto" muted autoplay loop class="img-fluid rounded z-depth-1">
    <source src="/assets/img/projects/manhole/lighting2.mp4" type="video/mp4"/>
</video>
<div class="caption">
    Street assets render
</div>


