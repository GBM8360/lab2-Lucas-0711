# 3. Simulation of Patient Motion (Head Rotation)

In clinical magnetic resonance imaging, patients rarely remain perfectly still throughout the entire scan. Any involuntary movement during data acquisition introduces inconsistencies into k-space, resulting in severe image artifacts.

**The Experiment:**
Assuming a Cartesian acquisition scheme where k-space is filled line by line, we simulate a sudden head rotation. Specifically, after the acquisition of the central lines plus a small offset (5 lines near the center), we imagine the patient suddenly rotates their head by a specific angle and then remains still. 

**The Physical Effect (Motion Artifacts):**
Because k-space data is acquired sequentially over time, the first part of k-space represents the stationary head, while the latter part represents the rotated position. This abrupt transition and mismatch in the frequency domain leads to prominent **ghosting artifacts** and signal smearing along the phase-encoding direction when the inverse Fourier transform is applied.

Use the interactive slider below to vary the rotation angle. You can observe how increasing the severity of the head movement alters the composite k-space and distorts the final reconstructed image magnitude.

:::{figure} #fig4 
:name: head-rotation

Dies ist die Bildunterschrift für das interaktive k-Raum-Zentrum.
:::
