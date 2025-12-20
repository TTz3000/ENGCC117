## Computer Programming for Computer Engineer 

# CODE
```c++
#include <stdio.h>
#include <string.h>

void go( int ***A, int **Z ) ;

int main (){
    int *b = new int ; *b = 10 ;
    int *c = new int ; *c = 20 ;
    int **a;
    go( &a, &b ) ;
    printf( "\n%d %p %p", **a, *a, a, &a);
    printf( "\n---------------------------------");
    go( &a, &c ) ;
    printf( "\n%d %p %p", **a, *a, a, &a);
    
    return 0 ;
}

void go( int ***A, int **Z ) {
    **A = *Z;
    printf( "\n%d %p %p", ***A, **A, *A, A);
}
```

## TEST CASE
### Input
```c++

```
### Output
```c++
10 0000000000757950 00000000005FFEE0
10 0000000000757950 00000000005FFEE0
---------------------------------
20 0000000000757990 00000000005FFEE0
20 0000000000757990 00000000005FFEE0
```





