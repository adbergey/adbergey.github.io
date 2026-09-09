---
layout: page
title: Husky Satellite Monitor
description: Developed a low-cost SDR based Starlink satellite downlink testbed, capable of receiving, tracking, and identifying KU-band signals
img: assets/img/sdr_challenge.jpg
importance: 2
category: Research
related_publications: false
---

During the 2025-2026 academic year I participated on a team of UW grad students developing a low-cost SDR based satellite downlink testbed. This was part of an annual SDR Challenge hosted by the US Air Force Research Lab (AFRL). Using cheap components (~$50), my team built an end-to-end pipeline which would record steady frequency leakage tones (at the satellite's carrier frequency) that appear during certain Starlink transmissions. We then built a Doppler predictor which gathered publicly available satellite trajectory information and identified candidates that would be nearby during a recording. Then we correlated the extracted Doppler curves from the experimental data and the predictor to identify which satellite(s) was passing overhead.

We were awarded the Best Demonstration Award at the final showcase. 



<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/sdr_waterfall.png" title="Waterfall Plot" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/sdr_predictor.png" title="SDR Predictor" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/sdr_identifying.png" title="Identifying Satellites" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Some highlights from the project: Left: A waterfall plot featuring several Starlink satellites passing overhead, showing the signature Doppler S-curve as the relative velocity changes at it passes overhead. Middle: A custom built Doppler predictor which uses public satellite trajectory data to estimate when and where satellites will pass overhead. Right: An example of our full pipeline matching our recorded data to the predicted satellites with high accuracy.
</div>
