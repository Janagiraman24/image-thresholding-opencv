# Image Segmentation Using Thresholding Techniques in OpenCV

## Aim

To segment an image using Global Thresholding, Adaptive Thresholding, and Otsu's Thresholding techniques using Python and OpenCV.

The program performs the following operations:

- Global Thresholding
- Adaptive Thresholding
- Otsu's Thresholding

## Software Used

- Anaconda – Python 3.7
- Jupyter Notebook / VS Code
- OpenCV (cv2)
- NumPy
- Matplotlib

## Algorithm

### Step 1:

Import the required libraries: OpenCV, NumPy, and Matplotlib.

### Step 2:

Load the input image using OpenCV.

### Step 3:

Convert the input image into grayscale format.

### Step 4: Global Thresholding

- Select a fixed threshold value.
- Apply thresholding to separate foreground and background pixels.
- Display the thresholded image.

### Step 5: Adaptive Thresholding

- Compute threshold values for small regions of the image.
- Apply Adaptive Mean Thresholding.
- Apply Adaptive Gaussian Thresholding.
- Display the segmented images.

### Step 6: Otsu's Thresholding

- Automatically determine the optimal threshold value.
- Apply Otsu's thresholding technique.
- Display the segmented image.

### Step 7:

Compare the results obtained from Global, Adaptive, and Otsu's thresholding methods.

## Program :
```python
# Step 1: Import required libraries
import cv2
import numpy as np
import matplotlib.pyplot as plt
```
```python
# Step 2: Load the input image using OpenCV
image = cv2.imread('lady.jpg')

if image is None:
    raise FileNotFoundError("image.jpg was not found. Place image.jpg in the same folder as this notebook.")
```
```python
# Step 3: Convert the input image to grayscale
gray = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)

plt.figure(figsize=(6,5))
plt.imshow(gray, cmap='gray')
plt.title('Grayscale Image')
plt.axis('off')
plt.show()
```
```python
# Step 4: Global Thresholding
threshold_value = 127
_, global_threshold = cv2.threshold(
    gray,
    threshold_value,
    255,
    cv2.THRESH_BINARY
)

plt.figure(figsize=(6,5))
plt.imshow(global_threshold, cmap='gray')
plt.title('Global Thresholding')
plt.axis('off')
plt.show()
```
```python
# Step 5: Adaptive Mean Thresholding
adaptive_mean = cv2.adaptiveThreshold(
    gray,
    255,
    cv2.ADAPTIVE_THRESH_MEAN_C,
    cv2.THRESH_BINARY,
    11,
    2
)

# Adaptive Gaussian Thresholding
adaptive_gaussian = cv2.adaptiveThreshold(
    gray,
    255,
    cv2.ADAPTIVE_THRESH_GAUSSIAN_C,
    cv2.THRESH_BINARY,
    11,
    2
)

plt.figure(figsize=(12,5))

plt.subplot(1,2,1)
plt.imshow(adaptive_mean, cmap='gray')
plt.title('Adaptive Mean Thresholding')
plt.axis('off')

plt.subplot(1,2,2)
plt.imshow(adaptive_gaussian, cmap='gray')
plt.title('Adaptive Gaussian Thresholding')
plt.axis('off')

plt.tight_layout()
plt.show()

```
```python
# Step 6: Otsu's Thresholding
otsu_threshold_value, otsu_threshold = cv2.threshold(
    gray,
    0,
    255,
    cv2.THRESH_BINARY + cv2.THRESH_OTSU
)

print("Otsu's Optimal Threshold Value:", otsu_threshold_value)

plt.figure(figsize=(6,5))
plt.imshow(otsu_threshold, cmap='gray')
plt.title("Otsu's Thresholding")
plt.axis('off')
plt.show()
```
```python
# Step 7: Compare all thresholding methods
plt.figure(figsize=(15,10))

plt.subplot(2,3,1)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title('Original Image')
plt.axis('off')

plt.subplot(2,3,2)
plt.imshow(gray, cmap='gray')
plt.title('Grayscale Image')
plt.axis('off')

plt.subplot(2,3,3)
plt.imshow(global_threshold, cmap='gray')
plt.title('Global Thresholding')
plt.axis('off')

plt.subplot(2,3,4)
plt.imshow(adaptive_mean, cmap='gray')
plt.title('Adaptive Mean Thresholding')
plt.axis('off')

plt.subplot(2,3,5)
plt.imshow(adaptive_gaussian, cmap='gray')
plt.title('Adaptive Gaussian Thresholding')
plt.axis('off')

plt.subplot(2,3,6)
plt.imshow(otsu_threshold, cmap='gray')
plt.title("Otsu's Thresholding")
plt.axis('off')

plt.tight_layout()
plt.show()

```

## Developed By

**Name:** JANAGIRAMAN M

**Register No:** 212224230101

## Output

### Original Grayscale Image

- The grayscale version of the input image is displayed.
- Serves as the input for thresholding operations.

<img width="573" height="332" alt="image" src="https://github.com/user-attachments/assets/a427027a-2fb3-4dc6-ac63-d1e2a120aa3c" />


### Global Thresholding

- Original image is displayed.
- Thresholded image is displayed.
- A fixed threshold value is used for segmentation.
- Pixels are classified as foreground or background.

<img width="572" height="325" alt="image" src="https://github.com/user-attachments/assets/021f5402-dc36-45bb-883d-446798a10f96" />

### Adaptive Thresholding

- Original image is displayed.
- Adaptive Mean Thresholded image is displayed.
- Adaptive Gaussian Thresholded image is displayed.
- Threshold values vary across different regions of the image.
- Suitable for images with uneven illumination.

<img width="1247" height="373" alt="image" src="https://github.com/user-attachments/assets/89a63c70-000e-44e9-9197-2f5fa02b042d" />


### Otsu's Thresholding

- Original image is displayed.
- Otsu segmented image is displayed.
- Optimal threshold value is calculated automatically.
- Produces improved segmentation for bimodal histograms.

<img width="593" height="365" alt="image" src="https://github.com/user-attachments/assets/3e2298a0-ed62-44e1-b6ae-3aebc2b488cd" />



## Result

Thus, image segmentation is successfully performed using **Global Thresholding, Adaptive Thresholding, and Otsu's Thresholding** techniques in OpenCV. 
