#Algorithm

***Geeks Links:*** https://www.geeksforgeeks.org/bucket-sort-2/

***Psuedo Code:***
![[Pasted image 20240923171212.png|800]]

***Worst-case Performance:*** O(n^2)

***Average performance:*** O(n^2 + n^2/k + k)

***Worst-case space complexity:*** O(n + k)

***Explaination:***
Given an array of *n* elements, create *k* buckets, then sort the element to the bucket by floor(k * arr\[i] / M)
Sort each bucket
Return the values