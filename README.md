# Implementation-of-Filters
## Aim:
To implement filters for smoothing and sharpening the images in the spatial domain.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
Step1
Import cv2, matplotlib.py libraries and read the saved images using cv2.imread().

Step2
Convert the saved BGR image to RGB using cvtColor().

Step3
By using the following filters for image smoothing:filter2D(src, ddepth, kernel), Box filter,Weighted Average filter,GaussianBlur(src, ksize, sigmaX[, dst[, sigmaY[, borderType]]]), medianBlur(src, ksize),and for image sharpening:Laplacian Kernel,Laplacian Operator.

Step4
Apply the filters using cv2.filter2D() for each respective filters.

Step5
Plot the images of the original one and the filtered one using plt.figure() and cv2.imshow().

## Program:
### Developed By   :Bhavishya Reddy Mitta
### Register Number:212221230061
import cv2
import numpy as np
import matplotlib.pyplot as plt
image = cv2.imread("pikachu.jpg")
original_image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)

### 1. Smoothing Filters

i) Using Averaging Filter
kernel1 = np.ones((11,11),np.float32)/121
avg_filter = cv2.filter2D(original_image,-1,kernel1)
plt.figure(figsize = (9,9))
plt.subplot(1,2,1)
plt.imshow(original_image)
plt.title("Original")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(avg_filter)
plt.title("Filtered")
plt.axis("off")



```
ii) Using Weighted Averaging Filter
kernel2 = np.array([[1,2,1],[2,4,2],[1,2,1]])/16
weighted_filter = cv2.filter2D(original_image,-1,kernel2)
plt.figure(figsize = (9,9))
plt.subplot(1,2,1)
plt.imshow(original_image)
plt.title("Original")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(weighted_filter)
plt.title("Filtered")
plt.axis("off")




```
iii) Using Gaussian Filter
gaussian_blur = cv2.GaussianBlur(src = original_image, ksize = (11,11), sigmaX=0, sigmaY=0)
plt.figure(figsize = (9,9))
plt.subplot(1,2,1)
plt.imshow(original_image)
plt.title("Original")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(gaussian_blur)
plt.title("Filtered")
plt.axis("off")
```

iv) Using Median Filter
median = cv2.medianBlur(src=original_image,ksize = 11)
plt.figure(figsize = (9,9))
plt.subplot(1,2,1)
plt.imshow(original_image)
plt.title("Original")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(median)
plt.title("Filtered")
plt.axis("off")




```

### 2. Sharpening Filters
i) Using Laplacian Kernal
kernel3 = np.array([[0,1,0],[1,-4,1],[0,1,0]])
laplacian_kernel = cv2.filter2D(original_image,-1,kernel3)
plt.figure(figsize = (9,9))
plt.subplot(1,2,1)
plt.imshow(original_image)
plt.title("Original")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(laplacian_kernel)
plt.title("Filtered")
plt.axis("off")




```
ii) Using Laplacian Operator
laplacian_operator = cv2.Laplacian(original_image,cv2.CV_64F)
plt.figure(figsize = (9,9))
plt.subplot(1,2,1)
plt.imshow(original_image)
plt.title("Original")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(laplacian_operator)
plt.title("Filtered")
plt.axis("off")





```

## OUTPUT:
### 1. Smoothing Filters
</br>

i) Using Averaging Filter

![dip b6-1](https://user-images.githubusercontent.com/94679395/233050930-4182b43d-d64f-47a7-aaed-60d2dd57934b.jpg)

ii) Using Weighted Averaging Filter

![dip b6-2](https://user-images.githubusercontent.com/94679395/233050986-0f666259-6607-42e0-b714-53336a712f2f.jpg)

iii) Using Gaussian Filter

![dip b6-3](https://user-images.githubusercontent.com/94679395/233051052-2b966dcd-f7d4-41b6-9628-b4f131cce1c1.jpg)

iv) Using Median Filter

![dip b6-4](https://user-images.githubusercontent.com/94679395/233051195-dec36af0-c7f8-4b08-9438-020bcadab0aa.jpg)



### 2. Sharpening Filters
</br>

i) Using Laplacian Kernal

![dip b6-5](https://user-images.githubusercontent.com/94679395/233051103-5970c544-c2d2-48e5-83b8-fe11333329f8.jpg)


ii) Using Laplacian Operator

![dip b6-6](https://user-images.githubusercontent.com/94679395/233051240-3e250e65-d824-4578-aae4-e7dacd08b7d0.jpg)


## Result:
Thus the filters are designed for smoothing and sharpening the images in the spatial domain.
