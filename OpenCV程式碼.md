ch3-04
=


2draw.py
-
```
import cv2 
import numpy as np

gc = np.zeros((512, 512, 3), dtype=np.uint8)
gc.fill(255)

#cv2.line(gc, (10, 50), (400, 300), (255, 0, 0), 5)
# cv2.rectangle(gc, (30, 50), (200, 280), (0, 0, 255), 5)
# cv2.rectangle(gc, (100, 200), (196, 276), (234, 151, 102), -1)
# cv2.circle(gc, (200, 100), 80, (255, 255, 0), -1)
# cv2.circle(gc, (280, 180), 60, (147, 113, 217), 3)
# cv2.ellipse(gc, (200, 100), (80, 40), 45, 0, 360, (80, 127, 255), 5)
# cv2.ellipse(gc, (250, 200), (70, 70), 0, 0, 135, (44, 141, 108), -1)

#設定頂點座標
# pts = np.array(((10,5), (100,100), (170,120), (200,50)))
#True:頭尾相連; False:頭尾不相連
# cv2.polylines(gc, [pts], True, (105, 105, 105), 2)

font = cv2.FONT_HERSHEY_SIMPLEX
cv2.putText(gc, 'OpenCV', (10,200), font, 4, (0,0,0), 2, cv2.LINE_AA)

cv2.imshow('draw', gc) 
cv2.waitKey(0)
cv2.destroyAllWindows()
```

font.py
-
```
import numpy as np
import cv2

#建立 512x512 的黑色畫布
gc = np.zeros((512, 512, 3), np.uint8)
#用(B, G, R) = (255, 255, 255): 白色填滿畫布
gc.fill(255)

font = [
    cv2.FONT_HERSHEY_SIMPLEX,
    cv2.FONT_HERSHEY_PLAIN,
    cv2.FONT_HERSHEY_DUPLEX,
    cv2.FONT_HERSHEY_COMPLEX,
    cv2.FONT_HERSHEY_TRIPLEX,
    cv2.FONT_HERSHEY_COMPLEX_SMALL,
    cv2.FONT_HERSHEY_SCRIPT_SIMPLEX,
    cv2.FONT_HERSHEY_SCRIPT_COMPLEX
]

y = 50
for f in font:
    cv2.putText(gc, 'OpenCV', (10,y), f, 2, (0,0,0), 2, cv2.LINE_AA)
    y += 60

cv2.imshow("draw", gc)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
***

1capture.py
-
```
import cv2
ESC = 27
# 畫面數量計數
n = 1
# 存檔檔名用
index = 0
# 人臉取樣總數
total = 100

def saveImage(face_image, index):
    filename = 'images/h0/{:02d}.pgm'.format(index)
    cv2.imwrite(filename, face_image)
    print(filename)

face_cascade = cv2.CascadeClassifier('haarcascade_frontalface_default.xml')
cap = cv2.VideoCapture(0)
cv2.namedWindow('video', cv2.WINDOW_NORMAL)

while n > 0:
    ret, frame = cap.read()
    # frame = cv2.resize(frame, (600, 336))
    frame = cv2.flip(frame, 1)
    gray = cv2.cvtColor(frame, cv2.COLOR_BGR2GRAY)

#### 在while內
    faces = face_cascade.detectMultiScale(gray, 1.1, 3)
    for (x, y, w, h) in faces:
        frame = cv2.rectangle(frame, (x, y), (x + w, y + h), (0, 255, 0), 3)
        if n % 5 == 0:
            face_image = cv2.resize(gray[y: y + h, x: x + w], (400, 400))
            saveImage(face_image, index)
            index += 1
            if index >= total:
                print('get training data done')
                n = -1
                break
        n += 1

#### 在while內
    cv2.imshow('video', frame)
    if cv2.waitKey(1) == 27:
        cv2.destroyAllWindows()
        break
```
***

2train.py
-
```
import cv2
import numpy as np

images = []
labels = []
for index in range(100):
    filename = 'images/h0/{:02d}.pgm'.format(index)
    print('read ' + filename)
    img = cv2.imread(filename, cv2.COLOR_BGR2GRAY)
    images.append(img)
    labels.append(0)    # 第一張人臉的標籤為0

print('training...')
model = cv2.face.LBPHFaceRecognizer_create()
model.train(np.asarray(images), np.asarray(labels))
model.save('faces.data')
print('training done')
```
***
3recognition.py
-
```
import cv2

model = cv2.face.LBPHFaceRecognizer_create()
model.read('faces.data')
print('load training data done')

face_cascade = cv2.CascadeClassifier('haarcascade_frontalface_default.xml')
cap = cv2.VideoCapture(0)
cv2.namedWindow('video', cv2.WINDOW_NORMAL)
# 可識別化名稱
names = ['ckk']

while True:
    ret, frame = cap.read()
    frame = cv2.resize(frame, (600, 336))
    frame = cv2.flip(frame, 1)
    gray = cv2.cvtColor(frame, cv2.COLOR_BGR2GRAY)

#### 在while內
    faces = face_cascade.detectMultiScale(gray, 1.1, 3)
    for (x, y, w, h) in faces:
        frame = cv2.rectangle(frame, (x, y), (x + w, y + h), (0, 255, 0), 3)
        face_image = cv2.resize(gray[y: y + h, x: x + w], (400, 400))
        try:
            val = model.predict(face_image)
            print('label:{}, confidence:{}'.format(val[0], val[1]))
            if val[1] < 50:
                cv2.putText(
                    frame, names[val[0]], 
                    (x, y - 10), 
                    cv2.FONT_HERSHEY_SIMPLEX, 1, 
                    (255,255,0), 3, cv2.LINE_AA
                )
        except:
            continue

#### 在while內
    cv2.imshow('video', frame)
    if cv2.waitKey(1) == 27:
        cv2.destroyAllWindows()
        break
```
***
