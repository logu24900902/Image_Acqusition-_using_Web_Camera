## DEVELOPED BY : R.LOGU
## REG NO : 212224230141
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
Use cv2.VideoCapture(0) to access web camera.

### Step 2:
Use cv2.imread to read the video or image.

### Step 3:
Use cv2.imwrite to save the image.

### Step 4:
Use cv2.imshow to show the video.

### Step 5:
End the program and close the output video window by pressing 'q'.

## Program:
``` Python
### Developed By: LOGU R
### Register No: 212224230141

## i) Write the frame as JPG file
import cv2
import matplotlib.pyplot as plt
from IPython.display import clear_output
import time
cap = cv2.VideoCapture(0)
ret, frame = cap.read()
if ret:
    cv2.imwrite("captured_frame.jpg", frame)
cap.release()
captured_image = cv2.imread('captured_frame.jpg')
plt.imshow(captured_image[:,:,::-1])
plt.title('Captured Frame')
plt.axis('off')
plt.show()

## ii) Display the video
cap = cv2.VideoCapture(0)

for i in range(50):
    ret, frame = cap.read()
    if not ret:
        break
    frame_rgb = cv2.cvtColor(frame, cv2.COLOR_BGR2RGB)
    clear_output(wait=True)
    plt.imshow(frame_rgb)
    plt.axis('off')
    plt.show()
    time.sleep(0.05)

cap.release()

## iii) Display the video by resizing the window

cap = cv2.VideoCapture(0)

for i in range(50):
    ret, frame = cap.read()
    if not ret:
        break
    resized_frame = cv2.resize(frame, (100, 150))  # Resize to 320x240
    frame_rgb = cv2.cvtColor(resized_frame, cv2.COLOR_BGR2RGB)
    clear_output(wait=True)
    plt.imshow(frame_rgb)
    plt.axis('off')
    plt.show()
    time.sleep(0.05)

cap.release()



## iv) Rotate and display the video

cap = cv2.VideoCapture(0)

for i in range(50):
    ret, frame = cap.read()
    if not ret:
        break
    rotated_frame = cv2.rotate(frame, cv2.ROTATE_90_CLOCKWISE)
    frame_rgb = cv2.cvtColor(rotated_frame, cv2.COLOR_BGR2RGB)
    clear_output(wait=True)
    plt.imshow(frame_rgb)
    plt.axis('off')
    plt.show()
    time.sleep(0.05)

cap.release()






```
## Output

### i) Write the frame as JPG image
</br>
<img width="614" height="507" alt="image" src="https://github.com/user-attachments/assets/b89de14d-dc3c-4dad-a712-c840c46af509" />

</br>


### ii) Display the video
</br>
<img width="638" height="470" alt="image" src="https://github.com/user-attachments/assets/4bad08f8-6621-43b7-b6d4-b6d2b95101f0" />

</br>


### iii) Display the video by resizing the window
</br>
<img width="381" height="480" alt="image" src="https://github.com/user-attachments/assets/3494d067-801e-45a9-84cc-1c038145144d" />

</br>



### iv) Rotate and display the video
</br>
<img width="387" height="487" alt="image" src="https://github.com/user-attachments/assets/04953c14-e25e-40dc-a103-769caf724701" />

</br>





## Result:
Thus the image is accessed from webcamera and displayed using openCV.
