# Histogram-of-an-images

### Developed By: Chandru M

### Register Number: 212224230041

## Aim

To obtain a histogram for finding the frequency of pixels in an image with pixel values ranging from 0 to 255. Also, write a Python program using OpenCV to perform histogram equalization.

## Software Required

- Anaconda - Python 3.7
- OpenCV
- NumPy
- Matplotlib

## Algorithm

### Step 1
Read the grayscale and color images using the `cv2.imread()` function.

### Step 2
Display the grayscale and color images using the `imshow()` function.

### Step 3
Use the `cv2.calcHist()` function to calculate the frequency of pixel intensities in the grayscale image.

### Step 4
Use the `cv2.calcHist()` function to calculate the histograms of the Blue, Green, and Red channels of the color image.

### Step 5
Plot and display the histograms of the grayscale image and color image.

## Program

```python
import cv2
import numpy as np
import matplotlib.pyplot as plt

img = cv2.imread(r"E:\College\THIRD YEAR\5TH SEM\DIPT\chandru.jpg", cv2.IMREAD_GRAYSCALE)

plt.imshow(img, cmap='gray')
plt.title('Original Image')
plt.show()

plt.hist(img.ravel(),256,range = [0, 256]);
plt.title('Original Image')
plt.show()

img_eq = cv2.equalizeHist(img)
plt.hist(img_eq.ravel(), 256, range = [0, 256])
plt.title('Equalized Histogram')

plt.imshow(img_eq, cmap='gray')
plt.title('Original Image')
plt.show()

img = cv2.imread(r"E:\College\THIRD YEAR\5TH SEM\DIPT\chandru.jpg", cv2.IMREAD_COLOR)
img_hsv = cv2.cvtColor(img, cv2.COLOR_BGR2HSV)
img_hsv[:,:,2] = cv2.equalizeHist(img_hsv[:, :, 2])
img_eq = cv2.cvtColor(img_hsv, cv2.COLOR_HSV2BGR)
plt.imshow(img_eq[:,:,::-1]); plt.title('Equalized Image');plt.show()

plt.hist(img_eq.ravel(),256,range = [0, 256]); plt.title('Histogram Equalized');plt.show()

plt.figure(figsize = (20,10))
plt.subplot(221); plt.imshow(img[:, :, ::-1]); plt.title('Original Color Image')
plt.subplot(222); plt.imshow(img_eq[:, :, ::-1]); plt.title('Equalized Image')
plt.show()

plt.figure(figsize = [15,4])
plt.subplot(121); plt.hist(img.ravel(),256,range = [0, 256]); plt.title('Original Image')
plt.subplot(122); plt.hist(img_eq.ravel(),256,range = [0, 256]); plt.title('Histogram Equalized')

```

## Output

### Input Grayscale Image

<img width="314" height="434" alt="download" src="https://github.com/user-attachments/assets/ed628b2b-d2f2-49b4-b3db-52e65acdf358" />


### Input Grayscale Image Range


<img width="547" height="434" alt="download" src="https://github.com/user-attachments/assets/2b6a3efa-e98a-4ae9-bc66-65d788147100" />


### Input Grayscale Image Equalized Histogram


<img width="547" height="434" alt="download" src="https://github.com/user-attachments/assets/53d1eb63-b4f4-40f6-b873-f85cb8f938ea" />





### Histogram of Grayscale Image and Color Image Channels

### Original Image

<img width="314" height="434" alt="download" src="https://github.com/user-attachments/assets/ea6983ab-3a18-437d-a2ca-89255bfd2908" />


### Equalized Image

<img width="314" height="434" alt="download" src="https://github.com/user-attachments/assets/04c8ec12-631b-4bc6-a22e-0f48a7de8fc5" />


### Equalized Histogram

<img width="547" height="434" alt="download" src="https://github.com/user-attachments/assets/55537c25-d0c1-4adb-ad48-7010405d3ea2" />


### Final Output of Original Image and Equalized 

<img width="1146" height="414" alt="download" src="https://github.com/user-attachments/assets/9ee91db6-5960-4ec9-9a01-ac384d8d29c2" />



### Final Output of Original Image and its Histogram Equalized

<img width="1214" height="372" alt="download" src="https://github.com/user-attachments/assets/113c9c2e-338a-42db-82ff-3b7f7b082a98" />



## Result

Thus, the histogram showing the frequency of pixel intensities ranging from 0 to 255 was obtained for the grayscale image and the color image using OpenCV.
