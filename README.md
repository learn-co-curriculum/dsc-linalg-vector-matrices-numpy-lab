
# Vectors and Matrices in Numpy - Lab

## Introduction

This lab will ask you to perform some simple matrix creation and manipulation exercises based on what we have covered so far in this section. The key takeaway here for you is to be able to understand how to using indexing with matrices and vectors while applying some basic operations.

## Objectives
You will be able to:
* Define vectors and matrices in NumPy
* Check the shape of vectors and matrices
* Access and manipulate individual scalar components of a matrix. 

### 1. Define two arrays A (4x2) and B (2x3) 
```
A = 1402, 191 
    1371, 821 
    949, 1437
    147, 1448
    
B = 1, 2, 3
    4, 5, 6
    ```


```python
import numpy as np
A = np.array([[1402, 191], [1371, 821], [949, 1437], [147, 1448]])
B = np.array([[1, 2, 3], [4, 5, 6]])
print ('A=\n', A)
print ('B=\n', B)
```

    A=
     [[1402  191]
     [1371  821]
     [ 949 1437]
     [ 147 1448]]
    B=
     [[1 2 3]
     [4 5 6]]



```python
B
```




    array([[1, 2, 3],
           [4, 5, 6]])



## 2. Print the dimensions of A and B 


```python
print('Shape of A:',A.shape)
print('Shape of B:',B.shape)
```

    Shape of A: (4, 2)
    Shape of B: (2, 3)


## 3. Print some of the elements from A at following locations
* first row and first column
* first row and second column
* third row and second column
* fourth row and first column


```python
print(A[0,0])
print(A[0,1])
print(A[2,1])
print(A[3,0])
```

    1402
    191
    1437
    147


## 4. Write a routine to populate matrix with random data
* Create an 3x3 numpy array with all zeros (use `np.zeros()`)
* Access each location i,j of this matrix and fill in random values between the range 1 and 10. 


```python
import random
M = np.zeros((3,3))
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
     [[7. 5. 1.]
     [5. 7. 9.]
     [3. 5. 5.]]


## 5. Turn above routine into a function.
* Create two 4x4 zero valued matrices and fill with random data using the function
* Add the matrices together in numpy 
* Show the results


```python
def fill(matrix):

    for x in range(0, matrix.shape[0]):
        for y in range(0, matrix.shape[1]):
            matrix[x][y] = random.randrange(1, 10)
    
    return matrix

M1 = np.zeros((4,4))
M2 = np.zeros((4,4))

M1_filled = fill(M1)
M2_filled = fill(M2)
out = M1_filled + M2_filled

print ('Final output\n\n', out)
```

    Final output
    
     [[10.  4.  6. 15.]
     [10.  4.  8. 15.]
     [ 9. 12.  9. 13.]
     [14. 12.  8.  7.]]


## Summary 

In this lab, we saw how to create and manipulate vectors and matrices in numpy. We shall now move forward to learning more complex operations including dot products and inverses. 
