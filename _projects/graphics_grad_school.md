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

 {% include figure.html path="assets/img/projects/gradphics/sculpting.gif" title="example image" class="img-fluid rounded z-depth-1" %}<br>




### Mass-Spring System simulation

This project was built during my independent study with [Prof Yin Yang](https://yangzzzy.github.io/). The study revolved around the use of the Alternating Direction Method of Multipliers(ADMM) solver in physics-based animation.

I implemented mass-spring systems with Newton's method first as a reference, and then implemented the paper ["Fast simulation of Mass Spring Systems"](http://graphics.berkeley.edu/papers/Liu-FSM-2013-11/Liu-FSM-2013-11.pdf). In the following gif, the purple bunny is using newton's method while the orange bunny uses ADMM. They are simulated with a fixed timestep of 1/30 seconds. **Newton's method takes 20 ms while ADMM take 7 ms**.

 {% include figure.html path="assets/img/projects/gradphics/admm.gif" title="example image" class="img-fluid rounded z-depth-1" %}

<br>

### Real-time Hair Rendering & Simulation

This is a project I worked on along with [Benjamin](https://benpm.github.io/) & [Alper](https://alpers-git.github.io/personal-website/#about). 

I implemented three hair shading models:
- Kajiya-Kay
- [LUT-based Marschner's hair shading](https://developer.nvidia.com/gpugems/gpugems2/part-iii-high-quality-rendering/chapter-23-hair-animation-and-rendering-nalu-demo)
- [Procedural Hair Shading](https://blog.selfshadow.com/publications/s2016-shading-course/karis/s2016_pbs_epic_hair.pdf)

On the physics side, we implemented The [Discrete Elastic Rods](https://www.cs.columbia.edu/cg/pdfs/143-rods.pdf) model to simulate hair strands. My contributions are:
- Sphere Colliders
- [Voxel-based strand-strand repulsion](https://graphics.pixar.com/library/Hair/paper.pdf)
- [Position-Based Dynamics Length Constraint](https://matthias-research.github.io/pages/publications/FTLHairFur.pdf)
- Improvements to the stability of anisotropic rods

{% include figure.html path="assets/img/projects/gradphics/hair.gif" title="example image" class="img-fluid rounded z-depth-1" %}

<br>


### Rasterization

I implemented an OpenGl rasterizer in C++ as part of my coursework. The features implemented are:
- 3D Model loading with textures
- Blinn-Phong Shading
- Direction & Spot Lights
- Cubemaps
- Reflection of cubemap
- Planar Reflection
- Shadow Mapping
- Rigidbody physics

<div class="row">    
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/projects/gradphics/raster.gif" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/projects/gradphics/rigidbody.gif" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>

</div>
<br>

### Disk Parameterization

This was the final project I chose to do for my computational geometry course, written in Python using [ligbl](https://libigl.github.io/). I implemented tutte's embedding to parameterize a genus-0 mesh with an open boundary. Here I show how such 3D models are mapped to a 2D plane

<div class="row">    
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/projects/gradphics/tutte.gif" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/projects/gradphics/tutte2.gif" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>

</div>

I use this parameterization to remesh the geometry. This part is an implementation of the paper [Interactive Geometry Remeshing
](http://www.geometry.caltech.edu/pubs/AMD02.pdf)

{% include figure.html path="assets/img/projects/gradphics/remesh.gif" title="example image" class="img-fluid rounded z-depth-1" %}

The area of each triangle and the curvature of the original model are used to determine where the new vertices are placed. The textures generated to guide this process are shown below.

{% include figure.html path="assets/img/projects/gradphics/remeshTextures.png" title="example image" class="img-fluid rounded z-depth-1" %}

<br>

### Nerual PBR Textures 

This was the final project for my Deep Learning course built using Python and PyTorch. I created 3 deep learning models to extract PBR textures from an image by modifying the resnet34 model:

- Model that takes a lit image as input and predicts an unlit image
- Model that takes a lit image and an unlit image as inputs to generate a normal map
- Model that takes the same inputs as the previous model to generate a roughness map

Example inputs and results are shown below. I used mean-squared error loss to train the models due to time and resource constraints, and it did not yield good results. Looking at papers that tackle the same issues, it seems like a differential rendering setup is the way to go.

{% include figure.html path="assets/img/projects/gradphics/neuralpbr.png" title="example image" class="img-fluid rounded z-depth-1" %}
