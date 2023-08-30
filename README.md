# Image-Acquisition-from-Web-Cameraa
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
<br>
Import OpenCV Package

### Step 2:
<br>
Capture Video from a Webcam. Use VideoCapture(0) to access the webcam and start capturing video.

### Step 3:
<br>
Read the Video or Image. Utilize 'imread' to read a video frame or image from the webcam


### Step 4:
<br>
Save Image to File. Employ 'imwrite' to save the captured image to a file.


### Step 5:
<br>
Display Video or Image. Use 'imshow' to display the captured video frame or image

### Step 6:
<br>
End the Program with 'q'. Allow the program to be terminated by pressing the 'q' key

## Program:
``` Python
### Developed By: Jeswanth
### Register No:212221230042
```
## i) Write the frame as JPG file
```
import cv2
videoCaptureObject = cv2.VideoCapture(0)
while (True):
    ret,frame = videoCaptureObject.read()
    cv2.imwrite("Frame.jpeg",frame)
    result = False
videoCaptureObject.release()
cv2.destroyAllWindows()

```


## ii) Display the video
```
import cv2
videoCaptureObject = cv2.VideoCapture(0)
while(True):
    ret,frame = videoCaptureObject.read()
    cv2.imshow('video',frame)
    if cv2.waitKey(1) == ord('q'):
        break
videoCaptureObject.release()
cv2.destroyAllWindows()


```

## iii) Display the video by resizing the window

```
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
    cv2.imshow('resize', image)
    if cv2.waitKey(1) == ord('q'):
        break
cap.release()
cv2.destroyAllWindows()

```



## iv) Rotate and display the video

```
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
    cv2.imshow('rotate', image)
    if cv2.waitKey(1) == ord('q'):
        break
cap.release()
cv2.destroyAllWindows()








```
## Output

### i) Write the frame as JPG image
</br>
<img width="437" alt="image" src="https://github.com/Jeswanth21001768/Image-Acquisition-from-Web-Cameraa/assets/94155480/d8f8228d-7f24-4b85-9ae0-1f82287b3d82">

</br>


### ii) Display the video
</br>
<img width="435" alt="image" src="https://github.com/Jeswanth21001768/Image-Acquisition-from-Web-Cameraa/assets/94155480/d973dadd-3276-46d9-bd9e-e1e91df5d8cc">

</br>


### iii) Display the video by resizing the window
</br>
<img width="436" alt="image" src="https://github.com/Jeswanth21001768/Image-Acquisition-from-Web-Cameraa/assets/94155480/c3845d4d-29ed-4bc5-ba13-9a580dd21722">

</br>



### iv) Rotate and display the video
</br>
<img width="437" alt="image" src="https://github.com/Jeswanth21001768/Image-Acquisition-from-Web-Cameraa/assets/94155480/2ee3f451-9c23-4d14-b71e-49ac76358c3c">

</br>





## Result:
Thus the image is accessed from webcamera and displayed using openCV.
