I loaded the raw complex k-space array and calculated its magnitude. Because in k-space data the centre contains the majority of the signal while the edges are very faint, applying a logarithmic transformation compresses the intensity scale. This makes the high-frequency information in the periphery visible to the human eye.
I used a 2D Inverse Fast Fourier Transform to convert the spatial frequencies back into an anatomical image. I applied 'ifftshift' before the transformation to move the low frequencies from the centre to the corners and 'fftshift' afterward to correctly re-centre the reconstructed image.
From the resulting complex image array I calculated the absolute value to generate the standard magnitude image (anatomy) and extracted the complex angle to display the phase image.
```{code-cell} python
:label: myFigure
import plotly.graph_objects as go
import numpy as np
import matplotlib.pyplot as plt

# 1. Load the k-space data
k_space = np.load('kspace_combined.npy')

# 2. Downsample k-space by half in one direction (take every 2nd row)
k_space_downsampled = k_space[::2, :]

# 3. Transform back to image space
img_downsampled = np.fft.fftshift(np.fft.ifft2(np.fft.ifftshift(k_space_downsampled)))
img_mag = np.abs(img_downsampled)

# 4. Visualize
fig, ax = plt.subplots(1, 2, figsize=(10, 5))

ax[0].imshow(img_mag, cmap='gray')
ax[0].set_title('Image Magnitude')

ax[1].imshow(np.log(np.abs(k_space_downsampled) + 1e-5), cmap='gray')
ax[1].set_title('Downsampled k-space')

plt.show()
```
