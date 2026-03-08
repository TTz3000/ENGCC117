## Computer Programming for Computer Engineer 

# CODE
```c++
#include <stdio.h>

void towerofHANOI( int m, int i, int j ) ;

int main() {
    towerofHANOI( 3, 1, 3 ) ;
    return 0 ;
}

void towerofHANOI( int m , int i , int j ) {
    if ( m > 0 ) {
        int k = 6 - i - j ;  
        towerofHANOI( m - 1, i, k ) ;
        printf( " Disc %d from %d to %d \n", m, i, j ) ;
        towerofHANOI( m - 1, k, j ) ;
    }
}
```

## TEST CASE
### Input
```c++

```
### Output
```c++
Disc 1 from 1 to 3
Disc 2 from 1 to 2
Disc 1 from 3 to 2
Disc 3 from 1 to 3
Disc 1 from 2 to 1
Disc 2 from 2 to 3
Disc 1 from 1 to 3
```





