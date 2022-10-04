---
layout: page
title: Graphics
description: Raytracing, Raymarching, Rasterization & NaNs
img: /assets/img/projects/graph/icon.png
importance: 1
category: work
---

<div class="row" style="text-align:center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="/assets/img/projects/graph/banner.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

A compilation of the projects I worked on while learning graphics by myself.<br><br>    
### Raytracing on Multiple Weekends

I implemented a Raytracer from scratch in C++, following the [Raytracing in one weekend](https://raytracing.github.io/) ebook series. The project was a helpful refresher for the maths used in graphics and contextualized the concepts. The first book focused on implementing vector math functions, rays, ray-sphere interactions, shading, aliasing, positionable camera, and lens blur. The following images show scenes that implement these features.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/projects/graph/render.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/projects/graph/output.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

The second book covered motion blur, Bounding Volume Hierarchy, procedural textures, image texture mapping, lights, and volumes. Beyond the contents of the book, I implemented multi-threading and non-uniform volumes.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/projects/graph/diffuse.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/projects/graph/rtnw.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/projects/graph/cornell.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/projects/graph/nonuniform.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<br>  

### Raymarching to my own beat

After the raytracing projects, I have implemented a couple of shaders in Shadertoy. The first was an interactive mandelbrot set, which served as a refresher for complex math and its uses in graphics. The second shader is an interactive mandelbulb, which helped me understand raymarching and SDFs. Click the play button on the shaders below, and use arrow keys to move around. Z/X for zooming in/out.

<p style="text-align:center">
<iframe width="640" height="360" frameborder="0" src="https://www.shadertoy.com/embed/Wljczw?gui=true&t=10&paused=true&muted=false" allowfullscreen ></iframe>

<iframe width="640" height="360" frameborder="0" src="https://www.shadertoy.com/embed/tt2cDm?gui=true&t=10&paused=true&muted=false" allowfullscreen ></iframe>
</p>

After watching Pixar's Soul and reading the [paper](https://graphics.pixar.com/library/SoulVolumetricChars/paper.pdf) on their pipeline for rendering volumetric characters, I used SDF's & volumetric raymarching to create a shader that renders an animated 22 from the movie. Press play and use the same controls as that of the fractals. Additionally, clicking and dragging would control the eyes.

<p style="text-align:center">
<iframe width="640" height="360" frameborder="0" src="https://www.shadertoy.com/embed/NsjGRt?gui=true&t=10&paused=true&muted=false" allowfullscreen></iframe>
</p>

<br>  

### Rasterization
 
I followed along with Prof Cem Yuksel's Interactive Computer Graphics course online and implemented a basic rasterizer in C++ & OpenGL. I created this project before applying to the University of Utah, and will be working on this further when I officially enroll in the course.

Currently, the rasterizer supports loading and parsing .Obj files, blinn shading, textures, lights, and object transforms.

<div class="row">    
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="https://raw.githubusercontent.com/AmarnathMurugan/InteractiveGraphicsProjects/main/Pictures/prj3.gif" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="https://raw.githubusercontent.com/AmarnathMurugan/InteractiveGraphicsProjects/main/Pictures/prj4.gif" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>

</div>
