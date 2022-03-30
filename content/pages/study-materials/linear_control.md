---
content_type: page
parent_title: Study Materials
parent_uid: a7a8f9ef-1f9b-6ce1-6418-f519b9fd5b7a
title: Linearized Control
uid: 80cbfe73-1932-d102-278f-8a2130fc3b1e
---

[Main]({{< baseurl >}}/pages/study-materials/main) | [Hardware]({{< baseurl >}}/pages/study-materials/hardware) | [System Model]({{< baseurl >}}/pages/study-materials/system_model) | Linearized Control | [Nonlinear Control]({{< baseurl >}}/pages/study-materials/nonlinear_cont) | [Movies]({{< baseurl >}}/pages/study-materials/movies) | [Technical Details]({{< baseurl >}}/pages/study-materials/tech_details) | [Credits]({{< baseurl >}}/pages/study-materials/credits)

Linearization
-------------

With the system model in hand we can turn our attention to control issues. Before a control scheme can be designed and implemented for this magnetic levitator, however, the equations of motion must be set in a form conducive to control. Unlike a mass, spring, dashpot system or an LRC circuit, the equation of motion of this levitator is nonlinear in both the input variable (i) and the state variable (x). The simplest solution to this is to linearize the equation of motion around a desired operating point, then apply traditional linear controls methods. The validity of this approach is restricted to small motions about the operating point. However, the advantages of working with a linear model mean that this technique is frequently applied in practice.

In the [modeling]({{< baseurl >}}/pages/study-materials/system_model) section, the equations pertaining to the system are given as:

{{< resource "701633de-ac79-7ac2-520b-49f7c38b3114" >}}

Eq. M1.

{{< resource "9669154c-4649-0247-72e1-e445249597a3" >}}

Eq. M2.

{{< resource "18d8d15e-d078-e595-ea7b-f45942af3124" >}}

Eq. M3.

The first step in linearizing the equation is to approximate i and x as:

{{< resource "bf9684f4-b644-3989-a75b-56de2963d925" >}}

Eq. L1.

where the bar (-) is the value at the operating point, and the tilde (~) term represents incremental variations around this point. We assume {{< resource "91cbcf96-be18-dc4e-9c33-946e7fb96770" >}} and {{< resource "8d1f1f50-9b6b-d97b-89c5-f50bedc5e496" >}}. Substituting (L1) into (M2) and taking the Taylor expansion yields:

{{< resource "7ba9a9e9-8cb3-52e0-8721-bb7cb3143e85" >}}

Eq. L2.

For our chosen first order aproximation, the higher order terms drop out. The two partial differential terms in the equation solve as:

{{< resource "7f5ca87d-a99f-a974-4dd0-78b1256e5621" >}}

Eq. L3.

Substituting (L3) into (L2) while dropping the higher order terms leaves:

{{< resource "cd1b68fb-20a2-3242-e5be-59639ac50db2" >}}

Eq. L4.

By definition, the equilibrium point is where there is no net acceleration, and where the incremental terms are equal to zero. At this point, (L4) becomes:

{{< resource "ea35d5f2-5284-34ab-7de8-78699fc62f18" >}}

Eq. L5.

Putting (L5) into (L4) and rearranging, the equation of motion takes on the familiar form of:

{{< resource "4e8ddbaf-54a5-84af-5190-7ab3cd8e95bd" >}}

Eq. L6.

The poles of this system are at:

{{< resource "f3912e6f-b3a2-74f3-6987-fbf0049c5695" >}}

Eq. L7.

For various lengths of the airgap, the pole locations are:

{{< resource "1f7c27c8-4679-7892-3a67-ffb63795e3b8" >}}

Fig. L1.

Plotting pole spacing against air gap distance results in the curve:

{{< resource "08e3758a-6eb9-52e5-6263-72aa011c7483" >}}

Fig. L2.

If the terms are properly expanded, the system pole locations can be shown to depend only on upon gravity and the operating air gap:

{{< resource "37b20894-3f08-10df-f75d-80cb76b5ab5b" >}}

Eq. L8.

When a properly designed controller is added to an unstable system, it serves to move right-half plane poles into the left half plane. The closer the unstable pole starts to zero, the easier it is to pull it across to stability. As the above relationship between pole location and opperating point shows that pole distance from zero decreases with increasing distance between the actuator and the ball. Large distances are, however, impractical in terms of building the actuator, as the magnetic force falls off with the square of the opperating point distance, requiring a commesurate increase in current to balance the forces.

Control
-------

Now that the system has been linearized, a controller can be applied to it. Various methods can be applied to show that a simple proportional gain controler is insufficient for this system and would not do better than to place both poles on the imaginary axis. Adding a zero to the system through the application of a proportional-differential controller can be shown by the same methods to pull the poles into the left-half plane.

The block diagram below represents the whole system. C1 represents the constant for converting between position and voltage in the position sensor and in the input. The other three blocks, from left to right, are the controller, the current supply and the plant.

{{< resource "a5c372a3-5ee4-b4fa-2e61-99c947e72577" >}}

Fig. L3.

For the purposes of examining the behavior of the controlled system, it is useful to consolidate the block diagram before analyzing it. The dynamics of available current controls are sufficiently faster than those of the plant that the block can be treated as a constant multiplier and incorporated into the controller gain. C1 and k2 can be similarly incorporated. The resulting block diagram, with G representing the combination of the constant multipliers, is:

{{< resource "fa9ea6b5-101b-a95d-f3c9-6ec5f459f568" >}}

Fig. L4.

Applying Black's Law to the simplified block diagram results in the following transfer function:

{{< resource "0778d425-ef28-fd7e-f878-04596c4e0acb" >}}

Eq. L9.

The mechanical equivalent system to the linearized model is:

{{< resource "76e8e235-355f-26c9-f24c-a4e0ccebaf1f" >}}

Fig. L5.

For G>k1, the system can be seen from the equation or the equivalent model to be stable. Putting the equation into cannonical form,

{{< resource "8bd7c6e2-2382-fe25-ab19-fd4dde8bf9c9" >}}

Eq. L10.

the steady state gain is seen to be K/(K-k1), which approaches unity as K gets large. Note that unlike a traditional second order system, the steady state gain here approaches unity from infinity, rather than from a fraction less than one. This effect is a result of the "negative spring" in the linearized equation of motion (Eq. L6).

Where steady state performance improves with increasing G, transient performance depends on all of the system's characteristics. Once a value of G is chosen to provide the acceptable steady state performance, however, {{< resource "460536cf-7a8b-58c9-8af5-5db5b18a7060" >}} is the only undefined term in the transfer function, and can be solved for to optimize transient performance.

The poles of (Eq. L9) are located at

{{< resource "c05c09a9-58d7-bb04-9f4a-d9ef3563cdf8" >}}

Eq. L11.

Critical damping occurs when the poles are co-located, where

{{< resource "4a2c12ca-6f8c-2fcd-d203-61f2eee4c516" >}}

Eq. L12.

Solving for {{< resource "460536cf-7a8b-58c9-8af5-5db5b18a7060" >}} provides

{{< resource "89da7469-9444-1414-d7c1-e0165b60db5a" >}}

Eq. L13.

It should be noted that the controller presented above is not physically realizable, as it contains an isolated zero, which gives gain as ever increasing with frequency. A more realistic controller would have a transfer function resembling

{{< resource "5262eec3-6d5e-d497-220a-d66a4828c23a" >}}

Eq. L14.