## 6D-RGBD-Odometry

This package provides a novel  6D  RGB-D   odometry   approach   that   finds   the   relative   camera   pose between consecutive RGB-D frames by keypoint extraction and feature  matching  both  on  the  RGB  and  depth  image  planes.

To find the Rigid Motion between two camera frames, the VO algorithm follows these steps:

#####1) RGB-D Keypoint Extraction:

STAR Detector for RGB image and NARF detector for Depth Image.

#####2) RGB-D Feature Matching:

BRAND Description computation on keypoints and brute-force descriptor matcher with the Hamming norm and correspondence cross checking.

#####3) Correspondences Outlier Rejection:

Filter the matches using RANSAC outlier rejection algorithm  

#####4) 6D Rigid Motion Estimation:

Iterative estimation using RANSAC and Umeyama Method.

The output of this algorithm should be something similar to this video:




###brand_odometry

To run this example you will need to install PCL library (www.pointclouds.org), OpenCV (www.opencv.org) and compile the brand library in this folder, to do so,  (after succesfully installing PCL and OpenCV) you must follow these instructions:

```
cd ~/brand/
mkdir build && cd build
make
sudo make install
```
Once compiled you can test the BRAND desciptors by running a simple matching example found in:

###brand_match
This stand-alone example shows how to use the class to create BRAND descriptors.

Compiling:
```
cd ~/brand_match/
mkdir build && cd build
make
```
Run Code:
```
./6D-rgbd-odometry ...
```

#####References:


---


Compile Code:
```
cmake ..
```

Run Code:
```
./6D-rgbd-odometry ...
```

---
#####Reference:
Nadia Figueroa, Haiwei Dong, and Abdulmotaleb El Saddik. 2015. A Combined Approach Toward Consistent Reconstructions of Indoor Spaces Based on 6D RGB-D Odometry and KinectFusion. ACM Trans. Intell. Syst. Technol. 6, 2, Article 14 (March 2015), 10 pages.

H. Dong, N. Figueroa and A. El Saddik, "Towards consistent reconstructions of indoor spaces based on 6D RGB-D odometry and KinectFusion," 2014 IEEE/RSJ International Conference on Intelligent Robots and Systems, Chicago, IL, 2014, pp. 1796-1803.

E. R. Nascimento, G. L. Oliveira, M. F. M. Campos, A. W. Vieira and W. R. Schwartz, "BRAND: A robust appearance and depth descriptor for RGB-D images," 2012 IEEE/RSJ International Conference on Intelligent Robots and Systems, Vilamoura, 2012, pp. 1720-1726.

Brand Code provided by: [Erickson R. Nascimento](http://homepages.dcc.ufmg.br/~erickson/index.html)
6D-RGD-Odometry Code provided by Nadia Figueroa.
