
### How Hough Transform works?
Finding a line  
https://www.youtube.com/watch?v=4zHbI-fFIlI

Note: 
1. Image space: [<img src="https://latex.codecogs.com/gif.latex?y=mx+c"/>]. In term of X and Y coordinates: y = mx + c. 
2. Hough space:  
2.1. Feature space: [<img src="https://latex.codecogs.com/gif.latex?m=(y-c)/x"/>]. In terms of SLOPE (m) and CONSTANCE (c): m = (y - c) / x.  
2.2. Circular space: [<img src="https://latex.codecogs.com/gif.latex?R_{Radius}=X.\cos(\theta)+Y.\sin\theta" />]. In terms of ANGLE (a)  and RADIUS (r): r = X . cos(angle) + Y . sin(angle)
* A point in the Image space is a line in the Hough space. A point in the Image space can take infinitely different values of m and c. Hence, the point representation is a line in the Hough space.
* For better representation of Hough Space formula with Radius and Angle is considered.
 
