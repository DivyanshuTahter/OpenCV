import cv2
from random import randrange
trained_face_data = cv2.CascadeClassifier('haarcascade_frontalface_default.xml')
webcam = cv2.VideoCapture(0)
webcam = cv2.VideoCapture(0)
webcam.set(100, 600)
while True:
    successfull_frame, frame = webcam.read()
    cv2.imshow("video", frame)
    gray_img = cv2.cvtColor(frame, cv2.COLOR_BGR2GRAY)
    face_coordinates = trained_face_data.detectMultiScale(gray_img)
    for(x,y,width,height) in face_coordinates:
        cv2.rectangle(frame,(x,y), (x+width, y+height),randrange(0,255),2)
    cv2.imshow("video", frame)
    k = cv2.waitKey(1)
    if k == ord('q'):
        break
print('code complete')
