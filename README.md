# Edge-Detection
## Aim:
To perform edge detection using Sobel, Laplacian, and Canny edge detectors.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
<br>
Import the necessary modules.

### Step2:
<br>
Load the image to operate on.

### Step3:
<br>
Convert the image to grayscale image.

### Step4:
<br>
Use Sobel operator along x,y and xy directions.

### Step5:
<br>
Operate the image using Laplacian operator.

### Step6:
<br>
Operate the image using Canny Edge operator.

### Step7:
<br>
Show all the operated images output.
 
## Program:

``` Python
# Import the packages
import cv2
import numpy as np
import matplotlib.pyplot as plt
image1=cv2.imread ('dip7.jpg') 
gray_image = cv2.cvtColor(image1,cv2.COLOR_BGR2GRAY)


# Load the image, Convert to grayscale and remove noise
plt.title('GRAY IMAGE')
plt.imshow(gray_image,cmap = 'gray')

img = cv2.GaussianBlur(gray_image,(3,3),0)
sobelx = cv2.Sobel(gray_image,cv2.CV_64F,1,0,ksize=5)
sobely = cv2.Sobel(gray_image,cv2.CV_64F,0,1,ksize=5)
sobelxy =cv2.Sobel(gray_image,cv2.CV_64F,1,1,ksize=5)
plt.figure(1)
plt.subplot(2,2,1)
plt.imshow(gray_image,cmap = 'gray')
plt.title('Original'), plt.xticks([]), plt.yticks([])


# SOBEL EDGE DETECTOR
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


# LAPLACIAN EDGE DETECTOR
# cv2.waitKey(0)
laplacian = cv2.Laplacian(gray_image,cv2.CV_64F)
plt.imshow(laplacian,cmap='gray')
plt.title('laplacian')
plt.show()



# CANNY EDGE DETECTOR
canny_edges = cv2.Canny(gray_image, 120, 150)
plt.imshow(canny_edges,cmap='gray')
plt.title('canny_edges')
plt.show()




```
## Output:
### SOBEL EDGE DETECTOR

![dip1](https://user-images.githubusercontent.com/94505585/231692994-c47571d2-7cb8-44a6-a966-1b26bbce0de2.jpg)



### LAPLACIAN EDGE DETECTOR

![dip2](https://user-images.githubusercontent.com/94505585/231693032-250abb34-5c5f-47b1-9645-d39dff6529e0.jpg)


### CANNY EDGE DETECTOR

![dip3](https://user-images.githubusercontent.com/94505585/231693066-65d0773d-cce3-486c-896e-31727ba004b0.jpg)


## Result:
Thus the edges are detected using Sobel, Laplacian, and Canny edge detectors.
