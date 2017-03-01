#**Finding Lane Lines on the Road** 

The goal of the project is to create an image processing pipeline to identify lane lines on a road. To start with , we will identify white and yellow lane lines in a series of image. Then we will expand it to identify lane lines in a video (a collection of images). We will then reflect on the work on a short writeup.


[//]: # (Image References)

[image1]: ./examples/grayscale.jpg "Grayscale"

---

###1. Description of the pipeline. 

The pipeline consisted of 4 steps. 

First, we blur the image with gaussian_blur.

Then we apply Canny edge detection to detect the sharp changes of colors in the blurred image. We tune the low and high threshold parameters of canny
```
low_threshold = 200
high_threshold = 300
edges = canny(blur_gray, low_threshold, high_threshold)
```    
Then we crop out the area of interest 

```
x = edges.shape[0]
y = edges.shape[1]
vertices = np.array( [[[3*x/4, 3*y/5],[x/4, 3*y/5],[40, y],[x - 40, y]]], dtype=np.int32 )
masked_edges = region_of_interest(edges, vertices)
```
Then we apply the hough line detection logic. We tune the parameters for hough line detection

```
rho = 3
theta = np.pi/180
threshold = 40
min_line_length = 30
max_line_gap = 200
```
Then we draw lines on the lane lines of the original image

```
result = weighted_img(line_img, image)
fig = plt.figure(figsize=(6,10))
```



###2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be what would happen when ... 

Another shortcoming could be ...


###3. Suggest possible improvements to your pipeline

A possible improvement would be to ...

Another potential improvement could be to ...
