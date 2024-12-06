# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
1. Import the numpy library
2. Initialize the matrix A with zeros using np.zeros()
3. Perform row echelon on the given matrix
4. Using back substitution solve the obtained equations.

## Program:

'''Program to solve a matrix using Gaussian elimination without partial pivoting.
Developed by: JAYANI N
RegisterNumber: 24900024
'''

    import numpy as np
    n=int(input())
    A=np.zeros((n,n+1))
    x=np.zeros(n)
    for i in range(n):
        for j in range(n+1):
            A[i][j]=int(input())
    for i in range(n):
        for j in range(i+1,n):
            ratio=A[j][i]/A[i][i]
            for k in range(n+1):
                A[j][k]=A[j][k]-ratio*A[i][k]

    x[n-1]=A[n-1][n]/A[n-1][n-1]
    for i in range(n-2,-1,-1):
        x[i]=A[i][n]
        for j in range(i+1,n):
            x[i]=x[i]-A[i][j]*x[j]
        x[i]=x[i]/A[i][i]
    for i in range(n):
        print("X%d = %0.2f" %(i,x[i]),end=" ")

## Output:
![alt text](<Screenshot 2024-12-06 142909.png>)


## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

