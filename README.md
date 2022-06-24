### EX NO: 02
### DATE:
# <p align="center">IMAGE ACQUISITION FROM WEB CAMERA</p>

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
Import cv2 and capture the video using cv2.VideoCapture(0)
### Step 2:
Write the captured image using cv2.imwrite("image.jpg",frame)
### Step 3:
Resize the image using cv2.resize(frame, (0,0), fx = 0.5, fy=0.5)
### Step 4:
display the image until the loop gets over
### Step 5:

Rotate the image using cv2.rotate(smaller_frame,cv2.cv2.ROTATE_180)
## Program:
```
### Developed By:N Sandhya Charu
### Register No:212220230041
```
### i) Write the frame as JPG file
```python3
import cv2

videoCaptureObject = cv2.VideoCapture(0)
ret,frame = videoCaptureObject.read()
cv2.imwrite("image.jpg",frame)

```
### ii) Display the video
```python3
import cv2
import numpy as np

cap = cv2.VideoCapture(0)

while True:
    ret, frame = cap.read()

    cv2.imshow("image",frame)
    if cv2.waitKey(1) & 0xFF == ord('q'):
        break
videoCaptureObject.release()
cv2.destroyAllWindows()
```

### iii) Display the video by resizing the window
```python3
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
    image[height//2:, width//2:] = smaller_frame

    image[:height//2, :width//2] = cv2.rotate(smaller_frame,cv2.cv2.ROTATE_180)
    cv2.imshow("image.jpg",image)
    if cv2.waitKey(1) & 0xFF == ord('q'):
        break
videoCaptureObject.release()
cv2.destroyAllWindows()
```

### iv) Rotate and display the video
```python3
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

    image[:height//2, :width//2] = cv2.rotate(smaller_frame,cv2.cv2.ROTATE_180)

    cv2.imshow("image.jpg",image)
    if cv2.waitKey(1) & 0xFF == ord('q'):
        break
videoCaptureObject.release()
cv2.destroyAllWindows()

```
## Output

### i) Write the frame as JPG image

![Picture2 jpg - Google Chrome 08-04-2022 08_21_28](https://user-images.githubusercontent.com/75235167/162354439-f22045c1-5936-4ce3-8808-d4f905fb89dd.png)

### ii) Display the video

![image](https://user-images.githubusercontent.com/75235167/162352421-fb82a30b-957f-433d-9bef-e9822728a94f.png)

### iii) Display the video by resizing the window

![image](https://user-images.githubusercontent.com/75235167/162353054-c5d2cca5-8291-4c86-8485-172896b3acd3.png)


### iv) Rotate and display the video

![image](https://user-images.githubusercontent.com/75235167/162353158-8781da2b-f8ef-4f09-b6d3-7207d8e03105.png)

## Result:
Thus the image is accessed from webcamera and displayed using openCV.
