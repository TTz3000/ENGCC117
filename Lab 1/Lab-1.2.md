## Computer Programming for Computer Engineer - Lab 1.1

# CODE
```c++
#include <stdio.h>

void GetSet( int [] , int  *);

int main() {
    int *data, num ;
    GetSet( data, &num );

    return 0 ;
}

void GetSet( int Data[] , int *N) {
    printf("Input size of column : ");
    scanf("%d" , N);

    for (int i = 0; i < *N; i++)
    {
        printf("Input value in column[%d] : " , i);
        scanf("%d" , &Data[i]);
    }//End for (input data)

    for (int i = 0; i < *N; i++)
    {
        printf("Column[%d] = %d \n" , i , Data[i]);
    }//End for (print data)

} //End F(GetSet)
```

## TEST CASE
### Input
```c++
Input size of column : 3
Input value in column[0] : 56
Input value in column[1] : 57
Input value in column[2] : 78
```
### Output
```c++
Column[0] = 56 
Column[1] = 57
Column[2] = 78
```





