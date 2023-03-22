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
## Algorithm
### Step 1:
Import cv2 and capture the video using cv2.VideoCapture(0).

### Step 2:
Write the captured image using cv2.imwrite("NewPicture.jpg",frame).

### Step 3:
Resize the image using cv2.resize(frame, (0,0), fx = 0.5, fy=0.5)

### Step 4:
Display the image until the loop gets over.

### Step 5:
Rotate the image using cv2.rotate(smaller_frame,cv2.cv2.ROTATE_180)
### Program:
### Developed By:M.Harikrishna
### Register No:212221230059

## i) Write the frame as JPG file

```
import cv2
obj = cv2.VideoCapture(0)
while(True):
    cap,frame = obj.read()
    cv2.imshow('video.jpg',frame)
    cv2.imwrite("keychain.jpg",frame)
    if cv2.waitKey(1) == ord('q'):
        break
obj.release()
cv2.destroyAllWindows()
```

## ii) Display the video
```
import cv2
object=cv2.VideoCapture(0)
while(True):
    ret,frame=object.read()
    cv2.imshow('CUTE',frame)
    if cv2.waitKey(1)==ord('q'):
        break
object.release()
cv2.destroyAllWindows()
```



## iii) Display the video by resizing the window

```
import numpy as np
import cv2
cap = cv2.VideoCapture(0)
while True:
    ret, frame = cap.read()
    width = int(cap.get(3))
    height = int(cap.get(4))
    
    image = np.zeros(frame.shape, np.uint8)
    smaller_frame = cv2.resize(frame, (0,0), fx = 0.5, fy=0.5)
    image[:height//2, :width//2] = smaller_frame
    image[height//2:, :width//2] = smaller_frame
    image[:height//2, width//2:] = smaller_frame
    image[height//2:, width//2:] = smaller_frame

    cv2.imshow('frame', image)
    if cv2.waitKey(1) == ord('q'):
        break
cap.release()
cv2.destroyAllWindows()

## iv) Rotate and display the video
import numpy as np
import cv2
cap = cv2.VideoCapture(0)
while True:
    ret, frame = cap.read()
    width = int(cap.get(3))
    height = int(cap.get(4))
    image = np.zeros(frame.shape, np.uint8)
    smaller_frame = cv2.resize(frame, (0,0), fx = 0.5, fy=0.5)
    image[:height//2, :width//2] = cv2.rotate(smaller_frame,cv2.ROTATE_180)
    image[height//2:,: width//2] = smaller_frame
    image[:height//2, width//2:] = cv2.rotate(smaller_frame,cv2.ROTATE_180)
    image[height//2:, width//2:] = smaller_frame
    cv2.imshow('frame', image)
    if cv2.waitKey(1) == ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```




## Output

### i) Write the frame as JPG image
![d1](https://user-images.githubusercontent.com/94747031/226684147-87adb00f-cf71-4132-a9d4-405ce4711bc9.png)


### ii) Display the video
![d2](https://user-images.githubusercontent.com/94747031/226684263-31d391ce-0818-4520-a083-d58800c14340.png)

### iii) Display the video by resizing the window
![d3](https://user-images.githubusercontent.com/94747031/226684255-cb0ac7f1-ebc1-43ac-8040-18936ad4fd9c.png)



### iv) Rotate and display the video
![d4](https://user-images.githubusercontent.com/94747031/226684240-75caccae-fb8e-464e-a3fc-9b1bc16b55a8.png)





## Result:
Thus the image is accessed from webcamera and displayed using openCV.
