# 3. Simulation of Patient Motion

## Head Rotation
In clinical magnetic resonance imaging, patients rarely remain perfectly still throughout the entire scan. Any involuntary movement during data acquisition introduces inconsistencies into k-space, resulting in severe image artifacts.

**The Experiment:**
Assuming a Cartesian acquisition scheme where k-space is filled line by line, we simulate a sudden head rotation. Specifically, after the acquisition of the central lines plus a small offset (5 lines near the center), we imagine the patient suddenly rotates their head by a specific angle and then remains still. 

**The Physical Effect (Motion Artifacts):**
Because k-space data is acquired sequentially over time, the first part of k-space represents the stationary head, while the latter part represents the rotated position. This abrupt transition and mismatch in the frequency domain leads to prominent **ghosting artifacts** and signal smearing along the phase-encoding direction when the inverse Fourier transform is applied.

Use the interactive slider below to vary the rotation angle. You can observe how increasing the severity of the head movement alters the composite k-space and distorts the final reconstructed image magnitude.

:::{figure} #fig4 
:name: head-rotation

Patient rotation their head.
:::

## Head Translation
Instead of a rotation, patients often shift their head laterally during an acquisition. According to the Fourier shift theorem, a spatial translation by $\Delta x$ introduces a linear phase ramp in the frequency domain, mathematically described by the Fourier transform equation:

$$S(k_x, k_y) = \iint \rho(x, y) e^{-i 2\pi (k_x x + k_y y)} dx dy$$

When interacting with the slider below, you might notice that the composite k-space plot does not visually change. This is physically accurate! A spatial translation only alters the complex *phase* of the k-space data, leaving its amplitude (magnitude) completely unchanged. The severe ghosting artifacts in the reconstructed image are caused entirely by the sudden phase mismatch where the stationary and shifted k-space lines are spliced together, an inconsistency that remains completely invisible in a standard magnitude plot.

:::{figure} #fig5 
:name: head-translation

Patient moving their head laterally.
:::
