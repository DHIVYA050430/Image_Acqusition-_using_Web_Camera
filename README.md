# Image Acqusition using Web Camera
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
<br>
Use cv2.VideoCapture(0) to access web camera.
<br>

### Step 2:
<br>
Use cv2.imread to read the video or image.
<br>

### Step 3:
<br>
Use cv2.imwrite to save the image.
<br>

### Step 4:
<br>
Use cv2.imshow to show the video.
<br>

### Step 5:
<br>
End the program and close the output video window by pressing 'q'.
<br>

## Program:

### Developed By: DIVYA e
### Register No: 212223230050

## i) Write the frame as JPG file

```
import cv2
videoCaptureObject = cv2.VideoCapture(0)
ret, frame = videoCaptureObject.read()
if ret:
    cv2.imwrite("web.jpg", frame)
    print("Image saved as web.jpg")
else:
    print("Failed to capture image")
videoCaptureObject.release()
cv2.destroyAllWindows()
```



## ii) Display the video
```
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

```
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

```
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

</br>

![image](https://github.com/user-attachments/assets/e6e36dcb-a870-499e-bb71-88fd78ee9e22)

</br>


### ii) Display the video

</br>

![image](https://github.com/user-attachments/assets/fa12987c-fca3-43fb-9d19-d9455c2b42ff)

</br>


### iii) Display the video by resizing the window

</br>

![image](https://github.com/user-attachments/assets/3bdf6d4e-241c-42a7-8d25-300410cb649d)

</br>



### iv) Rotate and display the video

</br>

![image](https://github.com/user-attachments/assets/7c3b7604-2987-416a-86d6-d52997a308a9)

</br>





## Result:
Thus the image is accessed from webcamera and displayed using openCV.
