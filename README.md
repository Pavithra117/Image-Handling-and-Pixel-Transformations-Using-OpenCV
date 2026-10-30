## Image-Handling-and-Pixel-Transformations-Using-OpenCV

## NAME : Pavithra K
## REG.NO : 212224240112

## AIM:

Write a Python program using OpenCV that performs the following tasks:

Read and display an image.

Adjust the brightness of an image.

Modify the image contrast.

Generate a third image using bitwise operations.

## Software Required:

Anaconda - Python

Jupyter Notebook (for interactive development and execution)

OpenCV

NumPy

## Algorithm:
Step 1:
Load an image from your local directory and display it.

Step 2:
Create a matrix of ones (with data type float64) to adjust brightness.

Step 3:
Create brighter and darker images by adding and subtracting the matrix from the original image. Display the original, brighter, and darker images.

Step 4:
Modify the image contrast by creating two higher contrast images using scaling factors of 1.1 and 1.2 (without overflow fix). Display the original, lower contrast, and higher contrast images.

Step 5:
Split the image (photo.p.jpeg) into B, G, R components and display the channels.

## Program:
```
import cv2
import matplotlib.pyplot as plt
# Read the image using OpenCV
img = cv2.imread('pavithra image.png', cv2.IMREAD_COLOR)
# Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
# Display the image using Matplotlib
plt.imshow(img_rgb, cmap='viridis')  # You can change 'viridis' to another cmap or use None for RGB images
plt.title("Original Image")
plt.axis('off')  # Removes axis ticks and labels
plt.show()

# 1.Draw a line from the top-left to the bottom-right of the image
# Load the image
image = cv2.imread('pavithra image.png')
# Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
img_rgb.shape
# Draw a line from top-left to bottom-right
line_img = cv2.line(img_rgb, (0, 0), (768, 600), (255, 0, 0), 2) # cv2.line(image, start_point, end_point, color, thickness)
plt.imshow(line_img, cmap='viridis')  
plt.title("Image with Line")
plt.axis('off')  
plt.show()

# 2.Draw a circle at the center of the image.
# Load the image
image = cv2.imread('pavithra image.png') 

# Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
img_rgb.shape
circle_img = cv2.circle(img_rgb,(400,300),150,(255,255,0),10) # cv2.circle(image, center, radius, color, thickness)
plt.imshow(circle_img, cmap='viridis')  
plt.title("Image with Circle")
plt.axis('off')  
plt.show()

# 3.Draw a rectangle around  the whole image
# Load the image
image = cv2.imread('pavithra image.png') 

# Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
img.shape
# Draw a rectangle around the Whole image
rectangle_img = cv2.rectangle(img_rgb, (0, 0), (768, 600), (0, 255, 255), 10)  # cv2.rectangle(image, start_point, end_point, color, thickness)
plt.imshow(rectangle_img, cmap='viridis')  
plt.title("Image with Rectangle")
plt.axis('off')  
plt.show()

# 4.Add the text "OpenCV Drawing" at the top-left corner of the image.
# Load the image
image = cv2.imread('pavithra image.png')
# Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
# Add text to the image
text_img = cv2.putText(img_rgb, "OpenCV Drawing", (50,100), cv2.FONT_HERSHEY_SIMPLEX, 3, (0, 255, 255), 10)  ## cv2.putText(image, text, position, font, font_scale, color, thickness)
plt.imshow(text_img, cmap='viridis')  
plt.title("IMAGE WITH TEXT")
plt.axis('off')  
plt.show()

# 5.Convert the image from RGB to HSV,GRAY,YCrCb,RGB
# Load the image
image = cv2.imread('pavithra image.png')
image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)
# Original RGB Image
plt.imshow(image_rgb)
plt.title("Original RGB Image")
plt.axis("off")
# Convert RGB to HSV
image_hsv = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2HSV)
# HSV Image') 

plt.imshow(image_hsv)
plt.title("HSV Image")
plt.axis("off")
# Convert RGB to GRAY
image_gray = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2GRAY)
# Grayscale Image
plt.imshow(image_gray, cmap='gray')
plt.title("Grayscale Image")
plt.axis("off")
# Convert RGB to YCrCb
image_ycrcb = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2YCrCb)
# YCrCb Image
plt.imshow(image_ycrcb)
plt.title("YCrCb Image")
plt.axis("off")
# Convert HSV back to RGB
image_hsv_to_rgb = cv2.cvtColor(image_hsv, cv2.COLOR_HSV2RGB)
plt.imshow(image_hsv_to_rgb)
plt.title("HSV to RGB Image")
plt.axis("off")

# Modify a block of pixels (300x300) to white, starting from (200, 200)
image[200:500, 200:500] = [255, 0, 255]  # Rows: 200-499, Columns: 200-499
# Convert BGR to RGB for displaying with Matplotlib
image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)
# Display the modified image
plt.imshow(image_rgb)
plt.title("Image with 300x300 White Block")
plt.axis("off")
plt.show()

#  6.Resize the original image to half its size and display it.
# Load the image
image = cv2.imread('pavithra image.png')
image.shape
# Resize the image to half its size
resized_image = cv2.resize(image, (768 // 2, 600 // 2))  # (new_width, new_height)
# Convert BGR to RGB for displaying with Matplotlib
resized_image_rgb = cv2.cvtColor(resized_image, cv2.COLOR_BGR2RGB)
resized_image_rgb.shape
# Display the resized image
plt.imshow(resized_image_rgb)
plt.title("Resized Image (Half Size)")
plt.axis("off")
plt.show()
# Load the image
image = cv2.imread('pavithra image.png')
image.shape
# Crop a 300x300 region starting from (50, 50)
roi = image[50:350, 50:350]  # Rows: 50-349, Columns: 50-349
# Convert BGR to RGB for displaying with Matplotlib
roi_rgb = cv2.cvtColor(roi, cv2.COLOR_BGR2RGB)
# Display the cropped region (ROI)
plt.imshow(roi_rgb)
plt.title("Cropped Region of Interest (ROI)")
plt.axis("off")
plt.show()

# 7.Flip the original image horizontal,vertical and display it.
# Load the image
image = cv2.imread('pavithra image.png')
# Flip the image horizontally (left-right)
flipped_horizontally = cv2.flip(image, 1)
# Convert BGR to RGB for displaying with Matplotlib
flipped_horizontally_rgb = cv2.cvtColor(flipped_horizontally, cv2.COLOR_BGR2RGB)
# Horizontal flip
plt.imshow(flipped_horizontally_rgb)
plt.title("Flipped Horizontally")
plt.axis("off")
# Flip the image vertically (up-down)
flipped_vertically = cv2.flip(image, 0)
# Convert BGR to RGB for displaying with Matplotlib
flipped_vertically_rgb = cv2.cvtColor(flipped_vertically, cv2.COLOR_BGR2RGB)
# Vertical flip
plt.imshow(flipped_vertically_rgb)
plt.title("Flipped Vertically")
plt.axis("off")
```

## Output:

<img width="482" height="474" alt="image" src="https://github.com/user-attachments/assets/f07da3bc-039b-4aef-a9f0-6969b0be814f" />

<img width="487" height="477" alt="image" src="https://github.com/user-attachments/assets/8a2e96ea-b660-4125-ab2b-f33c8fe2dad4" />

<img width="459" height="472" alt="image" src="https://github.com/user-attachments/assets/4b0dec9b-f359-4a5c-97e9-bff427e17d05" />

<img width="459" height="477" alt="image" src="https://github.com/user-attachments/assets/23aa1294-dbb6-43fe-a1b0-7b56a18f0a44" />

<img width="437" height="478" alt="image" src="https://github.com/user-attachments/assets/023c9420-e4b7-4fca-b993-7ac1193e539a" />

<img width="651" height="498" alt="image" src="https://github.com/user-attachments/assets/568aab3c-d8f0-4d22-bf3d-b1868de675b5" />

<img width="686" height="507" alt="image" src="https://github.com/user-attachments/assets/7c4d3fa7-2de5-4388-a5a7-9348df8207f7" />

<img width="459" height="463" alt="image" src="https://github.com/user-attachments/assets/1381a845-bdcb-4270-86be-7100ef239703" />

<img width="486" height="469" alt="image" src="https://github.com/user-attachments/assets/de99e8df-580d-4a37-9ced-449d8ba5c859" />

<img width="471" height="478" alt="image" src="https://github.com/user-attachments/assets/8195445b-9264-4abd-a4cc-9ee659fe5ec2" />

<img width="453" height="477" alt="image" src="https://github.com/user-attachments/assets/e9ba1fe8-f2e2-4bed-b070-1a271c95ae36" />

<img width="597" height="468" alt="image" src="https://github.com/user-attachments/assets/fcc4c9ba-1809-46a8-bca6-4741c060f959" />

<img width="478" height="484" alt="image" src="https://github.com/user-attachments/assets/b26edf02-bf6f-4281-9616-04b8b8c4533d" />

<img width="440" height="469" alt="image" src="https://github.com/user-attachments/assets/f5e9db7c-7eaf-49a4-bad3-74bd624b11e7" />

<img width="469" height="480" alt="image" src="https://github.com/user-attachments/assets/8cd5da93-1dc9-42a8-959a-417a13732c7f" />


## Result:

Thus, the images were read, displayed, brightness and contrast adjustments were made, and bitwise operations were performed successfully using the Python program.











