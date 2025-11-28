## Computer Programming for Computer Engineer - Lab 1.6

# CODE
```c++
#include <stdio.h>

int GetMatrix( int *row, int *col ) ;

int main() {
    int *data, m, n ;
    data = GetMatrix( &m, &n) ;
    delete [] data;
    return 0 ;
}

int GetMatrix( int *row, int *col ) {
    printf("How many row : ");
    scanf("%d", row);
    printf("How many col : ");
    scanf("%d", col);

    int *ar;
    ar = new int[ *row * *col];

    for (int i = 0; i < *row; i++) {
        for (int j = 0; j < *col; j++) {
            printf("Input value in [%d][%d] = ", i, j);
            scanf("%d", &ar[ i * *col + j ]);
        }
    }

    for (int i = 0; i < *row ; i++) {
        for (int j = 0; j < *col ; j++) {
            printf("Column [%d][%d] : %d \n" , i , j , ar[ i * *col + j ]);
        }
    }
    
    return *ar;
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





