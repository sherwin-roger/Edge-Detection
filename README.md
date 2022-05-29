# Edge-Detection
## Aim:

To perform edge detection using Sobel, Laplacian, and Canny edge detectors.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
Import the required packages.

### Step2:
Read the image and cconvert into gray image.

### Step3:
Remove the noise of the image using gaussian operator.

### Step4:
Find the sobel edge,laplacian edge,canny edge using the built in modules available in opencv.

### Step5:
Plot the edged image using matplotlib.
 
## Program:

``` Python
# Developed By   : SHERWIN ROGER R.D
# Register Number: 212220230046
import cv2
import numpy as np
import matplotlib.pyplot as plt
image1=cv2.imread ('images.jpg') 
gray = cv2.cvtColor(image1,cv2.COLOR_BGR2GRAY)

plt.title('GRAY IMAGE')
plt.imshow(gray,cmap = 'gray')

img = cv2.GaussianBlur(gray,(3,3),0)
sobelx = cv2.Sobel(gray,cv2.CV_64F,1,0,ksize=5)
sobely = cv2.Sobel(gray,cv2.CV_64F,0,1,ksize=5)
sobelxy =cv2.Sobel(gray,cv2.CV_64F,1,1,ksize=5)
plt.figure(1)
plt.subplot(2,2,1)
plt.imshow(gray,cmap = 'gray')
plt.title('Original'), plt.xticks([]), plt.yticks([])

plt.subplot(2,2,2)
plt.imshow(sobelx,cmap='gray')
plt.title('sobelx')
plt.xticks([]), plt.yticks([])

plt.subplot(2,2,3)
plt.imshow(sobely,cmap='gray')
plt.title('sobely')
plt.xticks([]), plt.yticks([])

plt.subplot(2,2,4)
plt.imshow(sobelxy,cmap='gray')
plt.title('sobelxy')
plt.xticks([]), plt.yticks([])
plt.show()
# cv2.waitKey(0)
laplacian = cv2.Laplacian(gray,cv2.CV_64F)
plt.imshow(laplacian,cmap='gray')
plt.title('laplacian')
plt.show()

canny_edges = cv2.Canny(gray, 120, 150)
plt.imshow(canny_edges,cmap='gray')
plt.title('canny_edges')
plt.show()
```
## Output:
### SOBEL EDGE DETECTOR
![O1](https://user-images.githubusercontent.com/75235747/168643877-2d3b2e4c-c586-4f92-b313-5926f3aa4d73.JPG)

### LAPLACIAN EDGE DETECTOR
![O2](https://user-images.githubusercontent.com/75235747/168643968-b99b4833-5ebb-45b2-a253-553ba2a7982d.JPG)

### CANNY EDGE DETECTOR
![O3](https://user-images.githubusercontent.com/75235747/168643999-090609d7-2a33-4e5d-9e95-fd9b1c4b9a52.JPG)

## Result:
Thus the edges are detected using Sobel, Laplacian, and Canny edge detectors.
