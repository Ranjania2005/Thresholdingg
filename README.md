# THRESHOLDING
## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm

### Step1:
Load the necessary packages.

### Step2:
Read the Image and convert to grayscale.

### Step3:
Use Global thresholding to segment the image.

### Step4:
Use Adaptive thresholding to segment the image.

### Step5:
Use Otsu's method to segment the image and display the results.

## Program


```python

#Developed by : RANJANI A
#Register No: 212223230170

# Load the necessary packages

import numpy as np
import matplotlib.pyplot as plt
import cv2

# Read the Image and convert to grayscale

image = cv2.imread('bird.jpg',1)
image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray = cv2.imread('bird.jpg',0)

# Use Global thresholding to segment the image

ret,thresh_img1=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
ret,thresh_img2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_img3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)
ret,thresh_img4=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_img5=cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)

# Use Adaptive thresholding to segment the image

thresh_img7=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_img8=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)

# Use Otsu's method to segment the image 

ret,thresh_img6=cv2.threshold(image_gray,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)

# Display the results

titles=["Gray Image","Threshold Image (Binary)","Threshold Image (Binary Inverse)","Threshold Image (To Zero)"
       ,"Threshold Image (To Zero-Inverse)","Threshold Image (Truncate)","Otsu","Adaptive Threshold (Mean)","Adaptive Threshold (Gaussian)"]
images=[image_gray,thresh_img1,thresh_img2,thresh_img3,thresh_img4,thresh_img5,thresh_img6,thresh_img7,thresh_img8]
for i in range(0,9):
    plt.figure(figsize=(10,10))
    plt.subplot(1,2,1)
    plt.title("Original Image")
    plt.imshow(image)
    plt.axis("off")
    plt.subplot(1,2,2)
    plt.title(titles[i])
    plt.imshow(cv2.cvtColor(images[i],cv2.COLOR_BGR2RGB))
    plt.axis("off")
    plt.show()

```
## Output

### Original Image

![Screenshot 2025-04-24 143811](https://github.com/user-attachments/assets/c9d8ff96-a1dd-4133-b107-10cb6930af74)

### Global Thresholding

![Screenshot 2025-04-24 143818](https://github.com/user-attachments/assets/0e183e51-2a0f-43a9-aae6-227deb72bbf5)
![Screenshot 2025-04-24 143825](https://github.com/user-attachments/assets/7e6edc1c-5046-4693-9618-59aa6346aa49)
![Screenshot 2025-04-24 143832](https://github.com/user-attachments/assets/5910d61f-38f2-4fe1-ae96-ac55dcbe5c08)
![Screenshot 2025-04-24 143838](https://github.com/user-attachments/assets/7969ee46-7a35-4096-bfb3-d47fc2ded8dc)
![Screenshot 2025-04-24 143844](https://github.com/user-attachments/assets/a547a891-f8d0-4dc0-b8a4-2fd0743dd804)


### Adaptive Thresholding
![Screenshot 2025-04-24 143910](https://github.com/user-attachments/assets/7e660bdc-89ad-403c-9e30-4bd2b268b0f3)
![Screenshot 2025-04-24 143917](https://github.com/user-attachments/assets/64905178-b0c0-476e-99df-8ee30cf4d188)


### Optimum Global Thesholding using Otsu's Method

![Screenshot 2025-04-24 143903](https://github.com/user-attachments/assets/0809d08b-a00e-414b-8fe5-faa3c8243f34)


## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
