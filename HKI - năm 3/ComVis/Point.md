# 2D points

- Can be denoted using a pair of values, x = (x, y)
- Can also be represented using [[Homogeneous coordinates]] , where vectors that differ only by scale are considered to be equivalent. 
 ![[Pasted image 20231019161119.png]]

- This is called the 2D projective space.
- A homogeneous vector x~ can be converted back into an inhomogeneous vector x by dividing through the last element w~:
  ![[Pasted image 20231019161450.png]]

where x- = (x, y, 1) is the augmented vector. Homogeneous points whose last element is w~ = 0 are called ideal points or points at infinity and do not have an equivalent inhomogeneous representation