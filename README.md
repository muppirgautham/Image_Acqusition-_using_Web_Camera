# Image_Acqusition-_using_Web_Camera
## Aim
 
To write a python program using OpenCV to capture the image from the web camera and do the following image manipulations.

i) Write the frame as JPG

ii) Display the video

iii) Display the video by resizing the window

iv) Rotate and display the video

## Software Used
Anaconda - Python 3.7
## Algorithm
### Step 1:
Use cv2.VideoCapture(0) to access web camera
<br>

### Step 2:
Use cv2.imread to read the video or image
<br>

### Step 3:
Use cv2.imwrite to save the image
<br>

### Step 4:
Use cv2.imshow to show the video
<br>

### Step 5:
End the program and close the output video window by pressing 'q'.
<br>

## Program:
### Developed By: M Gautham 
### Register No: 212221230027

## i) Write the frame as JPG file
```python
import cv2
video = cv2.VideoCapture(0)
while(True):
    t,frame = video.read()
    cv2.imwrite("car.jpg",frame)
    result=False
video.release()
cv2.destroyAllWindows()
```
## ii) Display the video
```python
import cv2
pic = cv2.VideoCapture(0)
while True:
    t,frame = pic.read()
    cv2.imshow('car',frame)
    if cv2.waitKey(1) == ord('b'):
        break
pic.release()
cv2.destroyAllWindows()
```
## iii) Display the video by resizing the window
```python
import numpy as np
import cv2
im = cv2.VideoCapture(0)
while True:
    ret,frame = im.read()
    width = int(im.get(3))
    height = int(im.get(4))
    image = np.zeros(frame.shape,np.uint8)
    smallerFrame = cv2.resize(frame,(0,0),fx = 0.5,fy=0.5)
    image[:height//2,:width//2] = smallerFrame
    image[height//2:, :width // 2] = smallerFrame
    image[:height//2, width//2:] = smallerFrame
    image[height//2:, width//2:] = smallerFrame
    cv2.imshow('car',image)
    if cv2.waitKey(1) == ord('b'):
        break
im.release()
cv2.destroyAllWindows()
```
## iv) Rotate and display the video
```python
import numpy as np
import cv2
im = cv2.VideoCapture(0)
while True:
    ret,frame = im.read()
    width = int(im.get(3))
    height = int(im.get(4))
    image = np.zeros(frame.shape,np.uint8)
    smallerFrame = cv2.resize(frame,(0,0),fx = 0.5,fy=0.5)
    image[:height//2,:width//2] = cv2.rotate(smallerFrame,cv2.ROTATE_180)
    image[height//2:, :width // 2] = smallerFrame
    image[:height//2, width//2:] = smallerFrame
    image[height//2:, width//2:] = cv2.rotate(smallerFrame,cv2.ROTATE_180)
    cv2.imshow('car',image)
    if cv2.waitKey(1) == ord('b'):
        break
im.release()
cv2.destroyAllWindows()
```
## Output

### i) Write the frame as JPG image
![Screenshot 2024-03-10 205740](https://github.com/muppirgautham/Image_Acqusition-_using_Web_Camera/assets/94810884/e35dab71-fafb-4a0d-947a-eb3043073103)

</br>
</br>


### ii) Display the video
![Screenshot 2024-03-10 210045](https://github.com/muppirgautham/Image_Acqusition-_using_Web_Camera/assets/94810884/71eaa6e4-f3c7-4e58-82d2-e9db232eebb0)

</br>
</br>


### iii) Display the video by resizing the window
![Screenshot 2024-03-10 210412](https://github.com/muppirgautham/Image_Acqusition-_using_Web_Camera/assets/94810884/6f6e9a3a-64ba-4c8c-b3fb-6d890797037d)

</br>
</br>



### iv) Rotate and display the video
![Screenshot 2024-03-10 210628](https://github.com/muppirgautham/Image_Acqusition-_using_Web_Camera/assets/94810884/08128d77-e516-4c6b-a711-b68f58ee562c)

</br>
</br>

## Result:
Thus the image is accessed from webcamera and displayed using openCV.
