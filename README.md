##Aim:
To implement QR decomposition algorithm using the Gram-Schmidt method.
## Equipment’s required:
1.	Hardware – PCs
2.	Anaconda – Python 3.7 Installation / Moodle-Code Runner
## Algorithm:
1.	Intialize the matrix Q and u
2.	The vector u and e is given by

     ![eqn1](https://github.com/Kishorerz/QRdecomposition/assets/144451216/3faf9aeb-6e0b-4083-9554-aa8c75d01c6e)

    ![eqn2](https://github.com/Kishorerz/QRdecomposition/assets/144451216/e525e00f-30e3-43af-9258-0e90c6f69000)

    ![eqn3](https://github.com/Kishorerz/QRdecomposition/assets/144451216/3d667e78-cc99-4e4b-ac47-6b114e574014)


3.	Obtain the Q matrix   
    ![eqn4](https://github.com/Kishorerz/QRdecomposition/assets/144451216/1d5319f2-2f7a-4a5a-af1e-079b2c91c72c)
4.	Construct the upper triangular matrix R
    ![eqn5](https://github.com/Kishorerz/QRdecomposition/assets/144451216/360c1dad-28d9-4e95-ad94-ee288ea3289d)




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
![Screenshot 2023-12-27 204504](https://github.com/Kishorerz/QRdecomposition/assets/144451216/8f314885-688d-4be9-b488-fe2407428d8a)

## Result
Thus the QR decomposition algorithm using the Gram-Schmidt process is written and verified the result.
