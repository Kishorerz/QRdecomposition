# Algorithm for QR Decomposition
## Aim:
To implement QR decomposition algorithm using the Gram-Schmidt method.
## Equipment’s required:
1.	Hardware – PCs
2.	Anaconda – Python 3.7 Installation / Moodle-Code Runner
## Algorithm:
1.	Intialize the matrix Q and u
2.	The vector u and e is given by

      ![ex4](https://github.com/Kishorerz/QRdecomposition/assets/144451216/d5b3d16a-52ac-4b91-b44c-e97eb1aeba6f)
    ![ex6](https://github.com/Kishorerz/QRdecomposition/assets/144451216/b91537f3-b265-4e4d-937c-d1087377e429)
    ![ex3](https://github.com/Kishorerz/QRdecomposition/assets/144451216/4b5e05d9-c04d-4016-beb7-21928e672ba1)


3.	Obtain the Q matrix   
        ![ex1](https://github.com/Kishorerz/QRdecomposition/assets/144451216/6b9e83c2-b15b-4425-ba41-3f24694b6ce9)

4.	Construct the upper triangular matrix R
        ![ex2](https://github.com/Kishorerz/QRdecomposition/assets/144451216/a39b5e54-78d2-42f7-93b9-2840295dd5f8)




## Program:
### Gram-Schmidt Method
```

''' 
Program to QR decomposition using the Gram-Schmidt method
Developed by: KISHOR KUMAR B.
RegisterNumber: 212223240072
'''
import numpy as np
def QR_Decomposition(A):
    n,m=A.shape
    Q=np.zeros((n,n))
    u=np.zeros((n,n))
    u[:,0]=A[:,0]
    Q[:,0]=u[:,0]/np.linalg.norm(u[:,0])
    for i in range (1,n):
        u[:,i]=A[:,i]
        for j in range (i):
            u[:,i]-=(A[:,i])@Q[:,j]*Q[:,j]
        Q[:,i]=u[:,i]/np.linalg.norm(u[:,i])
    R=np.zeros((n,m))
    for i in range (n):
        for j in range(i,m):
            R[i,j]=A[:,j]@Q[:,i]
    print(Q)
    print(R)
    
    
    
    
a = np.array(eval(input()))
QR_Decomposition(a)





```

## Output
![output](<Screenshot 2023-12-27 204504.png>)
## Result
Thus the QR decomposition algorithm using the Gram-Schmidt process is written and verified the result.
