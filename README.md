## Image Segmentation Using Thresholding Techniques in OpenCV

## Aim
To segment an image using Global Thresholding, Adaptive Thresholding, and Otsu's Thresholding techniques using Python and OpenCV.

The program performs the following operations:

-Global Thresholding
- Adaptive Thresholding
- Otsu's Thresholding
## Software Used
- Anaconda – Python 3.7
- Jupyter Notebook / VS Code
- OpenCV (cv2)
- NumPy
- Matplotlib
## Algorithm
Step 1:
Import the required libraries: OpenCV, NumPy, and Matplotlib.

Step 2:
Load the input image using OpenCV.

Step 3:
Convert the input image into grayscale format.

Step 4: Global Thresholding
Select a fixed threshold value.
Apply thresholding to separate foreground and background pixels.
Display the thresholded image.

Step 5: Adaptive Thresholding
Compute threshold values for small regions of the image.
Apply Adaptive Mean Thresholding.
Apply Adaptive Gaussian Thresholding.
Display the segmented images.

Step 6: Otsu's Thresholding
Automatically determine the optimal threshold value.
Apply Otsu's thresholding technique.
Display the segmented image.

Step 7:
Compare the results obtained from Global, Adaptive, and Otsu's thresholding methods.

## Program
Developed By
Name: Kruthika R
Register No: 212225240075
## Import Libraries
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
```
## Read and Display Original Grayscale Image
```
img = cv2.imread('boy.jpg')

gray = cv2.cvtColor(img, cv2.COLOR_BGR2GRAY)

plt.figure(figsize=(6, 5))
plt.imshow(gray, cmap='gray')
plt.title('Original Grayscale Image')
plt.axis('off')
plt.show()
```
## Global Thresholding
```
ret, global_thresh = cv2.threshold(gray, 127, 255, cv2.THRESH_BINARY)

plt.figure(figsize=(10, 5))

plt.subplot(1, 2, 1)
plt.imshow(gray, cmap='gray')
plt.title('Original Image')
plt.axis('off')

plt.subplot(1, 2, 2)
plt.imshow(global_thresh, cmap='gray')
plt.title('Global Thresholding')
plt.axis('off')

plt.show()
```
## Adaptive Mean Thresholding
```
adaptive_mean = cv2.adaptiveThreshold(
    gray, 255,
    cv2.ADAPTIVE_THRESH_MEAN_C,
    cv2.THRESH_BINARY,
    11, 2
)

plt.figure(figsize=(10, 5))

plt.subplot(1, 2, 1)
plt.imshow(gray, cmap='gray')
plt.title('Original Image')
plt.axis('off')

plt.subplot(1, 2, 2)
plt.imshow(adaptive_mean, cmap='gray')
plt.title('Adaptive Mean Thresholding')
plt.axis('off')

plt.show()
```
## Adaptive Gaussian Thresholding
```
adaptive_gaussian = cv2.adaptiveThreshold(
    gray, 255,
    cv2.ADAPTIVE_THRESH_GAUSSIAN_C,
    cv2.THRESH_BINARY,
    11, 2
)

plt.figure(figsize=(10, 5))

plt.subplot(1, 2, 1)
plt.imshow(gray, cmap='gray')
plt.title('Original Image')
plt.axis('off')

plt.subplot(1, 2, 2)
plt.imshow(adaptive_gaussian, cmap='gray')
plt.title('Adaptive Gaussian Thresholding')
plt.axis('off')

plt.show()
```
## Otsu's Thresholding
```
ret, otsu_thresh = cv2.threshold(
    gray, 0, 255,
    cv2.THRESH_BINARY + cv2.THRESH_OTSU
)

plt.figure(figsize=(10, 5))

plt.subplot(1, 2, 1)
plt.imshow(gray, cmap='gray')
plt.title('Original Image')
plt.axis('off')

plt.subplot(1, 2, 2)
plt.imshow(otsu_thresh, cmap='gray')
plt.title("Otsu's Thresholding")
plt.axis('off')

plt.show()

print("Optimal Threshold Value:", ret)
```
## Comparison of All Techniques
```
plt.figure(figsize=(12, 8))

images = [
    gray,
    global_thresh,
    adaptive_mean,
    adaptive_gaussian,
    otsu_thresh
]

titles = [
    'Original Grayscale',
    'Global Thresholding',
    'Adaptive Mean',
    'Adaptive Gaussian',
    "Otsu's Thresholding"
]

for i in range(5):
    plt.subplot(2, 3, i + 1)
    plt.imshow(images[i], cmap='gray')
    plt.title(titles[i])
    plt.axis('off')

plt.tight_layout()
plt.show()
```
## Output

## Original Grayscale Image
<img width="575" height="467" alt="image" src="https://github.com/user-attachments/assets/3feb9c5d-2f20-4710-ac16-2e6ad24428e7" />

## Global Thresholding
<img width="850" height="362" alt="image" src="https://github.com/user-attachments/assets/e36b2f85-452e-4eba-8f92-e4c9efec85bb" />

## Adaptive mean
<img width="920" height="372" alt="image" src="https://github.com/user-attachments/assets/2f6333c9-a222-47d4-973a-60c3a5a96236" />

## Adaptive Gaussian
<img width="922" height="371" alt="image" src="https://github.com/user-attachments/assets/79e946f6-2649-49aa-98aa-9e9723045136" />

## Otsu's Thresholding
<img width="871" height="390" alt="image" src="https://github.com/user-attachments/assets/16933551-659c-4ecd-953e-5d8cd290c45b" />

## All outputs
<img width="1232" height="752" alt="image" src="https://github.com/user-attachments/assets/93b04f8f-0d1b-4c42-9b22-e48185bf063f" />

## Result
Thus, image segmentation is successfully performed using Global Thresholding, Adaptive Thresholding, and Otsu's Thresholding techniques in OpenCV.
