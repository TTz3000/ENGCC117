## Computer Programming for Computer Engineer - Lab 1.3

# CODE
```c++
#include <stdio.h>

int *GetSet( int *);

int main() {
    int *data , num ;
    data = GetSet( &num );
    return 0 ;
}

int *GetSet( int *n) {
    printf("Input size of column : ");
    scanf("%d" , n);
    int arr[*n];

    for (int i = 0; i < *n; i++)
    {
        printf("Input value in column [%d] : " , i);
        scanf("%d" , &arr[i]);
    }//End for (input data)

    for (int i = 0; i < *n; i++)
    {
        printf("Column [%d] = %d \n" , i , arr[i]);
    }//End for (print data)

    return n;
}//End F(GetSet)
```

## TEST CASE
### Input
```c++
Input size of column : 3
Input value in column [0] : 16
Input value in column [1] : 47
Input value in column [2] : 96
```
### Output
```c++
Column [0] = 16 
Column [1] = 47
Column [2] = 96
```





