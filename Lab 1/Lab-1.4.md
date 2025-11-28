## Computer Programming for Computer Engineer - Lab 1.4

# CODE
```c++
#include <stdio.h>

int GetSet( int [] ); 

int main() {
    int *data, num ;
    num = GetSet( data ) ; 

    return 0 ;
}

int GetSet( int d[] ) {
    int col;
    printf("Input col : ");
    scanf("%d" , &col);

    for (int i = 0; i < col ; i++)
    {
        printf("Input value in col [%d] : " , i);
        scanf("%d" , &d[i]);
    }

    for (int i = 0; i < col ; i++)
    {
        printf("Col [%d] = %d \n" , i , d[i]);
    }

    return col;
}
```

## TEST CASE
### Input
```c++
Input col : 4
Input value in col [0] : 15
Input value in col [1] : 545
Input value in col [2] : 95
Input value in col [3] : 87
```
### Output
```c++
Col [0] = 15 
Col [1] = 545 
Col [2] = 95 
Col [3] = 87 
```





