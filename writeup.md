#**Finding Lane Lines on the Road** 

The goal of the project is to create an image processing pipeline to identify lane lines on a road. To start with , we will identify white and yellow lane lines in a series of image. Then we will expand it to identify lane lines in a video (a collection of images). We will then reflect on the work on a short writeup.


[//]: # (Image References)

[image1]: ./examples/grayscale.jpg "Grayscale"

---

###1. Description of the pipeline. 

The pipeline consisted of 4 steps. 
First, we blur the image with gaussian_blur
Then we apply Canny edge detection to detect the sharp changes of colors in the blurred image. We tune the low and high threshold parameters of canny
```low_threshold = 200
   high_threshold = 300
   edges = canny(blur_gray, low_threshold, high_threshold)
```    




###2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be what would happen when ... 

Another shortcoming could be ...


###3. Suggest possible improvements to your pipeline

A possible improvement would be to ...

Another potential improvement could be to ...
