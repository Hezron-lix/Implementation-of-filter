# Implementation-of-filter
## Aim:
To implement filters for smoothing and sharpening the images in the spatial domain.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1
Import the required libraries.

### Step2
Convert the image from BGR to RGB.

### Step3
Apply the required filters for the image separately.

### Step4
Plot the original and filtered image by using matplotlib.pyplot.

### Step5
End the program.

## Program:
## Developed By: Hezron Belix
## Register No: 212223230078


### 1. Smoothing Filters

#### i) Using Averaging Filter
```
import cv2
import matplotlib.pyplot as plt
import numpy as np
image1=cv2.imread("taj.jpeg")
image2=cv2.cvtColor(image1,cv2.COLOR_BGR2RGB)
kernel=np.ones((11,11),np.float32)/169
image3=cv2.filter2D(image2,-1,kernel)
plt.figure(figsize=(9,9))
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(image3)
plt.title("Average Filter Image")
plt.axis("off")
plt.show()
```
## Output 

![download](https://github.com/user-attachments/assets/a3fa7bb6-f735-4ced-8af4-a2cb719be35b)

#### ii) Using Weighted Averaging Filter
```
kernel1=np.array([[1,2,1],[2,4,2],[1,2,1]])/16
image3=cv2.filter2D(image2,-1,kernel1)
plt.imshow(image3)
plt.title("Weighted Average Filter Image")
plt.axis("off")
plt.show()
```
## Output

![download](https://github.com/user-attachments/assets/c1081d48-15aa-405d-943e-c992ddc7ba79)


#### iii) Using Gaussian Filter
```
gaussian_blur=cv2.GaussianBlur(image2,(33,33),0,0)
plt.imshow(gaussian_blur)
plt.title("Gaussian Blur")
plt.axis("off")
plt.show()
```
## Output

![download](https://github.com/user-attachments/assets/197178bd-8a62-4472-9846-795cc66bc639)


#### iv)Using Median Filter
```
median=cv2.medianBlur(image2,13)

plt.title("Median Blur")
plt.axis("off")
plt.show()
```
## Output

![download](https://github.com/user-attachments/assets/0ce16f0f-1d0e-4770-a22a-2f1ba6e02257)


### 2. Sharpening Filters

#### i) Using Laplacian Linear Kernal
```
kernel2=np.array([[-1,-1,-1],[2,-2,1],[2,1,-1]])
image3=cv2.filter2D(image2,-1,kernel2)
plt.imshow(image3)
plt.title("Laplacian Kernel")
plt.axis("off")
plt.show()
```
## Output

![download](https://github.com/user-attachments/assets/328c844c-6cb7-452b-abd2-b6a19ab7ec18)


#### ii) Using Laplacian Operator
```
laplacian=cv2.Laplacian(image2,cv2.CV_64F)
plt.imshow(laplacian)
plt.title("Laplacian Operator")
plt.axis("off")
plt.show()
```
## Output

![download](https://github.com/user-attachments/assets/f1466254-4219-4958-8d75-eb7a00f39c08)


## Result:
Thus the filters are designed for smoothing and sharpening the images in the spatial domain.
