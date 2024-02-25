# Image_Acqusition-_using_Web_Camera
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
Import OpenCV Package.

### Step 2:
Capture Video from Webcam. Use VideoCapture(0) to access the webcam and start capturing video.

### Step 3:
Read Video or Image. Utilize 'imread' to read a video frame or image from the webcam.

### Step 4:
Save Image to File. Employ 'imwrite' to save the captured image to a file.

### Step 5:
Display Video or Image. Use 'imshow' to display the captured video frame or image, and end Program with 'q'. Allow the program to be terminated by pressing the 'q' key.

## Program:
``` Python
### Developed By: GANESH R
### Register No: 212222240029


## i) Write the frame as JPG file
import cv2
videoCaptureObject = cv2.VideoCapture(0)
while (True):
    ret,frame = videoCaptureObject.read()
    cv2.imwrite("img.jpeg",frame)
    result = False
videoCaptureObject.release()
cv2.destroyAllWindows()


         OR

import cv2

videoCaptureObject = cv2.VideoCapture(0)
max_frames = 4  # Maximum number of frames to capture
frame_count = 0

while frame_count < max_frames:
    ret, frame = videoCaptureObject.read()
    cv2.imwrite(f"img_{frame_count}.jpeg", frame)
    frame_count += 1

videoCaptureObject.release()
cv2.destroyAllWindows()




## ii) Display the video
import cv2
videoCaptureObject = cv2.VideoCapture(0)
while(True):
    ret,frame = videoCaptureObject.read()
    cv2.imshow('myimage',frame)
    if cv2.waitKey(1) == ord('q'):
        break
videoCaptureObject.release()
cv2.destroyAllWindows()




## iii) Display the video by resizing the window
import cv2
import numpy as np
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
    image [height//2:, width//2:] = smaller_frame
    cv2.imshow('myimage', image)
    if cv2.waitKey(1) == ord('q'):
        break
cap.release()
cv2.destroyAllWindows()




## iv) Rotate and display the video
import cv2
import numpy as np
cap = cv2.VideoCapture(0)
while True:
    ret, frame = cap.read() 
    width = int(cap.get(3))
    height = int(cap.get(4))
    image = np.zeros(frame.shape, np.uint8) 
    smaller_frame = cv2.resize(frame, (0,0), fx = 0.5, fy=0.5) 
    image[:height//2, :width//2] = cv2.rotate(smaller_frame,cv2.ROTATE_180)
    image[height//2:, :width//2] = cv2.rotate(smaller_frame,cv2.ROTATE_180)
    image[:height//2, width//2:] = smaller_frame 
    image [height//2:, width//2:] = smaller_frame
    cv2.imshow('myimage', image)
    if cv2.waitKey(1) == ord('q'):
        break
cap.release()
cv2.destroyAllWindows()










```
## Output

### i) Write the frame as JPG image
![img](https://github.com/ganesha360/Image_Acqusition-_using_Web_Camera/assets/120884552/e865f1da-aa17-43ee-9821-f7b99e934c17)



### ii) Display the video
![videos](https://github.com/ganesha360/Image_Acqusition-_using_Web_Camera/assets/120884552/c04188ad-02c9-434c-9c1f-0e99763bd1aa)



### iii) Display the video by resizing the window
![display](https://github.com/ganesha360/Image_Acqusition-_using_Web_Camera/assets/120884552/9769a73d-442b-4ffe-a8cb-03b7d1374490)



### iv) Rotate and display the video
![myimage](https://github.com/ganesha360/Image_Acqusition-_using_Web_Camera/assets/120884552/99acb1ed-3ca0-42d3-a172-938dd977ecdd)





## Result:
Thus the image is accessed from webcamera and displayed using openCV.
