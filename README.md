# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm

1.Import NumPy for matrix operations

2. Get the input matrix and the right-hand-side vector.

3. Apply Gaussian Elimination to solve the system of linear equations

4. Print the solution and end the program.
   

## Program:

```

'''Program to solve a matrix using Gaussian elimination without partial pivoting.

Developed by: Kishore Kumar P

RegisterNumber: 26002452

'''

import os

os.environ["OPENBLAS_NUM_THREADS"]="1"

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

        sys.exit("Divide by zero detected!")

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
<img width="1202" height="552" alt="Screenshot 2026-10-16 094259" src="https://github.com/user-attachments/assets/29121a6f-2aa0-452f-bf94-474e12318646" />

<img width="1128" height="512" alt="Screenshot 2026-10-16 094330" src="https://github.com/user-attachments/assets/0f687fca-606b-4c8a-a733-58d38c13620c" />

<img width="1110" height="817" alt="Screenshot 2026-10-16 094440" src="https://github.com/user-attachments/assets/e835b599-bf3f-4edb-ab72-d798befabbf2" />


## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

