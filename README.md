# 8-THRESHOLDING_
Name : Jenittan Jose J B

Reg no : 212224240063

## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm

Step1:
Load the necessary packages.

Step2:
Read the Image and convert to grayscale.

Step3:
Use Global thresholding to segment the image.

Step4:
Use Adaptive thresholding to segment the image.

Step5:
Use Otsu's method to segment the image and display the results.

## Program

```python
# developed by :Jenittan Jose J B 
# Reg no : 212224240063

import cv2
import numpy as np
import matplotlib.pyplot as plt

# Read the Image and convert to grayscale

image = cv2.imread("/content/Screenshot 2025-11-05 191144.png")  # Replace with your image file path
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)  # Convert to grayscale
plt.subplot(2, 2, 1)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Convert from BGR to RGB for display
plt.title("Original Image")
plt.axis('off')

# Use Global thresholding to segment the image

_, global_thresholded = cv2.threshold(gray_image, 127, 255, cv2.THRESH_BINARY)

# Use Adaptive thresholding to segment the image

adaptive_thresholded = cv2.adaptiveThreshold(gray_image, 255, cv2.ADAPTIVE_THRESH_GAUSSIAN_C, cv2.THRESH_BINARY, 11, 2)

# Use Otsu's method to segment the image 

_, otsu_thresholded = cv2.threshold(gray_image, 0, 255, cv2.THRESH_BINARY + cv2.THRESH_OTSU)


# Display the results

# Global Thresholding
plt.subplot(2, 2, 2)
plt.imshow(global_thresholded, cmap='gray')
plt.title("Global Thresholding")
plt.axis('off')

# Adaptive Thresholding
plt.subplot(2, 2, 3)
plt.imshow(adaptive_thresholded, cmap='gray')
plt.title("Adaptive Thresholding")
plt.axis('off')

# Otsu's Method
plt.subplot(2, 2, 4)
plt.imshow(otsu_thresholded, cmap='gray')
plt.title("Otsu's Method")
plt.axis('off')

# Show the plot
plt.tight_layout()
plt.show()


```
## Output

### Original Image
<img width="346" height="272" alt="Screenshot 2025-11-12 214940" src="https://github.com/user-attachments/assets/2170fad7-0982-4732-a11e-e580a453b45e" />

### Global Thresholding
<img width="329" height="277" alt="Screenshot 2025-11-12 214948" src="https://github.com/user-attachments/assets/ff350b83-0c52-4964-b6c8-4f1b27f599ab" />


### Adaptive Thresholding
<img width="324" height="259" alt="Screenshot 2025-11-12 214957" src="https://github.com/user-attachments/assets/95ca6106-a583-4ce7-9d62-f561f9a1cab9" />


### Optimum Global Thesholding using Otsu's Method

<img width="323" height="270" alt="Screenshot 2025-11-12 215003" src="https://github.com/user-attachments/assets/59078ac8-8e71-4913-91b1-7277838c7fb5" />


## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
