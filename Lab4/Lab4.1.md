## Computer Programming for Computer Engineer 

# CODE
```c++
#include <stdio.h>
#include <string.h>

void go( int **p, int *z ) ;

int main (){
    int *a, b = 10, c = 20 ;
    go( &a, &b ) ;
    printf( "\n%d %p %p", *a, a, &a);
    printf( "\n---------------------------------");
    go( &a, &c ) ;
    printf( "\n%d %p %p", *a, a, &a);
    
    return 0 ;
}

void go( int **p, int *z ) {
    *p = z;
    printf( "\n%d %p %p", **p, *p, p);
}
```

## TEST CASE
### Input
```c++

```
### Output
```c++
10 00000000005FFEC4 00000000005FFEC8
10 00000000005FFEC4 00000000005FFEC8
---------------------------------
20 00000000005FFEC0 00000000005FFEC8
20 00000000005FFEC0 00000000005FFEC8
```





