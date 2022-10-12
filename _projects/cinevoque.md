---
layout: page
title: Cinévoqué
description: Passively responsive live-action VR films
img: assets/img/projects/cine/cinevoque_thumbnail.jpg
importance: 3
category: work
---

<div class="row" style="text-align:center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="/assets/img/projects/cine/cine_poster.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

Cinévoqué is my first research project. I created this in the summer of 2018 during my internship at IMXD lab under Prof Jayesh Pillai and in collaboration with Amal Dev. The project started as an exploration of dynamically changing the visuals outside the user's field of view in a live-action VR film. This idea led to the current framework, whose name is a portmanteau of the words Cinema and Evoke, signifying the system's ability to evoke a narrative corresponding to the viewer's gaze.

Virtual Reality as a medium of storytelling is relatively less developed than storytelling in traditional films. The viewer is empowered with the ability to change the framing in VR, and they may not follow all the points of interest intended by the storyteller. As a result, traditional films' filmmaking and storytelling practices do not directly translate. 


<div class="row" style="text-align:center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="/assets/img/projects/cine/Dragonfly_Eye-tracking_heatmap.gif" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Eye tracking data of 100 participants watching a VR film. The gray outline marks the area the director intended the viewers to look at
</div>

Cinévoqué alters the narrative shown to the viewers based on the events of the movie they have followed or missed. Furthermore, it also estimates their interest in particular events by measuring the time they spend gazing at it, and uses that to inform the transitions between possible storylines. Consequently, the experience **doesn't have to be interrupted** for the viewer to make conscious choices about the storyline branching, unlike existing interactive VR films.

{% include googleDrivePlayer.html id='1o0tb1068OqBI5RS8BRfo7xHoDiFaxZmz/preview' %}
<div class="caption">
    Explainer video for Cinévoqué
</div>
  
 
I built the project as a plugin for Unity, with custom editor scripts that allow filmmakers to create the story graph with the timings for transitions. I also created shaders that would handle the transitions such that it happens unbeknownst to the viewer. Additionally, having a real-time application running the movie leads to some interesting affordances. For example, I had a picture of a body layered on top of the film that rotated based on the orientation of a 6DOF controller attached to the viewer's chair. Similarly, we can layer in equirectangular assets whose behavior can be scripted.

<div class="row" style="text-align:center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="/assets/img/projects/cine/chair.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    [Left] Using a 6DOF controller to rotate a body in live-action VR. [Right] Viewer facing different direction with the virtual body
</div>

Please refer to our publications to learn about the Cinévoqué's design and implementation. We had the opportunity to present our work at reputed international conferences such as VRST, VRCAI, and INTERACT. We have also been invited speakers at national and international events such as SIGCHI Asian Symposium, UNITE India and IndiaHCI.
 
 
 <div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="/assets/img/projects/cine/unite.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="/assets/img/projects/cine/vrst.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">