# Face-detection-using-opencv
Face detection python program using opencv.

# Detect face from Image.
OpenCV already contains many pre-trained classifiers for face, eyes, smile etc.
loading the required XML classifiers.(Line 3)

loading the required image.(image must be saved in the same folder as program).(Line 5)

We use v2.CascadeClassifier.detectMultiScale() to find faces or eyes, and it is defined like this:
cv2.CascadeClassifier.detectMultiScale(image, scaleFactor, minNeighbors) (line 9)

Where the parameters are:

image : Matrix containing an image where objects are detected.
scaleFactor : Parameter specifying how much the image size is reduced at each image scale.
Suppose, the scale factor is 1.03, it means we're using a small step for resizing, i.e. reduce size by 3 %, we increase the chance of a matching size with the model for detection is found.

minNeighbors : Parameter specifying how many neighbors each candidate rectangle should have to retain it. This parameter will affect the quality of the detected faces: higher value results in less detections but with higher quality. We're using 5 in the code.
If faces are found, it returns the list of positions of detected faces as Rect(x,y,w,h).
where:
x=1st/top left corner of the rectangle
y=bottom-left cornerof the rectangle.
w=width
h=height
syntax:
faces = face_cascade.detectMultiScale(gray, 1.1, 4)

cv2.rectangle(img,(x,y),(x+w, y+h),(255,0,0),2) (line 12)
The rectangle function is used to draw the rectangle around the face's present in the image. it takes 5 parameters which are:  
img= image to be shown
(x,y),(x+w, y+h)= Co-ordinates of the rectangle
(255,0,0)= Colour of the rectangle i.e blue in this case in format of BGR.
2= width of the rectangle border

cv2.imshow('img',img) (line 14)
To output the image with face detected.

cv2.waitKey(0) (line 15)
To stop the screen from closing automatically.

