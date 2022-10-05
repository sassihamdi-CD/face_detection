## Table of contents
* [General info](#general-info)
* [Technologies](#technologies)
* [Setup](#setup)

## General info
A Face Recognition Code in Python can detect faces of people in an images, faces contains a list of coordinates for the rectangular regions where faces were found.

We use these coordinates to draw the rectangles in our image. And also the Face Detection Using Python Project can detect also real time faces in a camera on your laptop or pc.

Similarly, the Face Detection In Python Using Opencv can detect faces in videos. As you know videos are basically made up of frames, which are still images. So we perform the face detection for each frame in a video.

The only difference here is that we use an infinite loop to loop through each frame in the video. We use cap.read() to read each frame.
The first value returned is a flag that indicates if the frame was read correctly or not. We don’t need it. The second value returned is the still frame on which we will be performing the detection.


## Technologies
Project Name:	Face Recognition In Python
Language/s Used:	Python OpenCV
Python version (Recommended):	2.x or 3.x
Database:	None
Type:	Machine Learning

## Setup
# Steps on How To Build Face Recognition Code In Python Using OpenCV



Step 1: Download and unzip the zip file.
First, download the source code given below and unzip the zip file.

The project folder contains 4 files:

1.) detect_face_image.py – a python file for detecting face in an image.
2.) detect_face_video.py – a python file for detecting face in a camera.
3.) haarcascade_frontalface_default_default.xml – a file that load cascade from image.
4.) sample.jpg – sample image for experimenting in detecting face.download source code

Step 2: Creating code for detecting faces in an image.
Next, we want to create code for load cascade, read the input image and convert into grayscale, detect faces, draw rectangle around faces and display the output.
*Note: The code given below are already in a download source code.
face recognition detecting faces in an image
Step 3: Creating Code for detecting faces in a video.
Next, in the same process in step 2, we want to create a code for detecting faces in a video.
*Note: The code given below are already in a download source code.
face recognition detecting faces in a video

Step 4: Run detect_face_image python file.
The beginner Python project is now complete, you can run the Python file from the command prompt. Make sure to give an image path using ‘-i’ argument.

If the image is in another directory, then you need to give full path of the image:

face detection run image
Step 5: Run detect_face_video python file.
The beginner Python project is now complete, you can run the Python file from the command prompt.

face detection run camera
Face Recognition In An Image
I have here the step by step program which can detect faces in an Image.
1. Import OpenCV
'import cv2'
Explanation:
The code given above is the required libraries to be import.
2. Load Face Cascade Dataset
# Load the cascade
'face_cascade = cv2.CascadeClassifier('haarcascade_frontalface_default.xml')'
Explanation:
The code given above is the face_cascade dataset which can be extracted when we run the project to detect faces in an image.
3. Read The Input Image
Code:
# Read the input image
img = cv2.imread('sample.jpg')
Explanation:
The code given above is the function to read the input image.
4. Convert Image Into Grayscale
Code:
# Convert into grayscale
gray = cv2.cvtColor(img, cv2.COLOR_BGR2GRAY)
Explanation:
The code given above is the function to convert the image into grayscale.
5. Detect Faces
Code:
# Detect faces
faces = face_cascade.detectMultiScale(gray, 1.1, 4)
Explanation:
The code given above is the function to detect faces from the given image.

6. Draw Rectangle Around The Faces
Code:

# Draw rectangle around the faces
for (x, y, w, h) in faces:
    cv2.rectangle(img, (x, y), (x + w, y + h), (255, 0, 0), 2)
Explanation:
The code given above is the function to draw rectangle around the faces in an image.

7. Display The Output
Code:

# Display the output
cv2.imshow('img', img)
cv2.waitKey()
Explanation:

The code given above is the function to display the output.

Output


Complete Source Code of Face Recognition In An Image
import cv2

# Load the cascade
Code:
face_cascade = cv2.CascadeClassifier('haarcascade_frontalface_default.xml')

# Read the input image
Code:
img = cv2.imread('sample.jpg')

# Convert into grayscale
Code:
gray = cv2.cvtColor(img, cv2.COLOR_BGR2GRAY)

# Detect faces
Code:
faces = face_cascade.detectMultiScale(gray, 1.1, 4)

# Draw rectangle around the faces
Code:
for (x, y, w, h) in faces:
    cv2.rectangle(img, (x, y), (x + w, y + h), (255, 0, 0), 2)

# Display the output
cv2.imshow('img', img)
cv2.waitKey()
Real-Time Face Recognition Using Web Cam
Here’s the step by step program on How To Detect Faces In Real-Time using Web Cam.

1. Import OpenCV
Code:

import cv2
Explanation:

The code given above is the required libraries to be import.

2. Load Cascade Dataset
Code:

# Load the cascade
Code:
face_cascade = cv2.CascadeClassifier('haarcascade_frontalface_default.xml')
Explanation:

The code given above is the face_cascade dataset which can be extracted when we run the project to detect faces in an image.

3. Capture Video From Web Cam
Code:

# To capture video from webcam. 
cap = cv2.VideoCapture(0)
Explanation:

The code given above is the function to capture video from webcam.

4. Convert To Grayscale
Code:

# Read the frame
Code:
    _, img = cap.read()
    # Convert to grayscale
    gray = cv2.cvtColor(img, cv2.COLOR_BGR2GRAY)
The code given above is the function to convert video into grayscale.

5. Detect Faces
Code:

# Detect the faces
    faces = face_cascade.detectMultiScale(gray, 1.1, 4)
Explanation:

The code given above is the function to detect faces in the web cam.

6. Draw Rectangle Around The Faces
Code:

# Draw the rectangle around each face
Code:
    for (x, y, w, h) in faces:
        cv2.rectangle(img, (x, y), (x+w, y+h), (255, 0, 0), 2)
Explanation:

The code given above is the function to draw rectangle around the faces from the web cam.

Real-Time Face Recognition Output

Complete Source Code of Face Recognition in Real-Time
import cv2

# Load the cascade
Code:
face_cascade = cv2.CascadeClassifier('haarcascade_frontalface_default.xml')
# To capture video from webcam. 
Code:
cap = cv2.VideoCapture(0)
# To use a video file as input 
Code:
# cap = cv2.VideoCapture('filename.mp4')
Code:
while True:
    # Read the frame
    _, img = cap.read()
    # Convert to grayscale
    gray = cv2.cvtColor(img, cv2.COLOR_BGR2GRAY)
    # Detect the faces
    faces = face_cascade.detectMultiScale(gray, 1.1, 4)
    # Draw the rectangle around each face
    for (x, y, w, h) in faces:
        cv2.rectangle(img, (x, y), (x+w, y+h), (255, 0, 0), 2)
    # Display
    cv2.imshow('img', img)
    # Stop if escape key is pressed
    k = cv2.waitKey(30) & 0xff
    if k==27:
        break
# Release the VideoCapture object
cap.release()
Download Source Code below
Click Here To Download The Source Code!
Summary
Facial detection is a powerful and common use-case of Machine Learning. It can be used to automatize manual tasks such as school attendance and law enforcement. In the other hand, it can be used for biometric authorization.

OpenCV uses machine learning algorithms to search for faces within a picture. Because faces are so complicated, there isn’t one simple test that will tell you if it found a face or not.

Instead, there are thousands of small patterns and features that must be matched. The algorithms break the task of identifying the face into thousands of smaller, bite-sized tasks, each of which is easy to solve.

