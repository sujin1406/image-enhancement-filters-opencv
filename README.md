# Image Smoothing and Sharpening Using OpenCV

## Aim

To write a Python program using OpenCV to apply different smoothing filters (Averaging, Weighted Averaging, Gaussian, Median) and sharpening filters (Laplacian Kernel and Laplacian Operator) for image enhancement, and display each result separately along with the original image for comparison.

---

## The program performs the following operations:

- Read and display an input image  
- Apply Averaging filter  
- Apply Weighted Averaging filter  
- Apply Gaussian filter  
- Apply Median filter  
- Apply Laplacian sharpening using kernel  
- Apply Laplacian operator  
- Display all outputs for comparison  

---

##  Software Used

- Anaconda – Python 3.7  
- Jupyter Notebook / VS Code  
- OpenCV (cv2)  
- NumPy  
- Matplotlib  

---

##  Algorithm

### Step 1:
Import the required libraries: OpenCV, NumPy, and Matplotlib.

### Step 2:
Read the input image (e.g., `image.jpg`).

### Step 3:
Convert the image from BGR to RGB format for display.

### Step 4:
Apply Averaging Filter using `cv2.blur()`.

### Step 5:
Apply Weighted Averaging Filter using a custom kernel with `cv2.filter2D()`.

### Step 6:
Apply Gaussian Filter using `cv2.GaussianBlur()`.

### Step 7:
Apply Median Filter using `cv2.medianBlur()`.

### Step 8:
Apply Laplacian Sharpening using Kernel with `cv2.filter2D()`.

### Step 9:
Convert image to grayscale and apply Laplacian Operator using `cv2.Laplacian()`.

### Step 10:
Display all filtered images using a grid layout for comparison.

---

##  Developed By

- **Name:** SUJIN M L 
- **Register No:** 212225040435 

1.Import Image
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
img = cv2.imread("POC.jpg")
img = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
plt.imshow(img)
plt.title("Original Image")
plt.axis("off")
plt.show()
```
2.Averaging filter
```
avg = cv2.blur(img, (5,5))
plt.imshow(avg)
plt.title("Averaging Filter")
plt.axis("off")
plt.show()
```
3.Weighted averaging filter
```
kernel = np.array([[1,2,1],
                 [2,4,2],
                 [1,2,1]], np.float32) / 16
weighted = cv2.filter2D(img, -1, kernel)
plt.imshow(weighted)
plt.title("Weighted Averaging Filter")
plt.axis("off")
plt.show()
```
4.Gaussian filter 
```
gaussian = cv2.GaussianBlur(img, (5,5), 0)
plt.imshow(gaussian)
plt.title("Gaussian Filter")
plt.axis("off")
plt.show()

```
5.Median filter
```
median = cv2.medianBlur(img, 5)
plt.imshow(median)
plt.title("Median Filter")
plt.axis("off")
plt.show()
```
6.Laplacian Sharpening
```
kernel = np.array([[0,-1,0],
                   [-1,5,-1],
                   [0,-1,0]])
sharp = cv2.filter2D(img, -1, kernel)
plt.imshow(sharp)
plt.title("Laplacian Kernel")
plt.axis("off")
plt.show()
```
7.Laplacian operator  
```
lap = cv2.Laplacian(img, cv2.CV_64F)
lap = np.uint8(np.absolute(lap))
plt.imshow(lap)
plt.title("Laplacian Operator")
plt.axis("off")
plt.show()
```
---

##  Output

### Original Image
<img width="707" height="439" alt="image" src="https://github.com/user-attachments/assets/7d064af9-1fc0-4cb2-9acb-9368750b2857" />

### Averaging filter
<img width="706" height="438" alt="image" src="https://github.com/user-attachments/assets/9bdb4479-ee09-4442-ba2b-0d9953e224be" />

### Weighted averaging filter 
<img width="707" height="443" alt="image" src="https://github.com/user-attachments/assets/c0a67175-fcdb-4331-b290-4ada09cce0c5" />

### Gaussian filter  
<img width="698" height="439" alt="image" src="https://github.com/user-attachments/assets/1ba816d0-732b-4bda-b581-af761e6628f9" />

### Median filter
<img width="708" height="447" alt="image" src="https://github.com/user-attachments/assets/96d55196-ae74-4002-940c-773f6f832c66" />

### Laplacian Sharpening (kernel)
<img width="701" height="436" alt="image" src="https://github.com/user-attachments/assets/71db941a-36c4-46ec-962c-71de1f5de207" />

### Laplacian operator   
<img width="722" height="440" alt="image" src="https://github.com/user-attachments/assets/7b3cc4ee-9d7d-4a14-8f7a-a035d8fe3141" />


---

##  Result

Thus, smoothing filters and sharpening filters are successfully implemented using OpenCV.

The smoothing filters reduce noise and improve image quality, while sharpening filters enhance edges and details for better feature extraction.
