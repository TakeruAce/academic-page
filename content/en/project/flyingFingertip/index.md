---
title: Flying at Your Fingertips
summary: Fly through 3D space with fingertip force input — published at AHs 2026
tags:
- research
date: "2026-03-16T00:00:00Z"

external_link: ""
featured: true
draft: false

image:
  caption: "Fingertip force-based 4DoF locomotion (YUBI)"
  focal_point: Smart
---

# Related Publication
This project was presented at the Augmented Humans International Conference 2026 (AHs 2026) in Okinawa.

> **[Flying at Your Fingertips: Input Mapping Strategies for Fingertip Force-Based 3D Locomotion](https://doi.org/10.1145/3795011.3795047)**
> Shun Kondoh, Takeru Hashimoto, Yutaro Hirao, Takuji Narumi
> *The Augmented Humans International Conference 2026 (AHs 2026), Okinawa, Japan, March 16–19, 2026*
> [📄 PDF](paper.pdf)

# Overview
Free 3D navigation is becoming increasingly important across applications such as VR locomotion, drone teleoperation, and remote robotics. Yet today's options each have downsides: joystick-based control takes time to master, while body-motion interfaces tend to be tiring and demand space.

This project explores **fingertip force input** as an alternative — a way to drive high-dimensional control with very small physical motion.

# YUBI: 4-DoF Locomotion via Fingertip Force
We built **YUBI**, a system that maps the direction and magnitude of forces applied by both thumbs into 3D translation + yaw (4-DoF) locomotion, and evaluated it through a tunnel-traversal task.

We compared five different mapping strategies for force-to-motion. The findings:

- Naively replicating the displacement-based mapping of a joystick on a force-input device significantly degrades performance, due to cross-axis interference.
- Our proposed **"wheel-like" redundant mapping** — which integrates 6-DoF force input from both thumbs — matched the precision of a gamepad while scoring higher on **intuitiveness** and **embodiment**.

# Design Implications
Force-input interfaces should not simply emulate the control schemes of displacement-based controllers. Leveraging **redundancy** and **real-world metaphors** instead is what allows precision, intuitiveness, and physical comfort to coexist. These findings inform the design of next-generation human interfaces that exploit our body's intrinsic sense of control — drone control, VR locomotion, and tele-robotics among them.

{{<figure src="featured.png" id="teaser" caption="Left: the fingertip force input device YUBI. Right: the tunnel-traversal evaluation task.">}}
