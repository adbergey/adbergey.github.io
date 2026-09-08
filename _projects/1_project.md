---
layout: page
title: AMULET
description: Acoustic metastructure for DoA estimation underwater via a single hydrophone
img: assets/img/noLidMedCyl.png
importance: 1
category: Research
---

# AMULET: Rethinking Underwater Direction Finding with a Single Receiver

## Overview

One of the quiet constraints in underwater robotics is **directional awareness**.

If you want to know where a signal is coming from underwater, the standard answer has remained largely unchanged for decades: use an array of separated hydrophones and algorithms that take advantage of the spatial differences between the received signals.

This works well, but it doesn't scale easily to the newer generations of autonomous underwater vehicles (AUVs).

Small AUVs, distributed sensor nodes, and low-power platforms simply don't have the size, weight, and power (SWaP) budget for large hydrophone arrays. Without direction-of-arrival (DoA) estimation, capabilities such as navigation, localization, and tracking become much more difficult.

**AMULET** explores a different approach: achieving accurate underwater direction-of-arrival estimation using **a single hydrophone**.

---

## A Different Way to Think About the Problem

Instead of trying to optimize an array, we asked a different question:

> **Can we achieve high direction-of-arrival accuracy using only a single receiver?**

This led us to **acoustic metastructures** — structures engineered to interact with sound in useful ways.

We developed an underwater acoustic metastructure that surrounds a single hydrophone and alters an incoming acoustic signal differently depending on the angle from which the sound arrives.

The receiver therefore doesn't simply measure the incoming sound. The **physical structure itself transforms the sound into a direction-dependent signature**.

Once these signatures are learned, the receiver can compare a new measurement against the known signatures and estimate the direction of arrival.

---

## AMULET

**AMULET** stands for **Acoustic Metastructure for Underwater Localization and Entity Tracking**.

This work was developed at the University of Washington's Department of Electrical & Computer Engineering, with the goal of creating a compact, low-cost, and low-power alternative to traditional underwater hydrophone arrays.

The system uses commodity hardware together with a custom, 3D-printable acoustic metastructure.

The work was led by **Andrew Bergey**, with **Nakul Garg** and advised by **Akshay Gadre**.

The research was accepted to **ACM/IEEE SenSys 2026**.

[Read the full paper](https://doi.org/10.1145/3774906.3802750)

[View the 3D models, code, and datasets](https://github.com/adbergey/amulet)

---

## How Does the Metastructure Work?

A key challenge is creating enough distinction between acoustic signals arriving from different directions.

Many conventional solid materials behave relatively similarly to water from an acoustic perspective. As a result, much of an incoming sound wave simply passes through the material without being significantly altered.

The key insight came from nature.

### Inspired by Marine Shells

Some marine shells use internal air cavities to create complex acoustic behavior. These cavities create strong acoustic impedance contrasts and produce complicated reverberation patterns that depend on how sound interacts with the structure.

AMULET borrows this idea.

The metastructure contains a **spiral-shaped sealed air cavity** embedded within a 3D-printed structure.

Because air and water have dramatically different acoustic impedances, the boundary between them strongly interacts with incoming sound waves.

The changing width of the air cavity creates different acoustic paths and reverberation behavior throughout the structure.

The result is a compact, passive structure that produces **distinct and repeatable acoustic signatures for different angles of arrival**.

![AMULET metastructure](assets/img/amuletPaths.png)

*The AMULET acoustic metastructure uses a structured air cavity to create direction-dependent acoustic signatures.*

---

## From Acoustic Signatures to Direction

Once the metastructure creates these direction-dependent signatures, the problem becomes one of signal processing.

The system operates in three primary steps.

### 1. Extract the Signature

Given a known transmit signal, we estimate the acoustic impulse response observed through the metastructure.

This impulse response becomes the **signature** associated with a particular direction.

### 2. Calibrate the Metastructure

We rotate the metastructure through a range of known angles using a stepper motor.

At each angle, the system records the corresponding acoustic signature.

These measurements form a **signature dictionary** mapping acoustic responses to directions.

*The metastructure is rotated through known angles during calibration to construct its directional signature dictionary.*

### 3. Match an Unknown Signal

When an unknown signal arrives, its measured signature is compared against the calibrated dictionary.

The angle associated with the most similar signature becomes the estimated direction of arrival.

In other words, rather than calculating direction from the spatial separation between multiple hydrophones, AMULET uses the **physical transformation performed by the metastructure** to encode spatial information into the received signal.

---

## Why Does This Work?

The resulting acoustic signatures have several useful properties.

### Distance Agnostic

The signatures are largely independent of the distance between the transmitter and receiver.

This means the same directional signature can remain useful even when the transmitter moves closer to or farther away from the receiver.

### Robust to Multipath

Underwater environments contain reflections from surfaces, boundaries, and other objects.

Because the useful metastructure response is relatively short in duration, many reflected copies of the signal arrive outside the primary signature region.

This allows much of the multipath energy to be rejected during processing.

The result is a system that can extract directional information without requiring a perfectly controlled acoustic environment.

---

## Experimental Evaluation

We evaluated AMULET across three different environments:

- A small desktop aquarium
- A large indoor saltwater tank
- An open-water lake deployment

We performed several experiments to understand both the accuracy and robustness of the system.

These included:

- Baseline direction-of-arrival measurements
- Cross-environment calibration
- Testing across different transmitter-receiver distances
- Repeated experiments across different days
- Complete teardown and reconstruction of the experimental setup
- Tracking experiments using moving transmitters
- Simultaneous tracking of multiple transmitters

<div class="row justify-content-sm-center">
    <div class="col-sm">
        {% include figure.liquid path="assets/img/Ocean_setup.jpg" title="Experimental Setup" class="img-fluid rounded z-depth-1" %}
        AMULET calibraiton setup in the indoor saltwater tank testbed.
    </div>
</div>

*AMULET was evaluated across controlled laboratory environments and open-water deployments.*

---

## Results

The results demonstrate that a single hydrophone can recover surprisingly accurate directional information when augmented by the metastructure.

### Key Results

| Experiment | Result |
|---|---:|
| Same-environment calibration | **~1–2° average error** |
| Cross-environment calibration | **~4.1° average error** |
| Tracking | **~2.9° median error** |
| Multiple transmitters | **Simultaneous tracking demonstrated** |

One particularly important result was the ability to calibrate the system in one environment and deploy it in another.

After calibration indoors, AMULET achieved approximately **4.1° average error** when deployed in a lake.

This suggests that the directional signatures are not merely artifacts of a particular experimental setup, but capture meaningful characteristics of the metastructure's acoustic response.

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/amuletMainResult.png" title="Baseline Results" class="img-fluid rounded z-depth-1" %}
        These results show AMULET's baseline performance across environments and testing conditions.
    </div>
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/amuletTrackingResult.png" title="Tracking Result" class="img-fluid rounded z-depth-1" %}
        This example tracking result shows that AMULET can track a cooperative transmitter across time and angle.
    </div>
</div>


## Why This Matters

This work is not simply about replacing a hydrophone array with something smaller.

It represents a different way of thinking about sensing systems.

Traditional approaches often increase capability by adding more sensors, more hardware, and more computation.

AMULET instead asks:

> **What if some of the computation could happen in the physical layer?**

The metastructure performs part of the transformation before the signal ever reaches the receiver.

This creates the possibility of **compact, passive, low-power spatial sensing** using inexpensive hardware.

For small AUVs and distributed underwater sensor networks, this could make directional acoustic sensing practical in situations where conventional hydrophone arrays are too large, expensive, or power-hungry.

---

## Future Directions

There is still considerable work to do.

One natural next step is extending AMULET from two-dimensional direction-of-arrival estimation to **full 3D direction sensing**.

We are also interested in integrating the system with mobile platforms such as:

- Autonomous underwater vehicles
- Small robotic platforms
- Divers
- Distributed underwater sensor networks

More broadly, AMULET explores how **physical structures can augment sensing capabilities without requiring additional sensors**.

The broader vision is simple:

> You don't necessarily need more sensors to get more information. Sometimes, you just need to think more carefully about how waves interact with the world.

---

## Resources

- **Paper:** *AMULET: Acoustic Metastructure for Direction-of-Arrival Estimation Underwater Using a Single Hydrophone*
- **Code, models, and datasets:** [GitHub](https://github.com/adbergey/amulet)
- **Original article:** [LinkedIn](https://www.linkedin.com/pulse/amulet-rethinking-underwater-direction-finding-single-andrew-bergey-acgmc/)

---

## Acknowledgments

This work was conducted at the **University of Washington Department of Electrical & Computer Engineering** as part of the **Networking and Emerging Wireless Technologies (NEWT) Lab**.

The project was led by **Andrew Bergey**, in collaboration with **Nakul Garg** and under the guidance of **Akshay Gadre**.
---

```
