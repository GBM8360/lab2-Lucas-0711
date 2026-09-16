I loaded the raw complex k-space array and calculated its magnitude. Because in k-space data the centre contains the majority of the signal while the edges are very faint, applying a logarithmic transformation compresses the intensity scale. This makes the high-frequency information in the periphery visible to the human eye.
I used a 2D Inverse Fast Fourier Transform to convert the spatial frequencies back into an anatomical image. I applied 'ifftshift' before the transformation to move the low frequencies from the centre to the corners and 'fftshift' afterward to correctly re-centre the reconstructed image.
From the resulting complex image array I calculated the absolute value to generate the standard magnitude image (anatomy) and extracted the complex angle to display the phase image.
````python
import numpy as np
import matplotlib.pyplot as plt

# 1. Load the data
file_path = 'kspace_combined.npy'
k_space = np.load(file_path) 

# 2. Calculate Magnitude and Log Magnitude of k-space
k_space_mag = np.abs(k_space)
k_space_log_mag = np.log(k_space_mag + 1e-5) # + constant to avoid log(0)

# 3. Transform to Image Space
# Shift center to corners -> Inverse FFT -> Shift corners back to center
img_space = np.fft.fftshift(np.fft.ifft2(np.fft.ifftshift(k_space)))

# 4. Extract Magnitude and Phase of the reconstructed image
img_mag = np.abs(img_space)
img_phase = np.angle(img_space)

# 5. Visualize the results
fig, ax = plt.subplots(2, 2, figsize=(10, 8))
ax[0, 0].imshow(k_space_mag, cmap='gray')
ax[0, 0].set_title('Magnitude of k-space')

ax[0, 1].imshow(k_space_log_mag, cmap='gray')
ax[0, 1].set_title('Log Magnitude of k-space')

ax[1, 0].imshow(img_mag, cmap='gray')
ax[1, 0].set_title('Image Space: Magnitude')

ax[1, 1].imshow(img_phase, cmap='gray')
ax[1, 1].set_title('Image Space: Phase')

plt.tight_layout()
plt.show()
