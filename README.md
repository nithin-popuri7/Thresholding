# Thresholding of Images
## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm

### Step1:
Load the image and convert the image to Grayscale.



### Step2:
Smoothen the image using Gaussian Method.




### Step3:
Apply thresholding cv2.THRESH_BINARY on the image.



### Step4:
Apply thresholding cv2.THRESH_BINARY_INC on the image.




### Step5:
Apply thresholding cv2.THRESH_TRUNC on the image.



### Step6:
Apply thresholding cv2.THRESH_TOZERO on the image.



### Step7:
Apply thresholding cv2.THRESH_TOZERO_INC on the image.





## Program

```python
Developed By:P.Siva Naga Nithin
Reg.No:212221240037
import cv2
import matplotlib.pyplot as plt
image = cv2.imread("jerry.jpeg")

# Read the Image and convert to grayscale

grayImage = cv2.cvtColor(image,cv2.COLOR_BGR2GRAY)

# Use Global thresholding to segment the image

ret,thresh = cv2.threshold(grayImage,100,200,cv2.THRESH_BINARY)
ret1,thresh1 = cv2.threshold(grayImage,100,200,cv2.THRESH_BINARY_INV)
ret2, thresh2 = cv2.threshold(grayImage,100,200,cv2.THRESH_TRUNC)
ret3, thresh3 = cv2.threshold(grayImage,100,200,cv2.THRESH_TOZERO)
ret4, thresh4 = cv2.threshold(grayImage,100,200,cv2.THRESH_TOZERO_INV)

# Use Adaptive thresholding to segment the image

th1 = cv2.adaptiveThreshold(grayImage,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
th2 = cv2.adaptiveThreshold(grayImage,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)
titles = ["Original Image","Adaptive Mean Thresholding","Adaptive Gaussian Thresholding"]
imgs = [grayImage,th1,th2]

# Use Otsu's method to segment the image 
ret5,th3 = cv2.threshold(grayImage,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)

# Display the results

cv2.imshow("Original Image",image)
cv2.imshow("Gray Image",grayImage)
cv2.imshow("THRESH_BINARY",thresh)
cv2.imshow("THRESH_BINARY_INV",thresh1)
cv2.imshow("THRESH_TRUNC",thresh2)
cv2.imshow("THRESH_TOZERO",thresh3)
cv2.imshow("THRESH_TOZERO_INV",thresh4)

for i in range(3):
    plt.subplot(3,1,i+1)
    plt.imshow(imgs[i],'gray')
    plt.title(titles[i])
    plt.xticks([]),plt.yticks([])
plt.show()


cv2.imshow("Otsu method",th3)
cv2.waitKey(0)








```
## Output

### Original Image
<br>![dip2](https://user-images.githubusercontent.com/94154780/169657591-3acc6f32-d761-43c6-b4f7-5ef08af697e7.png)
<br>[dip3](https://user-images.githubusercontent.com/94154780/169658123-bc01f063-3234-4ece-8390-5320d772a3e9.png)<br>



### Global Thresholding
<br>![dip4](https://user-images.githubusercontent.com/94154780/169658023-a974fbf8-e6d9-44cd-9bb3-d23b843dd104.png)<br>
<br>![dip5](https://user-images.githubusercontent.com/94154780/169658042-aa27dfe4-20c3-43ba-a751-6c89badb044c.png)<br>
<br>![dip6](https://user-images.githubusercontent.com/94154780/169658065-1808988e-da91-429c-9148-e87b13bfc086.png)<br>


### Adaptive Thresholding
![dip1](https://user-images.githubusercontent.com/94154780/169657657-4e58be00-3e70-4039-a25c-d02567ba7bcb.png)

### Optimum Global Thesholding 
![dip9](https://user-images.githubusercontent.com/94154780/169658182-3fde12e2-bb1d-4000-88f6-683c871197f2.png)


## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.

