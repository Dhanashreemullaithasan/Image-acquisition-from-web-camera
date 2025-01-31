# Image-Acquisition-from-Web-Camera
## Aim
 
Aim:
 
To write a python program using OpenCV to capture the image from the web camera and do the following image manipulations.
i) Write the frame as JPG 
ii) Display the video 
iii) Display the video by resizing the window
iv) Rotate and display the video

## Software Used
Anaconda - Python 3.7
## Algorithm:

Step 1:

Import cv2 and capture the video using cv2.VideoCapture(0).

Step 2:

Write the captured image using cv2.imwrite("NewPicture.jpg",frame).

Step 3:

Resize the image using cv2.resize(frame, (0,0), fx = 0.5, fy=0.5).

Step 4:

Display the image until the loop gets over.

Step 5:

Rotate the image using cv2.rotate(smaller_frame,cv2.cv2.ROTATE_180).

## Program:
### Developed By:DHANASHREE M
### Register No:212221230018

## i) Write the frame as JPG file
```
import cv2
img = cv2.VideoCapture(0)
while(True):
    imagee,frame = img.read()
    cv2.imshow('myimage',frame)
    if cv2.waitKey(1) == ord('c'):
        break
img.release()
cv2.destroyAllWindows()
```


## ii) Display the video

```
import cv2
video = cv2.VideoCapture(0)
while (True):
    cap,frame=video.read()
    cv2.imshow('Capturing Video',frame)
    if cv2.waitKey(1) == ord('q'):
        break
video.release()
```

## iii) Display the video by resizing the window

```
import cv2
import numpy as np
img  = cv2.VideoCapture(0)
while True:
    pic,frame = img.read()
    width = int(img.get(3))
    height = int(img.get(4))
    image = np.zeros(frame.shape, np.uint8)
    small_frame = cv2.resize(frame,(0,0),fx =0.5, fy = 0.5)
    image[:height//2, :width//2]=small_frame
    image[height//2:, :width//2]=small_frame
    image[:height//2, width//2:]=small_frame
    image[height//2:, width//2:]=small_frame
    cv2.imshow('myimage',image)
    if cv2.waitKey(1) == ord('c'):
        break
img.release()
cv2.destroyAllWindows()
```


## iv) Rotate and display the video

```
import cv2
import numpy as np
img  = cv2.VideoCapture(0)
while True:
    pic,frame = img.read()
    width = int(img.get(3))
    height = int(img.get(4))
    image = np.zeros(frame.shape, np.uint8)
    small_frame = cv2.resize(frame,(0,0),fx =0.5, fy = 0.5)
    image[:height//2, :width//2]=cv2.rotate(small_frame,cv2.ROTATE_180)
    image[height//2:, :width//2]=small_frame
    image[:height//2, width//2:]=small_frame
    image[height//2:, width//2:]=cv2.rotate(small_frame,cv2.ROTATE_180)
    cv2.imshow('myimage',image)
    if cv2.waitKey(1) == ord('c'):
        break
img.release()
cv2.destroyAllWindows()
```
## Output

### i) Write the frame as JPG image

![ima11 dip ex2](https://user-images.githubusercontent.com/94165415/226949112-78f175ff-7c55-4f9e-9137-e3e09034efce.png)


### ii) Display the video

![img1](https://user-images.githubusercontent.com/94165415/226974857-27a0ed74-2a99-4c4a-924b-430dd8c6a176.png)


### iii) Display the video by resizing the window

![img3](https://user-images.githubusercontent.com/94165415/226974992-fa8d75cc-d77d-49fa-90d2-35fd6af9051d.png)


### iv) Rotate and display the video


![dipex3img4](https://user-images.githubusercontent.com/94165415/226977992-919e8796-750d-4b3c-a2c4-e95bc389ab8f.png)

## Result:
Thus the image is accessed from webcamera and displayed using openCV.
