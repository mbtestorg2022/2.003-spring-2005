---
content_type: page
parent_title: Study Materials
parent_uid: a7a8f9ef-1f9b-6ce1-6418-f519b9fd5b7a
title: Nonlinear Control
uid: 73744b95-66b8-8de0-1f15-daae37af3278
---

[Main]({{< baseurl >}}/pages/study-materials/main) | [Hardware]({{< baseurl >}}/pages/study-materials/hardware) | [System Model]({{< baseurl >}}/pages/study-materials/system_model) | [Linearized Control]({{< baseurl >}}/pages/study-materials/linear_control) | Nonlinear Control | [Movies]({{< baseurl >}}/pages/study-materials/movies) | [Technical Details]({{< baseurl >}}/pages/study-materials/tech_details) | [Credits]({{< baseurl >}}/pages/study-materials/credits)

While linearizing the behavior of the plant and applying traditional linear control methods is an effective method of controlling the system, it is only effective around the chosen opperating point. Large deviations from this point lead to instabilities and the eventual failure of the system to remain in the desired position. Our demonstration maglev system operates over a wide range of positions, with gaps from about 5 to 15 mm. This span is too great for a linearized control system to handle, requiring a nonlinear control system.

The basics of our non-linear control system are as follows. The chief difference is that the nonlinear design has an extra nonlinear block between the linear controller and the plant. This extra element combines with the plant to form an effectively linear system, which is controlled in the traditional manner.

![](/courses/mechanical-engineering/2-003-modeling-dynamics-and-control-i-spring-2005/study-materials/nlblock1.jpg)

Fig. N1.

The inputs on the nonlinear block are the measured position of the ball and the force requested by the linear section of the control system. The computer sums the desired force and the constant gravitational force to produce the needed magnetic force:

![](/courses/mechanical-engineering/2-003-modeling-dynamics-and-control-i-spring-2005/study-materials/neq1.jpg)

Eq. N1.

![](/courses/mechanical-engineering/2-003-modeling-dynamics-and-control-i-spring-2005/study-materials/neq2.jpg)

Eq. N2.

![](/courses/mechanical-engineering/2-003-modeling-dynamics-and-control-i-spring-2005/study-materials/neq3.jpg)

Eq. N3.

Based on the magnetic force needed, the computer takes the measured distance of the ball from the magnet and calculates the current needed to supply that force at the given distance via

![](/courses/mechanical-engineering/2-003-modeling-dynamics-and-control-i-spring-2005/study-materials/neq4.jpg)

Eq. N4.

Success in using this method of control is very dependent on having an accurate model of the system's behavior. The construction of such a model is demonstrated in Yi Xie's thesis, in the [technical details]({{< baseurl >}}/pages/study-materials/tech_details) section.