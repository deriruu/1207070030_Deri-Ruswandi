# 1207070030_Deri-Ruswandi
import matplotlib.pyplot as plt
%matplotlib inline

from skimage import data
from skimage.io import imread
from skimage.color import rgb2gray 
from skimage.util import invert

import numpy as np

catImage = data.cat()
coffeeImage = data.coffee()

catCropped = catImage.copy()
catCropped = catCropped[0:256,64:320]

coffeeCropped = catImage.copy()
coffeeCropped = coffeeCropped[64:256,128:320]

print('Cat Ori Shape : ',catImage.shape)
print('Cat Crop Shape : ',catCropped.shape)

print('coffee Ori Shape : ',coffeeImage.shape)
print('coffee Crop Shape : ',coffeeCropped.shape)

fig, axes = plt.subplots(2, 2, figsize=(12, 12))
ax = axes.ravel()

ax[0].imshow(catImage)
ax[0].set_title("Citra Input 1")

ax[1].imshow(coffeeImage, cmap='gray')
ax[1].set_title('Citra Input 2')

ax[2].imshow(catCropped)
ax[2].set_title("Citra Output 1")

ax[3].imshow(coffeeCropped, cmap='gray')
ax[3].set_title('Citra Output 2')
