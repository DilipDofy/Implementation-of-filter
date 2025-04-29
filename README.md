# Implementation-of-filter
## Aim:
To implement filters for smoothing and sharpening the images in the spatial domain.

## Software Required:
Anaconda - Python 3.7

## Algorithm:

1.Import the required libraries.

2.Convert the image from BGR to RGB.

3.Apply the required filters for the image separately.

4.Plot the original and filtered image by using matplotlib.pyplot.

5.End of Program

## Program:
### Developed By   : DILIP M P
### Register Number: 212223230048
</br>

### 1. Smoothing Filters

i) Using Averaging Filter
```Python
import cv2
import matplotlib.pyplot as plt
import numpy as np
import os

img_path = r"C:\Users\admin\Downloads\Taj mahal.jpg"  # Change this to your correct path

if not os.path.exists(img_path):
    print(" Image not found. Check the file path.")
else:
    image1 = cv2.imread(img_path)
    if image1 is None:
        print(" Image could not be loaded (possibly corrupted or unsupported format).")
    else:
        image2 = cv2.cvtColor(image1, cv2.COLOR_BGR2RGB)
        kernel = np.ones((11, 11), np.float32) / 169
        image3 = cv2.filter2D(image2, -1, kernel)

        plt.figure(figsize=(9, 9))
        plt.subplot(1, 2, 1)
        plt.imshow(image2)
        plt.title("Original Image")
        plt.axis("off")

        plt.subplot(1, 2, 2)
        plt.imshow(image3)
        plt.title("Average Filter Image")
        plt.axis("off")
        plt.show()




```
<h2>OUTPUT</h2>

![Screenshot 2025-04-28 192132](https://github.com/user-attachments/assets/789e9e11-f0e8-4917-92ed-37d2d95352d7)




ii) Using Weighted Averaging Filter
```Python
kernel1=np.array([[1,2,1],[2,4,2],[1,2,1]])/16
image3=cv2.filter2D(image2,-1,kernel1)
plt.imshow(image3)
plt.title("Weighted Average Filter Image")
plt.axis("off")
plt.show()
```
<h2>OUTPUT</h2>

![Screenshot 2025-04-28 192148](https://github.com/user-attachments/assets/d355fb31-2afe-4e64-92b1-3ade9a55f396)




iii) Using Gaussian Filter
```Python
gaussian_blur=cv2.GaussianBlur(image2,(33,33),0,0)
plt.imshow(gaussian_blur)
plt.title("Gaussian Blur")
plt.axis("off")
plt.show()
```
<h2>OUTPUT</h2>


![Screenshot 2025-04-28 192200](https://github.com/user-attachments/assets/ae7b5836-ac61-4cd3-a90f-6a0dce09dd36)



iv)Using Median Filter
```Python
median = cv2.medianBlur(image2, 13)
plt.imshow(cv2.cvtColor(median, cv2.COLOR_BGR2RGB))  # Convert BGR to RGB for correct color display
plt.title("Median Blur")
plt.axis("off")
plt.show()
```
<h2>OUTPUT</h2>

![Screenshot 2025-04-28 192212](https://github.com/user-attachments/assets/3019233c-7204-40f2-8ce0-affe7292f8af)




### 2. Sharpening Filters
i) Using Laplacian Linear Kernal
```Python
kernel2=np.array([[-1,-1,-1],[2,-2,1],[2,1,-1]])
image3=cv2.filter2D(image2,-1,kernel2)
plt.imshow(image3)
plt.title("Laplacian Kernel")
plt.axis("off")
plt.show()

```
<h2>OUTPUT</h2>

![Screenshot 2025-04-28 192225](https://github.com/user-attachments/assets/cb2a3f95-32be-4783-9129-681082d73d35)




ii) Using Laplacian Operator
```Python
laplacian=cv2.Laplacian(image2,cv2.CV_64F)
plt.imshow(laplacian)
plt.title("Laplacian Operator")
plt.axis("off")
plt.show()
```
<h2>OUTPUT</h2>


![Screenshot 2025-04-28 192250](https://github.com/user-attachments/assets/12eb2c16-0841-43f8-a049-7e8b9ec30482)



</br>

## Result:
Thus the filters are designed for smoothing and sharpening the images in the spatial domain.
