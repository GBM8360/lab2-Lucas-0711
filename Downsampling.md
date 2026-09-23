# 2. k-Space Downsampling and Aliasing

To accelerate data acquisition in magnetic resonance imaging, we often reduce the number of sampled k-space lines. This process is known as downsampling. In this experiment, we simulate downsampling by skipping every $n$-th row in k-space along one direction.

**The Physical Effect (Aliasing):**
According to the Nyquist-Shannon sampling theorem, reducing the sampling frequency in k-space decreases the effective Field of View (FOV) in the spatial domain. When k-space is downsampled by a factor of two, the FOV is effectively cut in half. If the underlying anatomical structure extends beyond this reduced FOV, the peripheral tissues wrap around and superimpose onto the opposite side of the image. This artifact is known as **aliasing** or **wrap-around**.

Use the interactive slider below to increase the downsampling factor. Watch how skipping k-space lines leads to a smaller effective matrix and observe the classic aliasing artifacts appearing in the magnitude image.
