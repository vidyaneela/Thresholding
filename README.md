# Thresholding of Images
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
Use Otsu's method to segment the image.

### Step 6:
Display the results.


## Program

```
Developed by : M VIDYA NEELA
Reg no : 212221230120
```

# Load the necessary packages
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
```


# Read the Image and convert to grayscale

```
in_img=cv2.imread('suzume.PNG')
in_img2=cv2.imread('suzume2.PNG')

in_img= cv2.resize(in_img, (461,250))
in_img2= cv2.resize(in_img2, (463,284))

gray_img = cv2.cvtColor(in_img,cv2.COLOR_BGR2GRAY)
gray_img2 = cv2.cvtColor(in_img2,cv2.COLOR_BGR2GRAY)
```




# Use Global thresholding to segment the image

```
# cv2.threshold(image, threshold_value, max_val, thresholding_technique)
ret,thresh_img1=cv2.threshold(gray_img,86,255,cv2.THRESH_BINARY)
ret,thresh_img2=cv2.threshold(gray_img,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_img3=cv2.threshold(gray_img,86,255,cv2.THRESH_TOZERO)
ret,thresh_img4=cv2.threshold(gray_img,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_img5=cv2.threshold(gray_img,100,255,cv2.THRESH_TRUNC)
```


# Use Adaptive thresholding to segment the image

```
# cv2.adaptiveThreshold(source, max_val, adaptive_method, threshold_type, blocksize, constant)
thresh_img6=cv2.adaptiveThreshold(gray_img2,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_img7=cv2.adaptiveThreshold(gray_img2,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)
```




# Use Otsu's method to segment the image 

```
# cv2.threshold(img,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)
ret,thresh_img8=cv2.threshold(gray_img2,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)
```


# Display the results
```
cv2.imshow('original image',in_img)
cv2.imshow('original image(second)',in_img2)

cv2.imshow('original image(gray)',gray_img)
cv2.imshow('original image(gray)(second)',gray_img2)

cv2.imshow('binary threshold',thresh_img1)
cv2.imshow('binary-inverse threshold',thresh_img2)
cv2.imshow('to-zero threshold',thresh_img3)
cv2.imshow('to-zero-inverse threshold',thresh_img4)
cv2.imshow('truncate threshold',thresh_img5)

cv2.imshow('mean adaptive threshold',thresh_img6)
cv2.imshow('gaussian adaptive threshold',thresh_img7)

cv2.imshow('otsu\'s threshold',thresh_img8)

cv2.waitKey(0)
cv2.destroyAllWindows()

```

## Output

### Original Image
![image](https://github.com/vidyaneela/Thresholding/assets/94169318/f48817c8-7598-43af-9237-a0a7623f8188)

![image](https://github.com/vidyaneela/Thresholding/assets/94169318/1fe47927-8647-4259-bf9e-06eccad98251)

![image](https://github.com/vidyaneela/Thresholding/assets/94169318/7c1d780b-de51-4307-aee7-dbe424f9c89b)


### Global Thresholding

![image](https://github.com/vidyaneela/Thresholding/assets/94169318/04306aa8-df2e-402c-be6a-66f8d4f82a18)

![image](https://github.com/vidyaneela/Thresholding/assets/94169318/c2696ed9-5765-449c-b69b-8d73f52ef1a8)


### Adaptive Thresholding

![image](https://github.com/vidyaneela/Thresholding/assets/94169318/22ad5da3-df1d-430a-ad02-2a725c986020)

### Optimum Global Thesholding using Otsu's Method

![image](https://github.com/vidyaneela/Thresholding/assets/94169318/cef21713-32a0-4b2c-b1d8-94e7a95f3db3)



## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.

