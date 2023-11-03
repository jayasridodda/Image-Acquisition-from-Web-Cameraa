# Image-Acquisition-from-Web-Cameraa
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
Use VideoCapture(0) to access web camera

### Step 2:
Use imread to read the video or image

### Step 3:
Use imwrite to save the image

### Step 4:
Use imshow to show the video

### Step 5:
End the program and close the output video windows by pressing 'q'.

## Program:
``` Python
### Developed By: DODDA JAYASRI
### Register No: 212222240028
```

## i) Write the frame as JPG file
```python
import cv2
videoCaptureObject = cv2.VideoCapture(0)
while (True):
    ret,frame = videoCaptureObject.read()
    cv2.imwrite("Dhanumalya.jpeg",frame)
    result = False
videoCaptureObject.release()
cv2.destroyAllWindows()
```


## ii) Display the video
```python
import cv2
videoCaptureObject = cv2.VideoCapture(0)
while(True):
    ret,frame = videoCaptureObject.read()
    cv2.imshow('myimage',frame)
    if cv2.waitKey(1) == ord('q'):
        break
videoCaptureObject.release()
cv2.destroyAllWindows()
```



## iii) Display the video by resizing the window
```python
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
```python
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

![Screenshot from 2023-08-17 21-53-09](https://github.com/Dhanudhanaraj/Image-Acquisition-from-Web-Cameraa/assets/119218812/0b072673-4746-426c-9ed7-36134a0e114e)


### ii) Display the video
![Screenshot from 2023-08-17 21-59-31](https://github.com/Dhanudhanaraj/Image-Acquisition-from-Web-Cameraa/assets/119218812/47d523ed-1825-4531-8163-38fbcfb7f5eb)



### iii) Display the video by resizing the window
![Screenshot from 2023-08-17 22-10-17](https://github.com/Dhanudhanaraj/Image-Acquisition-from-Web-Cameraa/assets/119218812/8ee896cf-ea92-4760-90d5-4defffd2a0ec)



### iv) Rotate and display the video
![Screenshot from 2023-08-17 22-24-00](https://github.com/Dhanudhanaraj/Image-Acquisition-from-Web-Cameraa/assets/119218812/984414f8-eae1-4f21-b0cb-830e317be7c6)






## Result:
Thus the image is accessed from webcamera and displayed using openCV.
