# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
1. Read the number of variables n and the n ×(𝑛+1) augmented matrix.
2. Eliminate variables to convert the matrix to upper triangular form.
3. If a pivot element is zero, terminate the program (to avoid divide-by-zero).
4. Solve for the variables starting from the last row up to the first.

## Program:
```
'''Program to solve a matrix using Gaussian elimination without partial pivoting.
Developed by: ARANI VENKATA SUNDARA LEELA KRISHNA
RegisterNumber: 212224240013
'''
import numpy as np
import sys
n=int(input())
a=np.zeros((n,n+1))
x=np.zeros(n)
for i in range(n):
    for j in range(n+1):
        a[i][j]=float(input())
for i in range(n):
    if a[i][j]==0.0:
        sys.exit('Divide by zero detected!')
    for j in range(i+1,n):
        ratio = a[j][i]/a[i][i]
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
<img width="766" height="455" alt="image" src="https://github.com/user-attachments/assets/a3e72b6c-3f1d-4490-a57f-1012fc7b7020" />



## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

