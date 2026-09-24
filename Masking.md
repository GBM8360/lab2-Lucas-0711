# 1. Masking the Centre of k-Space

In MRI, the raw data acquired by the scanner is stored in the frequency domain, commonly known as k-space. The spatia distribution of this data follows a very specific rule. The centre of k-space contains the low-frequency information, which dictates the overall image contrast and the general shapes of the anatomical structures. Conversely,  the periphery of k-space holds  the high-frequency information, which is responsible for the sharp edges, fine contours and  intricate details of the final image. <br>
<br>
For this first manipulation, we will alter the raw data by playcing a maask directly  in the centre of k-space. <br>
By setting the data points in this central region to zero, for example by masking one half of the total number of voxels in both dimensions, we effectivly remove the low spatial frequencies. <br>
<br>
In physical terms, this central masking acts as a mathematical high-pass filter. Because the low frequencies that provide tissue contrast are eliminated, the resulting magnitude image loses its global contrast entirely. Instead, only the sharp edges and boundaries of the anatomical structures remain visible, resulting in an image that looks like a contour drawing. <br>
<br>
Please use the interactive plot below to dyamically adjust the size of the central mask. By changing these parameters, yo can observe firsthand how removing varying amounts of cantral k-space data directly impacts the resulting image contrast and structure.


:::{figure} #fig1 
:name: central-k-space-masking

Dies ist die Bildunterschrift für das interaktive k-Raum-Zentrum.
:::

## Peripheral k-Space Masking (Low-Pass Filter)

Conversely, what happens if we do the exact opposite? In this experiment, we apply a low-pass filter by keeping only the central region of k-space and masking out the periphery (setting the outer high-frequency data points to zero). <br>
<br>
Because the high frequencies represent sharp edges and fine details, removing them causes the resulting image to become significantly blurred. However, since the low frequencies in the center are preserved, the global tissue contrast remains intact. <br>
<br>
Use the slider below to gradually reduce the amount of k-space data kept in the center and observe the increasing blurriness in the spatial domain.

:::{figure} #fig2 
:name: peripheral-k-space-masking

Dies ist die Bildunterschrift für das interaktive k-Raum-Zentrum.
:::
