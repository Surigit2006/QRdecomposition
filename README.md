# Algorithm for QR Decomposition
## Aim:
To implement QR decomposition algorithm using the Gram-Schmidt method.
## Equipment’s required:
1.	Hardware – PCs
2.	Anaconda – Python 3.7 Installation / Moodle-Code Runner
## Algorithm:
1.	Intialize the matrix Q and u
2.	The vector u and e is given by

    ![eqn1](./ex4.jpg)

    ![eqn2](./ex6.jpg)

    ![eqn3](./ex3.jpg)

3.	Obtain the Q matrix   
    ![eqn4](./ex1.jpg)
4.	Construct the upper triangular matrix R
    ![eqn5](./ex2.jpg)



## Program:
### Gram-Schmidt Method
```
''' 
Program to QR decomposition using the Gram-Schmidt method
Developed by: 212224110053
RegisterNumber: M.K.Suriya prakash
'''
import numpy as np
def QR_Decomposition(A):
    
    m,n=A.shape
    Q=np.empty((n, m))
    U=np.empty((n, m))
    U[:,0]=A[:,0]
    Q[:,0]=A[:,0]/np.linalg.norm(U[:,0])
    for i in range(1,m):
        U[:,i]=A[:,i]
        for j in range(i):
            proj=np.dot(A[:,i],Q[:,j])*Q[:,j]
            U[:,i]-=proj
        Q[:,i]=U[:,i]/np.linalg.norm(U[:,i])
    R=np.zeros((m,m))
    for i in range(m):
        for j in range(i,m):
            R[i,j]=np.dot(Q[:,i],A[:,j])
    print(f"The Q Matrix is\n {Q}") 
   
    print(f"The R Matrix is\n {R}")
    
a = np.array(eval(input()))
QR_Decomposition(a)






```

## Output
```

![image](https://github.com/user-attachments/assets/22fbf731-2553-422f-9f59-7130a8033919)

```

## Result
Thus the QR decomposition algorithm using the Gram-Schmidt process is written and verified the result.
