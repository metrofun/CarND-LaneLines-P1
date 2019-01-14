# **Finding Lane Lines on the Road** 

## Writeup Template

### You can use this file as a template for your writeup if you want to submit it as a markdown file. But feel free to use some other method and submit a pdf if you prefer.

---

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report


[//]: # (Image References)

[image1]: ./examples/grayscale.jpg "Grayscale"

---

### Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline consisted of 6 steps: make grayscale, canny lines detector, gaussian blurring, taking haugh transform, clustering in haugh space, drawing clustered lines

In order to draw a single line on the left and right lanes, I clustered hough lines using GMM without normalization into 3 clusters, two for lines and one more for noise. Since Gaussians are very sensitive to noise. Then I picked clustered means with good slope and draw them.


### 2. Identify potential shortcomings with your current pipeline

Field of view is hardcoded, lines can't band, lines are noisy, works only under similar weather conditions

### 3. Suggest possible improvements to your pipeline

More tuning would help, but bettwe way would be to use some kind of spatio-temporeral 3D CNNs 
