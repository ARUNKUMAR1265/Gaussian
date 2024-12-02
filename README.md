# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
1. Using numpy and sys library to calculate Gaussian elimination.
2. get the input from the user and a is an augmented matrix and x will store the solution of the system of linear equation.
3. using for loop to fill the augmented matrix.
4. a[i][i] is used to check the diagonal element is non zero element.
5. using a[j][k] = a[j][k] - ratio*a[i][k] to convert the upper triangular matrix.
6. x[i] = x[i]/a[i][k] this process work backward from  the bottom-most row to the top.
7. using print function to print the output of the program.

## Program:
```
/*
Program to find the solution of a matrix using Gaussian Elimination.
Developed by: Arunkumar S
RegisterNumber: 
24900773
*/
import numpy as np
import sys
n=int(input())
a=np.zeros((n,n+1))
x=np.zeros(n)
for i in range(n):
    for j in range(n+1):
        a[i][j]=float(input())
for i in range(n):
    if a[i][i]==0.0:
        sys.exit('Divide by zero detected!')
    for j in range(i+1,n):
        ratio=a[j][i]/a[i][i]
        for k in range(n+1):
            a[j][k]=a[j][k]-ratio*a[i][k]
x[n-1]=a[n-1][n]/a[n-1][n-1]
for i in range(n-2,-1,-1):
    x[i]=a[i][n]
    for j in range(i+1,n):
        x[i]=x[i]-a[i][j]*x[j]
    x[i]=x[i]/a[i][i]
for i in range(n):
    print('X%d = %0.2f'%(i,x[i]),end=' ')
```

## Output:
![gaussian elimination]()
![Screenshot 2024-11-28 202343](https://github.com/user-attachments/assets/faf39ca5-1ca3-43cf-ae45-c107744d7f4a)



## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

