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
### Developed By: MAHESH RAJ PUROHIT J
### Register Number: 212222240058
```
<table>
  <tr>
    <td width=50%>

### i) Read and display the image
```Python
    import cv2
    image=cv2.imread('meow.jpg',1)
    image=cv2.resize(image,(400,300))
    cv2.imshow('MAHESH RAJ PUROHIT J',image)
    cv2.waitKey(0)
    cv2.destroyAllWindows()
``` 
  </td>
  <td>

### OUTPUT:
![Screenshot 2024-02-15 233532](https://github.com/maheshrajpurohit18/COLOR_CONVERSIONS_OF-IMAGE/assets/118749665/f7de57db-211e-4f6d-8ed0-b674e2bace4f)



  </td>
  </tr>

   <tr>
    <td width=50%>

### ii)Write the image
```Python
    import cv2
    image=cv2.imread('meow.jpg',0)
    cv2.imwrite('d.jpg',image)
```
  </td>
  <td>

### OUTPUT:
![Screenshot 2024-02-15 235014](https://github.com/maheshrajpurohit18/COLOR_CONVERSIONS_OF-IMAGE/assets/118749665/236ebbca-8ffa-4241-ba9e-86f6ab9dc552)




  </td>
  </tr>
  <tr>
    <td width=50%>

### iii)Shape of the Image
```Python
    import cv2
    image=cv2.imread('meow.jpg',1)
    print(image.shape)
```
  </td>
  <td>

### OUTPUT:
![Screenshot 2024-02-15 235043](https://github.com/maheshrajpurohit18/COLOR_CONVERSIONS_OF-IMAGE/assets/118749665/258d3f8b-3518-4c50-a11c-0291e06ec4a5)


  </td>
  </tr>
  <tr>
    <td>
      
### iv)Access rows and columns
```Python
    import random
    import cv2
    image=cv2.imread('meow.jpg',1)
    image=cv2.resize(image,(400,400))
    for i in range (150,200):
      for j in range(image.shape[1]):
          image[i][j]=[random.randint(0,255),
                       random.randint(0,255),
                       random.randint(0,255)] 
    cv2.imshow('part image',image)
    cv2.waitKey(0)
    cv2.destroyAllWindows()
```
  </td>
  <td width="50%">

### OUTPUT:
![Screenshot 2024-02-15 233645](https://github.com/maheshrajpurohit18/COLOR_CONVERSIONS_OF-IMAGE/assets/118749665/ebb2c5fb-c950-4216-b85a-e53c6fb20c26)



  </td>
  </tr>
  <tr>
    <td width=50%>
      
### v)Cut and paste portion of image

 ```Python
    import cv2
    image=cv2.imread('meow.jpg',1)
    image=cv2.resize(image,(400,400))
    tag =image[130:200,110:190]
    image[110:180,120:200] = tag
    cv2.imshow('partimage1',image)
    cv2.waitKey(0)
    cv2.destroyAllWindows()
```
  </td>
  <td>
    
### OUTPUT:
![Screenshot 2024-02-15 233708](https://github.com/maheshrajpurohit18/COLOR_CONVERSIONS_OF-IMAGE/assets/118749665/470701a8-8e42-4ce1-8368-d08ec7c575f4)


  </td>
  </tr>
</table>

### vi) BGR and RGB to HSV and GRAY
```Python
import cv2
img = cv2.imread('meow.jpg',1)
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

### OUTPUT:
![Screenshot 2024-02-15 233956](https://github.com/maheshrajpurohit18/COLOR_CONVERSIONS_OF-IMAGE/assets/118749665/79567396-cf31-4d59-a138-d199ff67be30)
![Screenshot 2024-02-15 233805](https://github.com/maheshrajpurohit18/COLOR_CONVERSIONS_OF-IMAGE/assets/118749665/5742a137-a89b-4272-a5be-9c294e5b25d0)
![Screenshot 2024-02-15 233858](https://github.com/maheshrajpurohit18/COLOR_CONVERSIONS_OF-IMAGE/assets/118749665/39eb631a-ed1d-4e46-89b1-60ce79c85642)
![Screenshot 2024-02-15 233918](https://github.com/maheshrajpurohit18/COLOR_CONVERSIONS_OF-IMAGE/assets/118749665/c639435a-b1d6-4c8e-ab41-127096963253)
![Screenshot 2024-02-15 233938](https://github.com/maheshrajpurohit18/COLOR_CONVERSIONS_OF-IMAGE/assets/118749665/efb192a4-590b-4483-8c5e-9c9f0e2f7456)



### vii) HSV to RGB and BGR
```Python
import cv2
img = cv2.imread('meow.jpg')
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

### OUTPUT:
![Screenshot 2024-02-15 234107](https://github.com/maheshrajpurohit18/COLOR_CONVERSIONS_OF-IMAGE/assets/118749665/e59876ae-4905-44ac-8604-61e7ddb2987c)
![Screenshot 2024-02-15 234138](https://github.com/maheshrajpurohit18/COLOR_CONVERSIONS_OF-IMAGE/assets/118749665/3abc1efd-f5a9-4ebb-b542-e48fb456e2b1)
![Screenshot 2024-02-15 234125](https://github.com/maheshrajpurohit18/COLOR_CONVERSIONS_OF-IMAGE/assets/118749665/944f5fb9-0638-441d-b33f-ba6878ac0e63)


### viii) RGB and BGR to YCrCb
```Python
import cv2
img = cv2.imread('meow.jpg')
img = cv2.resize(img,(300,200))
cv2.imshow('Original RGB Image',img)
YCrCb1 = cv2.cvtColor(img, cv2.COLOR_BGR2YCrCb)
cv2.imshow('RGB-2-YCrCb',YCrCb1)
YCrCb2 = cv2.cvtColor(img, cv2.COLOR_RGB2YCrCb)
cv2.imshow('BGR-2-YCrCb',YCrCb2)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

### OUTPUT:
![Screenshot 2024-02-15 234520](https://github.com/maheshrajpurohit18/COLOR_CONVERSIONS_OF-IMAGE/assets/118749665/6fa34974-e951-4b66-9c7b-e70e28b945ed)
![Screenshot 2024-02-15 234539](https://github.com/maheshrajpurohit18/COLOR_CONVERSIONS_OF-IMAGE/assets/118749665/cedffccf-df3d-4b48-be94-f0ecfd3eb5c5)
![Screenshot 2024-02-15 234554](https://github.com/maheshrajpurohit18/COLOR_CONVERSIONS_OF-IMAGE/assets/118749665/b617206a-7a87-47c3-a961-3d2f326f2ac6)



### ix) Split and merge RGB Image
```Python
import cv2
img = cv2.imread('meow.jpg',1)
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

### OUTPUT:
![Screenshot 2024-02-15 234657](https://github.com/maheshrajpurohit18/COLOR_CONVERSIONS_OF-IMAGE/assets/118749665/c1d45ea7-4c80-4a59-9ec5-ed9e6900dff3)
![Screenshot 2024-02-15 234714](https://github.com/maheshrajpurohit18/COLOR_CONVERSIONS_OF-IMAGE/assets/118749665/de80ecd5-ad17-4c0b-80fd-9b5e104899ee)
![Screenshot 2024-02-15 234725](https://github.com/maheshrajpurohit18/COLOR_CONVERSIONS_OF-IMAGE/assets/118749665/c7503818-1200-4120-ba56-d16838276704)
![Screenshot 2024-02-15 234734](https://github.com/maheshrajpurohit18/COLOR_CONVERSIONS_OF-IMAGE/assets/118749665/102089de-4ba4-4056-a9f2-3f6f18908ac9)




### x) Split and merge HSV Image
```Python
import cv2
img = cv2.imread("meow.jpg",1)
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

### OUTPUT:
![Screenshot 2024-02-15 234826](https://github.com/maheshrajpurohit18/COLOR_CONVERSIONS_OF-IMAGE/assets/118749665/50879ada-c054-4c18-8ea3-ad789de9d2ac)
![Screenshot 2024-02-15 234838](https://github.com/maheshrajpurohit18/COLOR_CONVERSIONS_OF-IMAGE/assets/118749665/c9998a3b-6d17-40e3-96df-e4c55f947448)
![Screenshot 2024-02-15 234852](https://github.com/maheshrajpurohit18/COLOR_CONVERSIONS_OF-IMAGE/assets/118749665/dae498f2-3240-4267-8946-019edae99954)
![Screenshot 2024-02-15 234923](https://github.com/maheshrajpurohit18/COLOR_CONVERSIONS_OF-IMAGE/assets/118749665/a2f6b25e-c238-4cfd-9fda-2e0ba731ab8e)





## Result:
Thus the images are read, displayed, and written ,and color conversion was performed between RGB, HSV and YCbCr color models successfully using the python program.







