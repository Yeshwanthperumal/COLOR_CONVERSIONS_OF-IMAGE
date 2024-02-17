# COLOR_CONVERSIONS_OF-IMAGE
## AIM
To write a python program using OpenCV to do the following image manipulations.

i) Read, display, and write an image.

ii) Access the rows and columns in an image.

iii) Cut and paste a small portion of the image.

iv)To perform the color conversion between RGB, BGR, HSV, and YCbCr color models.


## Software Required:
Anaconda - Python 3.7
## Algorithm:
### Step1:
Choose an image and save it as a filename.jpg ,
### Step2:
Use imread(filename, flags) to read the file.
### Step3:
Use imshow(window_name, image) to display the image.
### Step4:
Use imwrite(filename, image) to write the image.
### Step5:
End the program and close the output image windows.
### Step6:
Convert BGR and RGB to HSV and GRAY
### Step7:
Convert HSV to RGB and BGR
### Step8:
Convert RGB and BGR to YCrCb
### Step9:
Split and Merge RGB Image
### Step10:
Split and merge HSV Image

##### Program:
### Developed By: YESHWANTH P
### Register Number: 212222230178


## Output:

### i) Read and display the image
```
import cv2
import matplotlib.pyplot as plt

img=cv2.imread("image.jpg",1)
cv2.imshow("display window",img)
cv2.waitKey(0)
cv2.destroyAllWindows()
print(img.shape)
```
### OUTPUT
![Screenshot 2024-02-17 124610](https://github.com/Yeshwanthperumal/COLOR_CONVERSIONS_OF-IMAGE/assets/119476088/17fa859d-83b9-4f22-9c37-da9a54bbc2ed)

### ii)Write the image
```
img1=cv2.imread("image.jpg",0)
cv2.imshow("display window",img1)
cv2.waitKey(0)
cv2.destroyAllWindows()
cv2.imwrite('greyscale.jpg',img1)
```
### OUTPUT
![Screenshot 2024-02-17 124725](https://github.com/Yeshwanthperumal/COLOR_CONVERSIONS_OF-IMAGE/assets/119476088/eb5eb208-98d0-4c94-a1e8-03f39ff64f1e)

### iii)Shape of the Image
```
 import cv2
img1=cv2.imread("image.jpg",1)
print(img1.shape)
```
### OUTPUT
![Screenshot 2024-02-17 125701](https://github.com/Yeshwanthperumal/COLOR_CONVERSIONS_OF-IMAGE/assets/119476088/f7d83c51-9c1d-41d6-98f2-0bf019340a17)

### iv)Access rows and columns
```
import random
import cv2
image=cv2.imread('image.jpg',1)
#image=cv2.resize(image,(400,400))
for i in range (150,200):
    for j in range(image.shape[1]):
        image[i][j]=[random.randint(0,255),
                    random.randint(0,255),
                    random.randint(0,255)] 
cv2.imshow('part image',image)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
### OUTPUT
![Screenshot 2024-02-17 125953](https://github.com/Yeshwanthperumal/COLOR_CONVERSIONS_OF-IMAGE/assets/119476088/cb52e094-a86c-48ae-986f-e9b41bad42e8)

### v)Cut and paste portion of image
```
import cv2
img2 = cv2.imread("image.jpg")
x = 0
y = 200
x1 = 160
y1 = 450
x2 = 0
y2 = 0
cropimg = img2[x:x1+x2, y:y1+y2]
cv2.imshow("Original Image", img2)
cv2.imshow("Cropped Image", cropimg)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
#### OUTPUT
![Screenshot 2024-02-17 130636](https://github.com/Yeshwanthperumal/COLOR_CONVERSIONS_OF-IMAGE/assets/119476088/76147a81-31db-40d8-b563-8129920117ed)

### vi) BGR and RGB to HSV and GRAY
```
import cv2
img = cv2.imread('image.jpg',1)
img = cv2.resize(img,(300,200))
cv2.imshow('Original Image',img)
hsv1 = cv2.cvtColor(img,cv2.COLOR_BGR2HSV)
cv2.imshow('BGR2HSV',hsv1)
hsv2 = cv2.cvtColor(img,cv2.COLOR_RGB2HSV)
cv2.imshow('RGB2HSV',hsv2)
gray1 = cv2.cvtColor(img,cv2.COLOR_BGR2GRAY)
cv2.imshow('BGR2GRAY',gray1)
gray2 = cv2.cvtColor(img,cv2.COLOR_RGB2GRAY)
cv2.imshow('RGB2GRAY',gray2)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
### OUTPUT
![Screenshot 2024-02-17 132245](https://github.com/Yeshwanthperumal/COLOR_CONVERSIONS_OF-IMAGE/assets/119476088/e9da333b-aa72-4c6d-a75b-a472045c6f00)

### vii) HSV to RGB and BGR
```
import cv2
img = cv2.imread('image.jpg')
img = cv2.resize(img,(300,200))
img = cv2.cvtColor(img,cv2.COLOR_BGR2HSV)
cv2.imshow('Original HSV Image',img)
RGB = cv2.cvtColor(img,cv2.COLOR_HSV2RGB)
cv2.imshow('2HSV2BGR',RGB)
BGR = cv2.cvtColor(img,cv2.COLOR_HSV2BGR)
cv2.imshow('HSV2RGB',BGR)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
### OUTPUT
![Screenshot 2024-02-17 132519](https://github.com/Yeshwanthperumal/COLOR_CONVERSIONS_OF-IMAGE/assets/119476088/978191db-8644-49ef-b97c-bef12004fd69)

### viii) RGB and BGR to YCrCb
```
import cv2
img = cv2.imread('image.jpg')
img = cv2.resize(img,(300,200))
cv2.imshow('Original RGB Image',img)
YCrCb1 = cv2.cvtColor(img, cv2.COLOR_BGR2YCrCb)
cv2.imshow('RGB-2-YCrCb',YCrCb1)
YCrCb2 = cv2.cvtColor(img, cv2.COLOR_RGB2YCrCb)
cv2.imshow('BGR-2-YCrCb',YCrCb2)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
### OUTPUT
![Screenshot 2024-02-17 132633](https://github.com/Yeshwanthperumal/COLOR_CONVERSIONS_OF-IMAGE/assets/119476088/4fad6811-3fac-4363-83b5-8ded777e8c52)

### ix) Split and merge RGB Image
```
import cv2
img = cv2.imread('image.jpg',1)
img = cv2.resize(img,(300,200))
R = img[:,:,2]
G = img[:,:,1]
B = img[:,:,0]
cv2.imshow('R-Channel',R)
cv2.imshow('G-Channel',G)
cv2.imshow('B-Channel',B)
merged = cv2.merge((B,G,R))
cv2.imshow('Merged RGB image',merged)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
### OUPUT
![Screenshot 2024-02-17 132812](https://github.com/Yeshwanthperumal/COLOR_CONVERSIONS_OF-IMAGE/assets/119476088/0cf803cb-715c-4775-8c06-67b36f5b0986)

### x) Split and merge HSV Image
```
import cv2
img = cv2.imread("image.jpg",1)
img = cv2.resize(img,(300,200))
img=cv2.cvtColor(img,cv2.COLOR_RGB2HSV)
H,S,V=cv2.split(img)
cv2.imshow('Hue',H)
cv2.imshow('Saturation',S)
cv2.imshow('Value',V)
merged = cv2.merge((H,S,V))
cv2.imshow('Merged',merged)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
### OUTPUT
![Screenshot 2024-02-17 132957](https://github.com/Yeshwanthperumal/COLOR_CONVERSIONS_OF-IMAGE/assets/119476088/9ee0f979-fc13-401d-bb20-869d2dc4d3f4)

## Result:
Thus the images are read, displayed, and written ,and color conversion was performed between RGB, HSV and YCbCr color models successfully using the python program.







