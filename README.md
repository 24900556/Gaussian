# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
1. Input the matrix 
𝐴
A and the right-hand side vector 
𝑏
b, forming an augmented matrix of the form 
[
𝐴
∣
𝑏
]
[A∣b].

2. Forward Elimination:
For each pivot element, eliminate the elements below it in the same column by using the ratio of the corresponding elements.

   Modify the augmented matrix by performing row operations to create a matrix in upper triangular form.

3. Back Substitution:
Starting from the last row, solve for each variable, moving upwards through the rows.

4. Output the solution vector 
X (i.e., the values of the unknowns). 

## Program:
```
/*
Program to find the solution of a matrix using Gaussian Elimination.
Developed by:R.R.Madhumitha 
RegisterNumber: 24900556
*/
```
    import numpy as np
    import sys
    n=int(input())
    a=np.zeros((n,n+1))
    X=np.zeros(n)
    for i in range(n):
        for j in range(n+1):
            a[i][j]=float(input())
    for i in range(n):
        if a[i][j]==0.0:
            sys.exit("Divide by zero is detected !")
        for j in range(i+1,n):
            ratio=a[j][i]/a[i][i]
            for k in range(i,n+1):
                a[j][k]=a[j][k]-ratio*a[i][k]
    X[n-1]=a[n-1][n]/a[n-1][n-1]
    for i in range(n-2,-1,-1):
        sum=a[i][n]
        for j in range(i+1,n):
            sum-=a[i][j]*X[j]
        X[i]=sum/a[i][i]
    for i in range(n):
        print("X%d = %0.2f"%(i,X[i]),end=" ")
            
        
        
        

## Output:
![alt text](<Screenshot 2024-12-06 072427.png>)


## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

