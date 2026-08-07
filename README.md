# EXP 3 - Histogram of an images
## Name : Meyyappan T
## Register No : 212223240086

## Aim
To obtain a histogram for finding the frequency of pixels in an Image with pixel values ranging from 0 to 255. Also write the code using OpenCV to perform histogram equalization.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
Read the gray and color image using imread()

### Step2:
Print the image using imshow().

### Step3:
Use calcHist() function to mark the image in graph frequency for gray and color image.

### step4:
Use calcHist() function to mark the image in graph frequency for gray and color image.

### Step5:
The Histogram of gray scale image and color image is shown.

## Program

### 1.Import Python necessary libraries
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
```
### 2.Histogram Equalization for Grayscale Images

```
img = cv2.imread('bird.jpg', cv2.IMREAD_GRAYSCALE)

plt.imshow(img, cmap='gray')
plt.title('Original Image')
plt.show()

```
<img width="552" height="344" alt="image" src="https://github.com/user-attachments/assets/f4f24c1a-7e99-4216-a3ea-697d679a4118" />


```
plt.hist(img.ravel(),256,range = [0, 256]);
plt.title('Original Image')
plt.show()
```
<img width="560" height="435" alt="image" src="https://github.com/user-attachments/assets/c27be14f-7bd8-4154-bcf5-a8177ec3474c" />


```
img_eq = cv2.equalizeHist(img)
plt.hist(img_eq.ravel(), 256, range = [0, 256])
plt.title('Equalized Histogram')
```
<img width="560" height="435" alt="image" src="https://github.com/user-attachments/assets/0ecd2687-f488-40fe-98fa-44cb39e13825" />

```
plt.imshow(img_eq, cmap='gray')
plt.title('Original Image')
plt.show()
```
<img width="552" height="344" alt="image" src="https://github.com/user-attachments/assets/37a544d7-5a4e-4da9-9ee3-0167b7ab0d91" />



### 3.Histogram Equalization for Color Images
```
img = cv2.imread('bird.jpg', cv2.IMREAD_COLOR)
img_hsv = cv2.cvtColor(img, cv2.COLOR_BGR2HSV)
img_hsv[:,:,2] = cv2.equalizeHist(img_hsv[:, :, 2])
img_eq = cv2.cvtColor(img_hsv, cv2.COLOR_HSV2BGR)
plt.imshow(img_eq[:,:,::-1]); plt.title('Equalized Image');plt.show()
```
<img width="552" height="344" alt="image" src="https://github.com/user-attachments/assets/e3a67ab9-8372-4adc-81c5-98659c151b72" />


```
plt.hist(img_eq.ravel(),256,range = [0, 256]); plt.title('Histogram Equalized');plt.show()
```
<img width="560" height="435" alt="image" src="https://github.com/user-attachments/assets/9a325e2a-f8fa-429a-a803-6e5a646ea0c3" />


```
plt.figure(figsize = (20,10))
plt.subplot(221); plt.imshow(img[:, :, ::-1]); plt.title('Original Color Image')
plt.subplot(222); plt.imshow(img_eq[:, :, ::-1]); plt.title('Equalized Image')
plt.show()
```
<img width="1525" height="416" alt="image" src="https://github.com/user-attachments/assets/3e6d5928-2bd3-4819-8106-f6b0797fa2b3" />


```
plt.figure(figsize = [15,4])
plt.subplot(121); plt.hist(img.ravel(),256,range = [0, 256]); plt.title('Original Image')
plt.subplot(122); plt.hist(img_eq.ravel(),256,range = [0, 256]); plt.title('Histogram Equalized')
```
<img width="1227" height="374" alt="image" src="https://github.com/user-attachments/assets/a912d920-0031-486b-ad26-b0089d9d654d" />


## Result:
Thus the histogram for finding the frequency of pixels in an image with pixel values ranging from 0 to 255 is obtained. Also,histogram equalization is done for the gray scale image using OpenCV.
