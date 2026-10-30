#  EXP.3-RECORD-HISTOGRAM-PROCESSING


## AIM
To write a Python program using OpenCV to perform histogram equalization on both grayscale and color images to enhance image contrast and brightness.

The program performs the following operations:

1. Read and display a grayscale image.
2. Plot the histogram of the grayscale image.
3. Apply histogram equalization on the grayscale image.
4. Read and display a color image.
5. Plot histograms of B, G, R channels.
6. Convert the image to HSV color space.
7. Apply histogram equalization on the Value (V) channel.
8. Convert the enhanced image back to BGR format.
9. Display original and enhanced images with histograms.

## SOFTWARE REQUIRED
- Anaconda – Python 3.7
- Jupyter Notebook / VS Code
- OpenCV (`cv2`)
- NumPy
- Matplotlib

## ALGORITHM

## Step 1:
Import the required libraries: OpenCV, NumPy, and Matplotlib.

## Step 2:
Read the image `parrot.jpg` in grayscale format.

## Step 3:
Display the grayscale image and plot its histogram.

## Step 4: 
Apply histogram equalization using `cv2.equalizeHist()` to enhance contrast.

## Step 5:
Display the original grayscale image, its histogram, enhanced image, and enhanced histogram using a 2 × 2 grid.

## Step 6: 
Read the same image in color format.

## Step 7:
Split the image into B, G, R channels and plot their histograms.

## Step 8: 
Convert the image from BGR to HSV color space.

## Step 9:
Apply histogram equalization on the V (Value) channel.

## Step 10: 
Merge the channels and convert the image back to BGR format.

## Step 11:
Display the original color image, histogram, enhanced image, and enhanced histogram using a 2 × 2 grid.

---

## PROGRAM

### Developed By
## Name: NIKILA D
## Register No: 212224230187

## 1. Import the Required Libraries and Read the Grayscale Image

```python
import cv2
import numpy as np
import matplotlib.pyplot as plt

img = cv2.imread('parrot.jpg', cv2.IMREAD_GRAYSCALE)

plt.imshow(img, cmap='gray')
plt.title('Original Grayscale Image')
plt.axis('off')
plt.show()
```

## OUTPUT:
<img width="517" height="607" alt="image" src="https://github.com/user-attachments/assets/14189c8a-b21d-4677-be13-707b4eee6cb9" />

## 2. Plot the Histogram of the Grayscale Image

```python
plt.hist(img.ravel(), 256, range=[0, 256])
plt.title('Original Grayscale Histogram')
plt.xlabel('Pixel Intensity')
plt.ylabel('Frequency')
plt.show()
```
## OUTPUT:
<img width="851" height="597" alt="image" src="https://github.com/user-attachments/assets/d508e92b-c536-4b54-88b6-52d6321bf3b4" />

## 3. Apply Histogram Equalization

```python
img_eq = cv2.equalizeHist(img)
```

## 4. Display the Histogram of the Equalized Image

```python
plt.hist(img_eq.ravel(), 256, range=[0, 256])
plt.title('Equalized Histogram')
plt.xlabel('Pixel Intensity')
plt.ylabel('Frequency')
plt.show()
```

## OUTPUT:
<img width="1027" height="615" alt="image" src="https://github.com/user-attachments/assets/f6a5d693-8b78-4f89-b7d9-aed9ee05f7a4" />

## 5. Display the Equalized Grayscale Image

```python
plt.imshow(img_eq, cmap='gray')
plt.title('Equalized Image')
plt.axis('off')
plt.show()
```

## OUTPUT:
<img width="486" height="605" alt="image" src="https://github.com/user-attachments/assets/8fe0905c-943b-444a-b7e8-b9a6291d28fa" />

## 6. Read the Image in Color Mode and Convert to HSV

```python
img = cv2.imread('parrot.jpg', cv2.IMREAD_COLOR)

img_hsv = cv2.cvtColor(img, cv2.COLOR_BGR2HSV)
```

## 7. Apply Histogram Equalization to the V Channel

```python
img_hsv[:, :, 2] = cv2.equalizeHist(img_hsv[:, :, 2])
```

## 8. Convert the Enhanced HSV Image Back to BGR

```python
img_eq = cv2.cvtColor(img_hsv, cv2.COLOR_HSV2BGR)
```

## 9. Display the Original and Equalized Color Images

```python
plt.figure(figsize=[12, 5])

plt.subplot(121)
plt.imshow(img[:, :, ::-1])
plt.title('Original Color Image')
plt.axis('off')

plt.subplot(122)
plt.imshow(img_eq[:, :, ::-1])
plt.title('Equalized Image')
plt.axis('off')

plt.show()
```

## OUTPUT:
<img width="502" height="555" alt="image" src="https://github.com/user-attachments/assets/2e36e4de-5b5b-4196-b726-a7977d8509f5" />
<img width="468" height="535" alt="image" src="https://github.com/user-attachments/assets/d84dfde9-720a-4ac0-bf3d-c556e6a95dbb" />


## 10. Display the Original and Equalized Images Along with Their Histograms

```python
plt.figure(figsize=[12, 10])

plt.subplot(221)
plt.imshow(img[:, :, ::-1])
plt.title('Original Color Image')
plt.axis('off')

plt.subplot(222)
plt.imshow(img_eq[:, :, ::-1])
plt.title('Equalized Image')
plt.axis('off')

plt.subplot(223)
plt.hist(img.ravel(), 256, range=[0, 256])
plt.title('Original Histogram')

plt.subplot(224)
plt.hist(img_eq.ravel(), 256, range=[0, 256])
plt.title('Histogram Equalized')

plt.show()
```
## OUTPUT:
<img width="1518" height="467" alt="image" src="https://github.com/user-attachments/assets/d56cce13-fa55-4119-98ad-a52d97c56097" />

## RESULT

Thus, histogram equalization is successfully performed on both grayscale and color images using OpenCV. The contrast and brightness of the images are improved, enhancing visual quality and feature visibility.
