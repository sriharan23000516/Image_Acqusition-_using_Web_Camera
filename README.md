# EX-02 : Image Acquisition using Web Camera
## Aim:
 
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
<br>

### Step 2:
Capture Video from Webcam. Use VideoCapture(0) to access the webcam and start capturing video.
<br>

### Step 3:
Read Video or Image. Utilize 'imread' to read a video frame or image from the webcam.
<br>

### Step 4:
Save Image to File. Employ 'imwrite' to save the captured image to a file.
<br>

### Step 5:
Display Video or Image. Use 'imshow' to display the captured video frame or image.
<br>

### Step 6:
End Program with 'q'. Allow the program to be terminated by pressing the 'q' key.
<br>

## Program:
```
### Developed By:  Sriharan J V
### Register No:  212223100054
```
## i) Write the frame as JPG file
``` Python
import cv2
videoCaptureObject = cv2.VideoCapture(0)
ret, frame = videoCaptureObject.read()
if ret:
    cv2.imwrite("img.jpg", frame)
    print("Image saved as img.jpg")
else:
    print("Failed to capture image")
videoCaptureObject.release()
cv2.destroyAllWindows()
```


## ii) Display the video
``` Python
import cv2
videoCaptureObject = cv2.VideoCapture(0)
while True:
    ret, frame = videoCaptureObject.read()
    cv2.imshow('myimage', frame)
    if cv2.waitKey(1) & 0xFF == ord('q'):
        break
videoCaptureObject.release()
cv2.destroyAllWindows()
```


## iii) Display the video by resizing the window
``` Python

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
```


## iv) Rotate and display the video
``` Python

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
![Screenshot 2024-09-23 211512](https://github.com/user-attachments/assets/2048bdb7-54ac-4dbd-9eb2-9e87df0d6657)

</br>
</br>


### ii) Display the video
![Screenshot 2024-09-23 210339](https://github.com/user-attachments/assets/76a8c8c4-52d6-4f2d-849e-b95f1fb4022d)

</br>
</br>


### iii) Display the video by resizing the window
![Screenshot 2024-09-23 210612](https://github.com/user-attachments/assets/cd16963f-f1f6-46d2-a47e-00ba3aac7627)

</br>
</br>



### iv) Rotate and display the video
![Screenshot 2024-09-23 210655](https://github.com/user-attachments/assets/cd94d5f6-d9b2-4ee0-aa83-053ccb344bf9)

</br>
</br>



## Result:
Thus the image is accessed from webcamera and displayed using openCV.
