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
``` Python
### Developed By: Abishek Xavier A
### Register No: 212222230004
```

## i) Write the frame as JPG file
```Python
import cv2
viedoCaptureObject=cv2.VideoCapture(0)
while(True):
    ret,frame=viedoCaptureObject.read()
    cv2.imwrite("abishek.jpg",frame)
    result=False
viedoCaptureObject.release()
cv2.destroyAllWindows()
```
## ii) Display the video
```Python
import numpy as np
import cv2
cap=cv2.VideoCapture(0)
while True:
    ret,frame=cap.read()
    cv2.imshow('lion',frame)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```
## iii) Display the video by resizing the window
```Python
import numpy as np
import cv2
cap=cv2.VideoCapture(0)
while True:
    ret,frame=cap.read()
    width=int(cap.get(3))
    height=int(cap.get(4))
    image=np.zeros(frame.shape,np.uint8)
    smaller_frame=cv2.resize(frame,(0,0),fx=0.5,fy=0.5)
    image[:height//2, :width//2]=smaller_frame
    image[height//2:, :width//2]=smaller_frame
    image[:height//2, width//2:]=smaller_frame
    image[height//2:, width//2:]=smaller_frame
    cv2.imshow('212222230004_abishek',image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```
## iv) Rotate and display the video
```Python
import numpy as np
import cv2
cap=cv2.VideoCapture(0)
while True:
    ret,frame=cap.read()
    width=int(cap.get(3))
    height=int(cap.get(4))
    image=np.zeros(frame.shape,np.uint8)
    smaller_frame=cv2.resize(frame,(0,0),fx=0.5,fy=0.5)
    image[:height//2, :width//2]=cv2.rotate(smaller_frame,cv2.ROTATE_180)
    image[height//2:, :width//2]=smaller_frame
    image[:height//2, width//2:]=cv2.rotate(smaller_frame,cv2.ROTATE_180)
    image[height//2:, width//2:]=smaller_frame
    cv2.imshow('212222230004_abishek',image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```
## Output
### i) Write the frame as JPG image
![Screenshot 2024-02-22 223708](https://github.com/AbishekAnand15/Image_Acqusition-_using_Web_Camera/assets/118706942/71a6787a-cefe-498f-a7a9-29fd36792f49)
</br>
</br>

### ii) Display the video
![Screenshot 2024-02-22 222200](https://github.com/AbishekAnand15/Image_Acqusition-_using_Web_Camera/assets/118706942/b8f32bfe-57d8-4ecc-b730-eb562404eae4)

</br>
</br>

### iii) Display the video by resizing the window
![WhatsApp Image 2024-02-22 at 23 26 49_d006ec67](https://github.com/AbishekAnand15/Image_Acqusition-_using_Web_Camera/assets/118706942/1c6a8091-cc54-4164-9e4e-ac151fb67249)
</br>
</br>

### iv) Rotate and display the video
![WhatsApp Image 2024-02-22 at 23 28 24_b2280c11](https://github.com/AbishekAnand15/Image_Acqusition-_using_Web_Camera/assets/118706942/a3caf2b2-c008-4950-95b3-59d0c50a9817)
</br>
</br>

## Result:
Thus the image is accessed from webcamera and displayed using openCV.
