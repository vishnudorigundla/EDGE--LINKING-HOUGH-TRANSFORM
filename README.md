# Edge-Linking-using-Hough-Transform
## Aim:
To write a Python program to detect the lines using Hough Transform.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
Import the required modules. 

### Step2:
Import the image to operate on. 

### Step3:
Convert the imported image from BGR to GRAYSCALE. 

### Step4:
Find the edges using canny edge detector and display the image. 

### Step5:
Detect the points that form a line using hough transform. 

### Step6:
Draw the lines on the image

### Step7:
Display the output

### Step8:
End the program. 


## Program:
```
Developed By : D.Vishnu vardhan reddy
Reg.No : 212221230023

```
```Python

# Read image and convert it to grayscale image

import numpy as np
import cv2
import matplotlib.pyplot as plt
img=cv2.imread("car.jpg",0)
img_c=cv2.imread("car.jpg",1)
img_c=cv2.cvtColor(img_c,cv2.COLOR_BGR2RGB)
gray=cv2.cvtColor(img,cv2.COLOR_GRAY2RGB)
gray = cv2.GaussianBlur(gray,(3,3),0)
plt.figure(figsize=(13,13))
plt.subplot(1,2,1)
plt.imshow(img_c)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(gray)
plt.title("Gray Image")
plt.axis("off")
plt.show()



# Find the edges in the image using canny detector and display
canny=cv2.Canny(gray,120,150)
plt.imshow(canny)
plt.title("Canny Edge Detector")
plt.axis("off")
plt.show()

# Detect points that form a line using HoughLinesP

lines=cv2.HoughLinesP(canny,1,np.pi/180,threshold=80,minLineLength=50,maxLineGap=250)


# Draw lines on the image

for line in lines:
    x1,y1,x2,y2=line[0]
    cv2.line(img_c,(x1,y1),(x2,y2),(255,0,0),3)


# Display the result
plt.imshow(img_c)
plt.title("Result Image")
plt.axis("off")
plt.show()



```
## Output

### Input image and grayscale image
![image](https://github.com/vishnudorigundla/EDGE--LINKING-HOUGH-TRANSFORM/assets/94175324/72180d28-e46f-4a14-a3d4-1df2a5625cff)

### Canny Edge detector output
![image](https://github.com/vishnudorigundla/EDGE--LINKING-HOUGH-TRANSFORM/assets/94175324/bff96ab0-633c-445c-b608-1b4a71465693)


### Display the result of Hough transform
![image](https://github.com/vishnudorigundla/EDGE--LINKING-HOUGH-TRANSFORM/assets/94175324/30b14047-f08e-41eb-9fa6-b734ae353e4b)


## Result:
Thus the program is written with python and OpenCV to detect lines using Hough transform. 
