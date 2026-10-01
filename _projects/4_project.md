---
layout: page
title: SARDINE
description: Single-hydrophone AMULET for ROV Doppler-Informed Navigation Estimation
img: assets/img/sardineTeaser.png
importance: 2
category: Research
related_publications: false
---

This project is a follow-up to the AMULET project. We extended the signature dictionary to 2.5D, including a limited range of elevation angles allowing us to track a moving ROV in 3D in a limited region. Additionally, we developed an algorithm for jointly estimating the Doppler velocity along with heading, improving accuracy and providing velocity for free.

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        <div style="position: relative; padding-bottom: 56.25%; height: 0; overflow: hidden; width: 100%;">
            <iframe
                src="https://www.youtube.com/embed/W9CjxmJ4NKY?si=1D9PlNdZzmA1P_BE"
                title="AMULET project demonstration"
                style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"
                frameborder="0"
                allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
                allowfullscreen>
            </iframe>
        </div>
    </div>
</div>


Here is a nice visualization of one of our tracking results:

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        <div style="position: relative; padding-bottom: 56.25%; height: 0; overflow: hidden; width: 100%;">
            <iframe src="/widgets/score_prism_viewer.html" width="100%" height="720"
                    style="border:0" loading="lazy" allowfullscreen
                    title="SARDINE 3D Matching Score Viewer"></iframe>
            <p><a href="/viz/score_prism_viewer.html">Open the viewer full screen</a></p>
        </div>
    </div>
</div>



<!--
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
-->
