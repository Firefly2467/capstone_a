---
slug: design_process_next_steps
featured_image: ../assets/images/posts/e11.png
title: Next Steps in Designing our Proof of Concept
date: 2023-11-17T06:30:05.142Z
description: Fifth blog post, details our progress towards refining our proof of concept
draft: false
language: en
author: PostureMax Team
authorimage: ../assets/images/global/logo4.png
categories: Blog
tags: Blog
---
## Proof of Concept Development
#### Posted 2023-11-17 | Previous Post: [Presenting our PDP and Gauging Peer Feedback](https://posturemax.uwtron.xyz/posts/pdp_and_peer_feedback/ "Fourth blog post, shows our PDP slides and we discuss peer feedback")

As we move closer towards building our first prototype, the team had to make key design decisions as we persue the selected "All-in-one" solution. The first step was to decompose the design into small components or sub-assemblies, where we could evaluate existing off-the-shelf parts or solutions that could be built into our design. A rudimentary "Bill of Materials" (BOM) was created to evaluate everything from displays, cameras, to single board computers (SBC), wireless communcation adaptors, AI accelerators and power circuits/supplies. 

From these lists, some items we could evaluate by collecting data from blogs or news articles, such as performance metrics of various popular SBCs running common AI benchmarks. Some key decisions were based on price, availablity, or the experience / wisdom of team member. Nonetheless, with many aspects of the device performance (for detecting posture) unknown, the team felt it would be best to verify certain concepts/components quickly, and refining the design rapidly as we gain a better understanding of the shortcomings of our initial assumptions.

Simple and bulky designs were drawn up quickly by hand to determine the mecahnical design we could expect:

![e1](https://posturemax.uwtron.xyz/assets/images/posts/e1.png "Hand Drawn Design")

But quickly developed into CAD drawings so that the team could get a feeling for the real-world dimensions of the device, an important factor for how the camera will be mounted and where it would sit on a desk compared to the user. It was determined that possibly a vertical-tilt might be needed based on the initial dimensions, and thus, a small servo was added temporarily into the first revision of the design such that it could be evaluated and removed later if no longer needed.

![e7](https://posturemax.uwtron.xyz/assets/images/posts/e7.png "Initial CAD design")

![e4](https://posturemax.uwtron.xyz/assets/images/posts/e4.png "Calculated Real-World dimensions")

With a Raspberry Pi 4 selected as an initial SBC, and the OAK-D-Lite camera (with onboard AI accelerator), the team quickly evaluated the power and circuit requirements for running a few displays and extra sensors. Noting that depending on the sensors chosen, the SBC would need a logic-level shifter and ADC added (as these are missing from the SBC), a few example sensors were added into the circuit to visualize these possible requirements.

![e7](https://posturemax.uwtron.xyz/assets/images/posts/e7.png "Example Electrical Circuit")

While the OAK-D-Lite camera would take some time to procure, part of the team focused on validating intial software ideas regarding the posture tracking with USB web cameras. Evaluating existing body detection/tracking software helped quickly guide the team towards a general understanding of the software pipeline/loop that would be at the core of the prototype. PoseNet Demo shown in image below:

![e12](https://posturemax.uwtron.xyz/assets/images/posts/e12.png "PoseNet Demo")

The performance of the PoseNet demo helped reinforce initial assumptions arround the quality / framerate of the camera required for the device, and the compute performance required on the SBC such that the device could run the software at a reasonable level of accuracy and performance. Several aspects of the software pipeline were explored, with the feedback to the user being of the highest importance:

![e10](https://posturemax.uwtron.xyz/assets/images/posts/e10.png "User Feedback")

With the core components ordered and slowly shipping, we continue our work into exploring our user-facing application and software-stack, driving available displays, testing additional sensors and electronic components. As we build a better understanding of the core components of our design, we may look towards slimming the device down, creating tighter integrations, and revisiting component selection.

