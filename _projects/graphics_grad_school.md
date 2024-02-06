---
layout: page
title: Grad-phics
dates: Aug 2022 - Present
description: Advanced graphics projects in grad school
img: /assets/img/projects/gradphics/icon.png
importance: 1
category: work
---

<div class="row" style="text-align:center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="/assets/img/projects/gradphics/banner.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

A compilation of the projects I worked on during my Master's at the University of Utah<br><br>    
### 3D Modelling Research

The goal of this research project is to improve the ease of 3d modelling with a different way of interaction. I have been working on this project with [Benjamin Mastripolito](https://benpm.github.io/) advised by [Prof Cem Yuksel](http://www.cemyuksel.com/) since fall 2023. 

The project is still in its early stages, and the only major contribution I can talk about is my implementation of sculpting using compute shaders. No vertex data is communicated between the CPU & GPU, the compute shaders directly modify the vertex buffers of the model. I've implemented **clay brush**, **symmetry**, and **masking** at the moment. More features will be added soon.

 {% include figure.html path="assets/img/projects/gradphics/sculpting.gif" title="example image" class="img-fluid rounded z-depth-1" %}


### Mass-Spring System simulation

This project was built during my independent study with [Prof Yin Yang](https://yangzzzy.github.io/). The study revolved around the use of the Alternating Direction Method of Multipliers(ADMM) solver in physics-based animation.

I implemented mass-spring systems with Newton's method first as a reference, and then implemented the paper ["Fast simulation of Mass Spring Systems"](http://graphics.berkeley.edu/papers/Liu-FSM-2013-11/Liu-FSM-2013-11.pdf). In the following gif, the purple bunny is using newton's method while the orange bunny uses ADMM. They are simulated with a fixed timestep of 1/30 seconds. **Newton's method takes 20 ms while ADMM take 7 ms**.

 {% include figure.html path="assets/img/projects/gradphics/admm.gif" title="example image" class="img-fluid rounded z-depth-1" %}

<!-- 

### Hair Rendering & Simulation

### Rasterization

### Disk Parameterization

### Nerual PBR Textures -->