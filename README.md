# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
Step 1: Input the integer n, the size of the system of linear equations.
Step 2: Initialize an n by (n+1) augmented matrix a with zeros and a solution vector x with zeros.
Step 3: Fill the augmented matrix a with user inputs for each coefficient and constant term.
Step 4: For each row i, check if the pivot element a[i][i] is zero; if yes, exit to avoid division by zero.
Step 5: For each row below i, calculate the ratio of the current element to the pivot and update the row by subtracting the pivot row multiplied by this ratio (Gaussian elimination).
Step 6: After forming the upper triangular matrix, compute the last variable x[n-1] by dividing the last constant term by the last pivot element.
Step 7: Perform back substitution from row n-2 to 0 to find each unknown by subtracting the known terms and dividing by the pivot element.
Step 8: Print the solutions x[0] to x[n-1] formatted to two decimal places.

## Program:
```
'''Program to solve a matrix using Gaussian elimination without partial pivoting.
Developed by: Prathik TS
RegisterNumber: 212224240117
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
        sys.exit('divide by zero detected')
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
    print("X%d = %0.2f"%(i,x[i]),end=' ')
```

## Output:
![gaussian elimination]()
![image](https://github.com/user-attachments/assets/75633e3a-f42d-4a1f-a142-97a8437a5562)


## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

