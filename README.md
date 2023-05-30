# Manually-Making-your-Panaroma-in-python
Stitching two images together in python - only focuses on calculating homography.

This project explores homgraphy and uses that to create image mosaics i.e., a panaroma.


## Installation

To be able to run this python script, you would need to install few libraries - numpy and matplotlib.

If you use conda, I prefer using environments.
After activating your environment, simply run this command:

```bash
  conda install numpy
```
```bash
  conda install matplotlib
```
And if you use pip instead, just run this command instead:
```bash
  pip install numpy
```
```bash
  pip install matplotlib
```
## Few Notes on Homography

It's a mathematical transformation that maps points from one image plane to another image plane.The mathematical transformation can be represented by a 3x3 matrix known as the homography matrix. It takes you from one image plane to another image lane but through a point of projection.For example, if you share the same center of projection and you take multiple images, you can map all the images to a single plane by simply computing the homographies between the images.Which is why it is very useful in image stitching. 

How do we compute it? 

1) Lets say, you have two images - you first apply a sift detector to these two images.
2) Then, you get the matching pairs from the images which are matrix A - which is our known matrix.
3) Then we take A^t A  - A^t is the transpose of A - and you find the eigenvalues and the eigenvectors of that matrix.
4) Our homography H, is simply the eigenvector which gives us the smallest eigenvalue of that matrix A.
5) Leastly, you can rearrange the elements of H to get the homography. 




## Links I found helpful

For Homography:

https://www.youtube.com/watch?v=l_qjO4cM74o

https://towardsdatascience.com/understanding-homography-a-k-a-perspective-transformation-cacaed5ca17

## For coordinates
I used gimp to get the image coordinates. You can also use automatic feature detection using Harris Corners etc. You need a minimum of 4 points and the points you select should preferably be corners i.e.., where the edges intersect. It's because corners are easy to locate on other images too with higher accuracy.




