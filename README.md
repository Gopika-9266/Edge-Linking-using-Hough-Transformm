# Edge-Linking-using-Hough-Transformm
## Aim:
To write a Python program to detect the lines using Hough Transform.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step 1:

Import all the necessary modules for the program.
### Step 2:

Load a image using imread() from cv2 module.
### Step 3:

Convert the image to grayscale.
### Step 4:

Using Canny operator from cv2,detect the edges of the image.
### Step 5:

Using the HoughLinesP(),detect line co-ordinates for every points in the images.Using For loop,draw the lines on the found co-ordinates.Display the image.

## Program:
```
Developed By: Gopika R
Register No: 212222240031

import cv2
import numpy as np
r=cv2.imread('gate.jpg',-1)
gray=cv2.cvtColor(r,cv2.COLOR_BGR2GRAY)
img = cv2.GaussianBlur(gray,(3,3),0)
cv2.imshow('original',r)
cv2.waitKey(0)
cv2.destroyAllWindows()
cv2.imshow('gray',gray)
cv2.waitKey(0)
cv2.destroyAllWindows()


canny_edges = cv2.Canny(img, 50, 120)
cv2.imshow('canny',canny_edges)
cv2.waitKey(0)
cv2.destroyAllWindows()

lines =cv2.HoughLinesP(canny_edges, 1, np.pi/180,threshold = 15, minLineLength =5 ,
maxLineGap = 7)

for line in lines:
 x1,y1,x2,y2 = line[0]
 cv2.line(r, (x1,y1),(x2,y2),(255,0,0),3)


cv2.imshow('hough_detected',r)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
## Output:

### Input image and grayscale image
![Screenshot 2024-10-02 101541](https://github.com/user-attachments/assets/a6f1e7d8-b5eb-4c7e-aa86-2065baeb0e31)

![Screenshot 2024-10-02 101601](https://github.com/user-attachments/assets/b02b1759-50b8-4d6a-8abc-51f22e97a99f)

### Canny Edge detector output

![Screenshot 2024-10-02 101643](https://github.com/user-attachments/assets/7777e060-3431-4632-bc3f-9274c6ca0e95)

### Display the result of Hough transform
![Screenshot 2024-10-02 101707](https://github.com/user-attachments/assets/c53b5cc2-155c-4feb-b49e-951cfb7ae90f)


## Result:

Thus the program is written with Python and OpenCV to detect lines using Hough transform.
