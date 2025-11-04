# Edge-Linking-using-Hough-Transformm
## Aim:
To write a Python program to detect the lines using Hough Transform.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:

Import all the necessary modules for the program.
### Step2:

Load a image using imread() from cv2 module.
### Step3:

Convert the image to grayscale.
### Step4:

Using Canny operator from cv2,detect the edges of the image.
### Step5:

Using the HoughLinesP(),detect line co-ordinates for every points in the images.Using For loop,draw the lines on the found co-ordinates.Display the image.

## Program
## Developed By: INIYASRI S
## Reg.No.: 212223230081

## Input image
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
image = cv2.imread('Qn_7_.jpg')
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Convert image to RGB for displaying
plt.title("Input Image")
plt.axis('off')
```
## Grayscale image
```
plt.imshow(gray_image, cmap='gray')
plt.title("Grayscale Image")
plt.axis('off')
```
## Canny Edge detector output
```
edges = cv2.Canny(gray_image, 50, 150)
plt.imshow(edges, cmap='gray')
plt.title("Canny Edge Detector")
plt.axis('off')
```
## Display the result of Hough transform
```
lines = cv2.HoughLinesP(edges, 1, np.pi / 180, 100, minLineLength=50, maxLineGap=10)
for line in lines:
    x1, y1, x2, y2 = line[0]  # Unpacking the line coordinates
    cv2.line(image, (x1, y1), (x2, y2), (0, 255, 0), 2)  # Draw green lines with thickness of 2
# Display the result of Hough Transform (Image with lines)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Image with lines drawn
plt.title("Result of Hough Transform")
plt.axis('off')
```

## Output
### Input image  

<img width="512" height="490" alt="image" src="https://github.com/user-attachments/assets/028025af-1c70-4512-9554-8fccb825dc17" />

### Grayscale image

<img width="457" height="496" alt="image" src="https://github.com/user-attachments/assets/cca81e49-2599-41c8-a348-9f8f7c1ed726" />

### Canny Edge detector output

<img width="504" height="512" alt="image" src="https://github.com/user-attachments/assets/2f58880a-5b4c-476e-ba49-9c22a4867e77" />

### Display the result of Hough transform

<img width="459" height="480" alt="image" src="https://github.com/user-attachments/assets/d56d0b30-cf93-4e9f-98b4-2e6c7f32023e" />

## Result:
 Thus the python program to detect the lines using Hough Transform was successfully completed.
