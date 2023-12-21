# 2D lines:
- 2D lines can also be represented using homogeneous coordinates L = (a, b, c)
- The corresponding line equation is

![[Pasted image 20231019161932.png]]

- We can normalize the line equation vector so that
![[Pasted image 20231019162112.png]]

- In this case, n^ is the normal vector perpendicular to the line and d is its distance to the origin (Figure 2.2). (The one exception to this normalization is the line at infinity l~ = (0, 0, 1), which includes all ideal points at infinity.)
- We can also express n^ as a function of rotation angle $\alpha$,  n^ = ( $n_x$ , $n_y$ ) = ( $cos \alpha$ , $sin\alpha$ ) (Figure 2,2a). This representation is commonly used in the Hough transform line-finding algorithm. The combination of ( $\alpha$ , d ) is also known as polar coordinates

![[Pasted image 20231019163142.png]]

- When using homogeneous coordinates, we can compute the intersection of two lines as
![[Pasted image 20231019163348.png]]
where x is the cross product operator. Similarly, the line joining two points can be written as:
![[Pasted image 20231019163458.png]]
- When trying to fit an intersection point to multiple lines or, conversly, a line to multiple points, least squares techniques can be used.