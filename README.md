# Assignment-on-DL
import cv2 as cv
import numpy as np
import matplotlib.pyplot as plt

img=cv.imread('/berry-1.jpg',cv.IMREAD_GRAYSCALE)

ret,th1=cv.threshold(img,60,255,cv.THRESH_BINARY)
th2 =cv.adaptiveThreshold(img,255,cv.ADAPTIVE_THRESH_MEAN_C,cv.THRESH_BINARY,11, 2)
th3=cv.adaptiveThreshold(img,255,cv.ADAPTIVE_THRESH_GAUSSIAN_C,cv.THRESH_BINARY,11, 2)

titles=['Original Image','Global Thresholding(v=127)','Adaptive Mean Thresholding','Adaptive Gaussian Thresholding']
images=[img,th1,th2,th3]

for i in range(4):
  plt.subplot(2,2,i+1),plt.imshow(images[i],'gray')
  plt.title(titles[i])
  plt.xticks([]),plt.yticks([])
plt.show()


#Number 2
import cv2
import numpy as np
from matplotlib import pyplot as plt

img = cv2.imread('/berry-1.jpg', cv2.IMREAD_GRAYSCALE)
ret1, th1 =cv2.threshold(img,60,255,cv2.THRESH_BINARY)
ret2,th2 =cv2.threshold(img,60,255,cv2.THRESH_BINARY_INV + cv2.THRESH_OTSU)

th4 = cv2.adaptiveThreshold(img,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)

titles =['Original Image', 'Global Thresholding (v=60)','Otsus Thresholding','Adaptive Thresholding']
images = [img,th1,th2,th4]
for i in range (4):
  plt.subplot(2,2,i+1)
  plt.imshow(images[i], 'gray')
  plt.title(titles[i])
  plt.xticks([]),plt.yticks([])
plt.show()
