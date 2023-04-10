# Image-Transformation
## Aim
To perform image transformation such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping using OpenCV and Python.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
Import the required libraries.

### Step2:
Read the image and convert the image from RGB to BGR.

### Step3:
Perform the following Image translations
1. Image Translation
2. Image Scaling
3. Image Shearing
4. Image Reflection
5. Image Rotation
6. Image Cropping 

## Program:
```
Developed By: Y SHAVEDHA
Register Number: 212221230095
```

i)Image Translation
```
#Translation 
image = cv2.imread('img.jpg')
#convert BGR TO RGB
image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
# Disable x and y axis
plt.axis('off')
#show the image
plt.imshow(image)
plt.show()
#get the image shape
rows,cols,dim = image.shape
#Transformation matrix for translation
M = np.float32([[1,0,60],
               [0,1,80],
               [0,0,1]])
# Apply a perspective transformation to the image
translated_image = cv2.warpPerspective(image,M,(cols,rows))

#Disable x,y axis
plt.axis('off')
#show the resulting image
plt.imshow(translated_image)
plt.show()
```

ii) Image Scaling
```
#Scaling the image
plt.axis('off')
#show the original image
plt.imshow(image)
plt.show()
M = np.float32([[1.5,0,0],
               [0,1.8,0],
               [0,0,1]])
scaled_image = cv2.warpPerspective(image,M,(cols*2,rows*2))
plt.axis('off')
plt.imshow(scaled_image)
plt.show()
```
iii)Image shearing
```
# Shearing 
#shearing applied to x axis
M_x = np.float32([[1,0.5,0],
                 [0,1,0],
                [0,0,1]])
#Shearing applied to y-axis
M_y = np.float32([[1,0,0],
                 [0.5,1,0],
                 [0,0,1]])
sheared_img_xaxis = cv2.warpPerspective(image,M_x,(int(cols*1.5),int(rows*1.5)))
sheared_img_yaxis = cv2.warpPerspective(image,M_y,(int(cols*1.5),int(rows*1.5)))
plt.axis('off')
plt.imshow(sheared_img_xaxis)
plt.show()
plt.axis('off')
plt.imshow(sheared_img_yaxis)
plt.show()
```

iv)Image Reflection
```
#Reflection
#Transformation matrix for x_axis
M_x = np.float32([[1,0,0],
                 [0,-1,rows],
                 [0,0,1]])
#Transformation matrix for y_axis
M_y = np.float32([[-1,0,cols],
                 [0,1,0],
                 [0,0,1]])
ref_xaxis = cv2.warpPerspective(image,M_x,(int(cols),int(rows)))
ref_yaxis = cv2.warpPerspective(image,M_y,(int(cols),int(rows)))
plt.axis('off')
plt.imshow(ref_xaxis)
plt.show()
plt.axis('off')
plt.imshow(ref_yaxis)
plt.show()
```
v)Image Rotation
```
#Rotation
#Angle from degree to radian
angle = np.radians(10)
#Transform matrix for rotation
M = np.float32([[np.cos(angle),-(np.sin(angle)),0],
               [np.sin(angle),np.cos(angle),0],
               [0,0,1]])
rotated_img = cv2.warpPerspective(image,M,(int(cols),int(rows)))
plt.axis('off')
plt.imshow(rotated_img)
plt.show()
```
vi)Image Cropping
```
#cropping
#get 200 pixels from 100 to 300 on both x and y axis
cropped_img = image[100:300,100:300]
plt.axis('off')
plt.imshow(cropped_img)
plt.show()
```
## Output:
### i)Image Translation
<img width="361" alt="image" src="https://user-images.githubusercontent.com/93427376/230819368-8a2465e4-d035-4987-a030-8a14e0a3cb2f.png">

### ii) Image Scaling
<img width="437" alt="image" src="https://user-images.githubusercontent.com/93427376/230819422-d4cd1b33-eb86-4dc7-b143-7e752c6b2884.png">

### iii)Image shearing
<img width="324" alt="image" src="https://user-images.githubusercontent.com/93427376/230819471-9fa37916-32ff-49cd-8bae-ac6ee490cdd8.png">

### iv)Image Reflection
<img width="386" alt="image" src="https://user-images.githubusercontent.com/93427376/230819511-71a67778-9c89-40b4-a6a9-12f4efac4e5d.png">

### v)Image Rotation
<img width="356" alt="image" src="https://user-images.githubusercontent.com/93427376/230819582-80f8fd29-2535-4216-9765-548d48ab61ff.png">

### vi)Image Cropping
<img width="308" alt="image" src="https://user-images.githubusercontent.com/93427376/230819696-ebd7fabf-e77a-4316-be6b-aff0650681da.png">

## Result: 
Thus the different image transformations such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping are done using OpenCV and python programming.
