## Computer Programming for Computer Engineer - Lab 1.5

# CODE
```c++
#include <stdio.h>

void GetMatrix( int value[], int *row, int *col ) ;

int main() {
    int *data, m, n ;
    GetMatrix( data, &m, &n);
    return 0 ;
}

void GetMatrix( int value[], int *row, int *col ) {
    printf("How many row : ");
    scanf("%d", row);
    printf("How many col : ");
    scanf("%d", col);

    value = new int[*row * *col];

    for (int i = 0; i < *row ; i++) {
        for (int j = 0; j < *col ; j++) {
            printf("Input value in [%d][%d] : " , i , j );
            scanf("%d" , &value[ i * *col + j ]);
    }
    }
    for (int i = 0; i < *row ; i++) {
        for (int j = 0; j < *col ; j++) {
            printf("Column [%d][%d] : %d \n" , i , j , value[ i * *col + j ]);
    }
    }
}
```

## TEST CASE
### Input
```c++
How many row : 2
How many col : 2
Input value in [0][0] = 48
Input value in [0][1] = 59
Input value in [1][0] = 15
Input value in [1][1] = 26
```
### Output
```c++
Column [0][0] : 48
Column [0][1] : 59
Column [1][0] : 15
Column [1][1] : 26
```





