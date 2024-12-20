# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
1. Get the matrix from user.
2. Using numpy library we solve the matrix using gaussian elimination with partial pivoting
3. Print the result matrices.
4. End the program.

## Program:
~~~
import numpy as np
n=int(input())
matrix=np.zeros((n,n+1))
x=np.zeros(n)
for  i in range(n):
    for j in range(n+1):
        matrix[i][j]=int(input())
for i in range (n):
    for j in range(i+1,n):
        ratio=matrix[j][i]/matrix[i][i]
        for k in range(n+1):
            matrix[j][k]=matrix[j][k]-ratio*matrix[i][k]

#back substituion
x[n-1]=matrix[n-1][n]/matrix[n-1][n-1]
for i in range(n-2,-1,-1):
    x[i]=matrix[i][n]
    for j in range(i+1,n):
        x[i]=x[i]-matrix[i][j]*x[j]
    x[i]=x[i]/matrix[i][i]
for i in range(n):
    print("X%d = %0.2f" %(i,x[i]),end=" ")

~~~

## Output:
![OUTPUT]![Alt text](<Screenshot from 2024-12-20 22-40-37.png>)


## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

