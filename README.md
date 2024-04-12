# Implementation-of-Erosion-and-Dilation
## Aim
To implement Erosion and Dilation using Python and OpenCV.
## Software Required
1. Anaconda - Python 3.7
2. OpenCV
## Algorithm:
### Step1:
<br>
Import necessary packages

### Step2:
<br>
Create an empty window and add text to it
### Step3:
<br>
create a structuring element
### Step4:
<br>
Do the operation
### Step5:
<br>
Show the output image
 
## Program:

``` Python
import cv2
import numpy as np
from matplotlib import pyplot as plt

#to read the color image
input_image_path='picture.jpg'
color_image=cv2.imread(input_image_path)

#convert the color image to grayscale
gray_image=cv2.cvtColor(color_image,cv2.COLOR_BGR2GRAY)

#perform edge detection using Canny
edges=cv2.Canny(gray_image,100,200)

#define the kernel size for erosion and dilation
kernel_size=5
kernel=np.ones((kernel_size,kernel_size),np.uint8)

#perform erosion
erosion=cv2.erode(edges,kernel,iterations=1)

#perform dilation
dilation=cv2.dilate(edges,kernel,iterations=1)

#display all images
plt.figure(figsize=(15,10))

plt.subplot(2,3,1)
plt.imshow(cv2.cvtColor(color_image,cv2.COLOR_BGR2RGB))
plt.title('Original Color Image')
plt.axis('on')

plt.subplot(2,3,2)
plt.imshow(gray_image,cmap='gray')
plt.title('Black and White Image')
plt.axis('on')

plt.subplot(2,3,3)
plt.imshow(edges,cmap='gray')
plt.title('Edge Segmentation')
plt.axis('on')

plt.subplot(2,3,4)
plt.imshow(erosion,cmap='gray')
plt.title('Erosion')
plt.axis('on')

plt.subplot(2,3,5)
plt.imshow(dilation,cmap='gray')
plt.title('Dilation')
plt.axis('on')

plt.show()

```
## Output:

### Display the input Image
![image](https://github.com/Augustine0306/erosion-dilation/assets/119404460/30829bae-712e-48b7-b040-bd0e543a6283)


### Display the Eroded Image
![image](https://github.com/Augustine0306/erosion-dilation/assets/119404460/fb348817-fc74-4233-adf5-2d053ee4affb)


### Display the Dilated Image
![image](https://github.com/Augustine0306/erosion-dilation/assets/119404460/a00b4415-480a-4632-bf1d-53f7d9ed264e)


## Result
Thus the generated text image is eroded and dilated using python and OpenCV.
