---
content_type: page
parent_title: Study Materials
parent_uid: a7a8f9ef-1f9b-6ce1-6418-f519b9fd5b7a
title: Hardware
uid: 7772984a-0715-ec47-488a-c34f735f05c9
---

[Main]({{< baseurl >}}/pages/study-materials/main) | Hardware | [System Model]({{< baseurl >}}/pages/study-materials/system_model) | [Linearized Control]({{< baseurl >}}/pages/study-materials/linear_control) | [Nonlinear Control]({{< baseurl >}}/pages/study-materials/nonlinear_cont) | [Movies]({{< baseurl >}}/pages/study-materials/movies) | [Technical Details]({{< baseurl >}}/pages/study-materials/tech_details) | [Credits]({{< baseurl >}}/pages/study-materials/credits)

The two major sections of the Levitator are the plant/sensor structure and the electronics and computer which control the structure.

Plant
-----

{{< resource "51cf2445-8958-d508-6a5c-df39c8231dde" >}}

Levitator in action (above) and its schematic representation (below).

{{< resource "c745922d-2b56-c5aa-4b79-aa4317b979f4" >}}

The plant consists of the actuator, an iron-core electromagnet and the steel ball bearing levitated by the electromagnet, along with the sensor that sends position to the control circuitry.

Current through the coils of the electromagnet induces a magnetic field in the iron core. In conjunction with the sensor and control electronics, the electromagnet exerts a force on the steel ball so as to keep it floating at a given height.

To control the position of the ball, the control electronics need to know the actual position of the ball at any given time. In this device, position is sensed by a light source and detector acting in combination. Light from the source striking the detector creates a current which is transduced into a voltage. The higher the ball is, the less light passes above the ball to the detector, translating to correspondlingly less voltage. In the control electronics, this voltage is translated into a position reading.

Control Electronics
-------------------

{{< resource "9dc1a7fa-9388-95fb-14c0-d78c4855eb27" >}}

Control circuitry, with the plant structure.

The control circuitry consists of a set of power supplies and amplifiers connected to a control computer. The control computer is a dedicated digital signal processor (DSP), programmed through the laptop. The power supplies and amplifiers receive the signal from the position sensor and send power to the actuator. An input/output box wired to the analog to digital and digital to analog converters on the computer allows the power electronics and the computer to talk to one another. In the photograph above, the ball rests on a micrometer/force measurement apparatus used in calibrating the system.

{{< resource "3cda07b0-1c0b-6126-c45a-68a89bba61dd" >}}

The power electronics box.

Combining the plant and control electronics, the schematic for the whole system is:

{{< resource "5344ad53-4e9a-b158-7f14-9ceca4b14490" >}}