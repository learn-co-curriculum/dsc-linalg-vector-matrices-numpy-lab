
# Vectors and Matrices in Numpy - Lab

## Introduction

In this lab, you'll solve some simple matrix creation and manipulation exercises based on what you've learned so far in this section. The key takeaway here is to be able to understand how to use indexing with matrices and vectors while applying some basic operations.

## Objectives

In this lab you will: 

- Find the shape of vectors and matrices 
- Access and manipulate individual scalar components of a matrix 
- Create vectors and matrices using Numpy and Python

## 1. Define two arrays $A$  with shape $ (4 \times 2)$ and $B$ with shape $(2 \times 3)$ 
So    $A =    
  \left[ {\begin{array}{cc}
   1402 & 191 \\
   1371 &  821\\
   949 &  1437 \\
   147 & 1448 \\
  \end{array} }\right]
$
and
$
B =    
  \left[ {\begin{array}{ccc}
   1 & 2 & 3 \\
   4 & 5 & 6\\
  \end{array} }\right]
$


```python
import numpy as np
A = np.array([[1402, 191], [1371, 821], [949, 1437], [147, 1448]])
B = np.array([[1, 2, 3], [4, 5, 6]])
print ('A = \n', A)
print ('B = \n', B)
```

    A = 
     [[1402  191]
     [1371  821]
     [ 949 1437]
     [ 147 1448]]
    B = 
     [[1 2 3]
     [4 5 6]]


## 2. Print the dimensions of $A$ and $B$ 


```python
print('Shape of A:', A.shape)
print('Shape of B:', B.shape)
```

    Shape of A: (4, 2)
    Shape of B: (2, 3)


## 3. Print elements from $A$

Print the following elements from $A$: 

* First row and first column
* First row and second column
* Third row and second column
* Fourth row and first column


```python
print(A[0, 0])
print(A[0, 1])
print(A[2, 1])
print(A[3, 0])
```

    1402
    191
    1437
    147


## 4. Write a routine to populate a matrix with random data
* Create an $(3 \times 3)$ Numpy array with all zeros (use `np.zeros()`)
* Access each location $(i,j)$ of this matrix and fill in random values between the range 1 and 10 


```python
import random
M = np.zeros((3, 3))
print ('before random data:\n',M)

for x in range(0, M.shape[0]):
    for y in range(0, M.shape[1]):
        M[x][y] = random.randrange(1, 10) 
print ('\nafter random data:\n',M)
```

    before random data:
     [[0. 0. 0.]
     [0. 0. 0.]
     [0. 0. 0.]]
    
    after random data:
     [[7. 7. 9.]
     [5. 3. 3.]
     [8. 2. 2.]]


## 5. Turn the above routine into a function
* Create two $(4 \times 4)$ zero-valued matrices and fill with random data using the function
* Add the matrices together in Numpy 
* Print the results


```python
def fill(matrix):

    for x in range(0, matrix.shape[0]):
        for y in range(0, matrix.shape[1]):
            matrix[x][y] = random.randrange(1, 10)
    
    return matrix

M1 = np.zeros((4, 4))
M2 = np.zeros((4, 4))

M1_filled = fill(M1)
M2_filled = fill(M2)
out = M1_filled + M2_filled

print ('Final output\n\n', out)
```

    Final output
    
     [[ 9. 13. 13. 12.]
     [ 7. 12. 14. 11.]
     [12. 14.  6. 12.]
     [ 6.  5.  7.  7.]]


## Summary 

In this lab, we saw how to create and manipulate vectors and matrices in Numpy. We shall now move forward to learning more complex operations including dot products and matrix inversions.  
