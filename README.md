# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
1. Read the number of unknowns and the augmented matrix from the user.
2. Apply Gaussian Elimination to convert the matrix into upper triangular form
3. Use back substitution to find the values of the unknown variables.
4. Display the solution of the system of equations.

## Program:
~~~
import os 
os.environ["OPENBLAS_NUM_THREADS"]="1"
import numpy as np
n=int(input())
a=np.zeros((n,n+1))
for i in range (n):
    for j in range (n+1):
        a[i][j]=float(input())
x=np.zeros(n)
for i in range(n):
    if a[i][i]==0:
        print('divide by zero detected')
        exit()
        
    for j in range(i+1,n):
        ratio=a[j][i]/a[i][i]
        for k in range(n+1):
            a[j][k]=a[j][k]-ratio*a[i][k]
x[n-1]=a[n-1][n]/a[n-1][n-1]
for i in range (n-2,-1,-1):
    x[i]=a[i][n]
    for j in range(i+1,n):
        x[i]=x[i]-a[i][j]*x[j]
    x[i]=x[i]/a[i][i]
for i in range(n):
    print("X%d = %0.2f" % (i,x[i]),end=' ')
~~~
```
/*
Program to find the solution of a matrix using Gaussian Elimination.
Developed by: MONISH.V
RegisterNumber: 212225220066
*/
```

## Output:
<img width="843" height="447" alt="image" src="https://github.com/user-attachments/assets/42e7927a-e1a2-45c4-8671-6c7becd102b1" />


## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

