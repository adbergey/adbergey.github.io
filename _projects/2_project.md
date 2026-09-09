---
layout: page
title: Underwater ToF Camera
description: Developed a real time ToF camera for underwater applications
img: assets/img/tof_pool.jpg
importance: 3
category: Research
related_publications: false
---

Throughout my undergraduate years at Grove City College (2022-24), I worked with Prof. Luke Rumbaugh developing an underwater time-of-flight (ToF) camera. We took a commercial off the shelf camera which used infrared illumination, and built out hardware to allow the camera to operate using green lasers (an optimal wavelength for underwater imaging).  We then packaged all of the hardware to be deployed on a BlueRobotics BlueROV2.
Check out this video from our collaborators at the U.S. Naval Air Warfare Center Aircraft Division which features my team demonstrating our camera in a Navy test tank. 

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        <div style="position: relative; padding-bottom: 56.25%; height: 0; overflow: hidden; width: 100%;">
            <iframe
                src="https://www.youtube.com/embed/90qg-l9EXGQ?si=z6DQSHJZzeZsxI7Q"
                title="AMULET project demonstration"
                style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"
                frameborder="0"
                allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
                allowfullscreen>
            </iframe>
        </div>
    </div>
</div>


<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/tof_pool.jpg" title="ToF Camera on ROV" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/tof_SigBoard.png" title="Custom Signal and Power PCB" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/tof_pipes.png" title="ToF Images" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Some highlights from the project: Left: The ToF camera mounted on an ROV deployed in a pool. Middle: A signal and power redistribution breakout PCB I designed. Right: Some example images showing the depth data captured by the camera.
</div>
