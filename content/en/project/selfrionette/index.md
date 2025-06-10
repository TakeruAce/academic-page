---
title: Selfrionette
summary: Achieving full-body movement and diverse haptic sensations with minimal effort
tags:
- research
date: "2024-09-27T00:00:00Z"

# Optional external URL for project (replaces project detail page).
external_link: ""
featured: true

image:
  caption: 
  focal_point: Smart

# Slides (optional).
#   Associate this project with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides = "example-slides"` references `content/slides/example-slides.md`.
#   Otherwise, set `slides = ""`.
---

# Only 30 seconds Concept Video -- dive in!
{{<youtube ZPZmRLOwJy0>}}


{{% callout note %}}
If you are interested in our Selfrionette project, please read the background information below.
{{% /callout %}}

# Selfrionette: A New VR Controller for Manipulating Full-Body Avatars with Fingertip Force

## Overview
**Selfrionette** is an innovative controller that enables users to manipulate a full-body avatar in VR with fingertip force input. This system overcomes physical and spatial constraints while achieving diverse and highly dynamic haptic interactions.

{{<figure src="media/img/selfrionette/omosa.gif">}}
<!-- {{<figure src="media/img/selfrionette/yawara.gif">}} -->

*Interaction with virtual objects using Selfrionette.*

---

## Key Features
### 1. Fingertip Force Input
Selfrionette uses **seven single-beam load cells per hand** to measure fingertip forces. These sensors are embedded in a spherical casing, allowing for natural hand postures during operation. Each load cell can detect forces of up to **20kg**, converting them into digital signals at **80Hz** via an HX711 chip, which are then read by a microcontroller.

#### Degrees of Freedom (DoF):
- **Thumb and Index Finger**: 3 DoF each (up/down, forward/backward, left/right), corresponding to arm and leg movements.
- **Pinky Finger**: 1 DoF (pressing), corresponding to object grasping.

Using both hands, users can achieve up to 14 DoF for full-body control.

{{<figure src="media/img/selfrionette/device.png" caption="Mouse-shaped Input Interface">}}


### 2. Translating Force to Motion
Forces measured at the fingertips are converted into avatar movements in VR. This translation is achieved in real-time using **inverse kinematics (IK)**.

#### Avatar Motion Generation Equation
The avatar's motion is described as follows:

{{< math >}}$$
F_v = \alpha F_l \quad \text{and} \quad m_v \ddot{x} + c \dot{x} + k(x - x_0) = F_v
$$ {{< /math >}}

- {{< math >}}$F_l${{< /math >}}: Force applied to the load cell  
- {{< math >}}$F_v${{< /math >}}: Force acting on the target point (limb endpoint) in the virtual space  
- {{< math >}}$m_v${{< /math >}}: Virtual mass  
- {{< math >}}$c, k${{< /math >}}: Damping and spring constants  
- {{< math >}}$x_0${{< /math >}}: Avatar limb's initial position  

This model allows for intuitive and highly responsive control based on fingertip force input.

### 3. Haptic Feedback Representation
In addition to motion generation, Selfrionette incorporates the simulation of haptic properties (e.g., weight, friction, elasticity) to enhance the realism of virtual object interactions.

#### Additional Forces for Haptic Feedback
The motion equation for generating haptic feedback is expressed as follows:

{{< math >}}$$
m_v \ddot{x} + c \dot{x} + k(x - x_0) = F_v + f_m
$$ {{< /math >}}

- {{< math >}}$f_m${{< /math >}}: Additional force representing haptic properties.

Each haptic property is implemented as follows:

##### 1. Weight
Weight is represented by incorporating acceleration and gravity:

{{< math >}}$$
f_m = -m \ddot{x} - m g
$$ {{< /math >}}

- {{< math >}}$m${{< /math >}}: Virtual object's mass  
- {{< math >}}$g${{< /math >}}: Gravitational acceleration  

##### 2. Friction
Surface friction is modeled as:

{{< math >}}$$
f_m =
\begin{cases}
-f_p, & |f_p| \leq \mu |f_n| \ (\text{static friction}) \\
-\mu' |f_n| \cdot \text{dir}(f_p), & |f_p| > \mu |f_n| \ (\text{kinetic friction})
\end{cases}
$$ {{< /math >}}

- {{< math >}}$f_p${{< /math >}}: Parallel force  
- {{< math >}}$f_n${{< /math >}}: Normal force  
- {{< math >}}$\mu, \mu'${{< /math >}}: Static and kinetic friction coefficients  

##### 3. Compliance
Elasticity is expressed using spring properties:

{{< math >}}$$
f_m = -k (x - x_c)
$$ {{< /math >}}

- {{< math >}}$x_c${{< /math >}}: Contact point  
- {{< math >}}$k${{< /math >}}: Spring constant  

This allows users to feel soft objects and elastic materials realistically.

---

## Publications
### UIST 2024  
- **Title**: Selfrionette: A Fingertip Force-Input Controller for Continuous Full-Body Avatar Manipulation and Diverse Haptic Interactions  
- **Authors**: Takeru Hashimoto, Yutaro Hirao  
- [Paper URL](https://doi.org/10.1145/3654777.3676409)

### SIGGRAPH Asia 2024  
- **Title**: A Demonstration of Selfrionette: A Force-Input Controller for Continuous Full-Body Avatar Manipulation and Enhanced Virtual Haptics
- **Authors**: Yutaro Hirao, Takeru Hashimoto
- [Paper URL](https://doi.org/10.1145/3681755.3688943)

### VRSJ 2024  
- **Title**: Selfrionette: Realizing Full-Body Avatar Manipulation and Diverse Haptic Interactions with Fingertip Force Input
- **Authors**: Yutaro Hirao, Takeru Hashimoto
- [Paper URL](https://conference.vrsj.org/ac2024/program/doc/3G-22.pdf)

--- 

## Awards and Grants
**Best Demo in Show Award**, SIGGRAPH Asia 2024

**ACM SIGGRAPH Special Prize**, INTERBEE x DCEXPO 2024

**NEDO Award**, INTERBEE x DCEXPO 2024

[Selected for METI's TIP Program (Technology Implementation Program) for Overseas Content Development](https://dcaj-techbiz.com/tip/tip_2024_6612/)

[Selected for NEDO Entrepreneurs Program 2025 Pioneer Course](https://nep.nedo.go.jp/selected/603e73ef-27e7-43b8-835e-6ada8894640d?fbclid=IwY2xjawK00v5leHRuA2FlbQIxMABicmlkETFmOWw4NjZZYkJCYk45VVdXAR7rMX5XYFK19gS2GGjr_gUSq10ANTxJmqf-hkfGlqVnT1wCxCmQKyP8lMfUyg_aem_IlPrSBwRR3VU-h9mTB9uaA)

--- 

## Media Coverage

### Denpa Shimbun
[Creating "Sensory Experiences": Avatar Operation and Haptic Reproduction with Selfrionette](https://dempa-digital.com/article/607509)

### Nikkan Kogyo Shimbun
[Avatar Control with Fingers: Collaborative Development by NAIST and Sony CSL](https://www.nikkan.co.jp/articles/view/00733970)

### DC EXPO 2024 Arino Iku Report
{{<youtube PcH3ritX4tM>}}


--- 

## Demonstrations
[Maker Faire Kyoto 2024](https://makezine.jp/event/makers-mfk2024/m0101/)
