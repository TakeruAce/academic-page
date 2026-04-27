---
title: Haptic Avatar
summary: A body whose physical "feel" changes with the avatar — published at ISMAR 2025
tags:
- research
date: "2025-09-14T00:00:00Z"

external_link: ""
featured: true
draft: false

image:
  caption: 
  focal_point: Smart
---

# Related Publication
This project's outcome was presented at ISMAR 2025.

> **[Move Like an Ammonite: Personalizing Force Feedback for Avatar Embodiment in Virtual Reality](https://doi.org/10.1109/ISMAR67309.2025.00098)**
> Shun Kondoh, Takeru Hashimoto, Takuji Narumi
> *2025 IEEE International Symposium on Mixed and Augmented Reality (ISMAR), pp. 899–909*

# Concept: Haptic Avatar
Advances in haptic display technology now let us recreate experiences such as touching objects or holding tools inside virtual reality. Until now, haptic technology has been used mostly to simulate the interaction between a human and the physical world.

In parallel, VR has made it possible to inhabit avatars whose body characteristics differ from our own. By altering not only an avatar's appearance but also the wearer's proprioception (the internal sense of one's body), we can begin to evoke the feeling of transforming into an entirely new body.

Our goal is to create experiences that go beyond the physical limits of the human body.

# Body Movement Reconstruction — "Move Like an Ammonite"
In our ISMAR 2025 paper, we designed force feedback that produces motion sensations matching an avatar whose form differs sharply from the human body — like an ammonite.

In the experiment, we prepared **four avatars** whose body structures gradually depart from a typical human form (standard human → robotic → non-human → ammonite), and designed force feedback tailored to the embodiment of each.
{{<figure src="4avatars.png" id="4avatars" caption="The four avatars used in our experiment, ordered from human-like to ammonite-like.">}}

By injecting force feedback at strategically chosen moments during a user's movement, we evoke the perception that the user's *own* body has changed its physical properties — rather than that an external force is being applied. We call this change in the relationship between body sensation and movement **Body Movement Reconstruction**. Internally, this is implemented by reusing impedance control, which represents the static properties of objects as force information.

Building on this, the paper proposes **Personalized Force Feedback**: a method that uses Bayesian optimization to tune force feedback parameters per user, so that the embodiment experience converges to each individual's most immersive setting. This makes the **sense of body ownership** of the non-human body markedly stronger.
{{<figure src="media/img/somatoshift/heavy_light.png" id="heavy_light">}}

# Hardware
The wearable force-feedback device used in this project is introduced on a separate page.
