# Implementation-of-filter
## Developed By   : VISHNU RATHAN B
## Register Number: 212224240185
## Aim:
To implement filters for smoothing and sharpening the images in the spatial domain.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1
</br>Import the necessary libraries (cv2, numpy, matplotlib.pyplot) and read the input image using cv2.imread().

</br> 

### Step2
</br>
Define the kernels for the filters, such as an averaging kernel for smoothing (e.g., a 5x5 matrix of ones divided by 25) and a Laplacian kernel for sharpening.

</br> 

### Step3
</br>
Apply the smoothing filters to the original image using functions like cv2.filter2D() for the averaging filter, cv2.GaussianBlur() for Gaussian blur, and cv2.medianBlur() for median blur.

</br> 

### Step4
</br>
Apply the sharpening filter using cv2.filter2D() with the Laplacian kernel, and then add this filtered output to the original image to create the final sharpened image.

</br> 

### Step5
</br>
Display the original, smoothed, and sharpened images side-by-side using matplotlib.pyplot.imshow() and plt.subplot() for comparison.

</br> 

## Program:

</br>

### 1. Smoothing Filters

i) Using Averaging Filter
```Python



import cv2
import matplotlib.pyplot as plt
import numpy as np
image1=cv2.imread("vis.jpeg")
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
ii) Using Weighted Averaging Filter
```Python



kernel1=np.array([[1,2,1],[2,4,2],[1,2,1]])/16
image2=cv2.cvtColor(image1,cv2.COLOR_BGR2RGB)
image3=cv2.filter2D(image2,-1,kernel1)
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(image3)
plt.title("Weighted Average Filter Image")
plt.axis("off")
plt.show()






```
iii) Using Gaussian Filter
```Python





gaussian_blur=cv2.GaussianBlur(image2,(33,33),0,0)
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(gaussian_blur)
plt.title("Gaussian Blur")
plt.axis("off")
plt.show()



```
iv)Using Median Filter
```Python



median=cv2.medianBlur(image2,13)
plt.figure(figsize=(9,9))
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(median)
plt.title("Median Blur")
plt.axis("off")
plt.show()





```

### 2. Sharpening Filters
i) Using Laplacian Linear Kernal
```Python



kernel2=np.array([[-1,-1,-1],[2,-2,1],[2,1,-1]])
image3=cv2.filter2D(image2,-1,kernel2)
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(image3)
plt.title("Laplacian Kernel")
plt.axis("off")
plt.show()





```
ii) Using Laplacian Operator
```Python




laplacian=cv2.Laplacian(image2,cv2.CV_64F)
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(laplacian)
plt.title("Laplacian Operator")
plt.axis("off")
plt.show()




```

## OUTPUT:
### 1. Smoothing Filters
</br>

i) Using Averaging Filter

<img width="812" height="526" alt="image" src="https://github.com/user-attachments/assets/b60d409e-4879-481c-93b0-cb13674f24b6" />



ii)Using Weighted Averaging Filter

<img width="623" height="382" alt="image" src="https://github.com/user-attachments/assets/4dfb2e0e-b200-4ed9-bd7d-37afbc7da134" />




iii)Using Gaussian Filter

<img width="590" height="386" alt="image" src="https://github.com/user-attachments/assets/9d85bc88-759b-4415-86dd-725cf96dced8" />



iv) Using Median Filter

<img width="587" height="392" alt="image" src="https://github.com/user-attachments/assets/d65bf706-ad66-47fa-8e5e-04c491955d2c" />



### 2. Sharpening Filters
</br>

i) Using Laplacian Kernal

<img width="807" height="525" alt="image" src="https://github.com/user-attachments/assets/8c925ffb-c118-4743-b10b-63abc5f059a7" />


ii) Using Laplacian Operator

<img width="577" height="370" alt="image" src="https://github.com/user-attachments/assets/fa34f484-85b5-430d-902d-d67b718537dd" />




## Result:
Thus the filters are designed for smoothing and sharpening the images in the spatial domain.
