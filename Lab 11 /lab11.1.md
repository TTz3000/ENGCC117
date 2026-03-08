## Computer Programming for Computer Engineer 

# CODE
```c++
#include <stdio.h>

int binSearch( int data[], int n, int find ) ;

int main() {
    int data[ 6 ] = { 1 , 2 , 3 , 4 , 5 , 7 } ;
    int n = 6 ;
    int find = 5 ; 

    int pos = binSearch( data , n , find ) ;
    if ( pos != -1 ) {
        printf( " Found %d at %d \n " , find , pos ) ;
    } else {
        printf( " Not Found~! \n " ) ;
    }
    
    return 0 ;
}

int binSearch( int data[], int n, int find ) {
    int Left = 0 ;
    int Right = n - 1 ;
    
    while ( Left <= Right ) {
        int Mid = ( Left + Right ) / 2 ; 
        
        if ( data[ Mid ] == find ) {
            return Mid ; 
        } 
        else if ( data[ Mid ] < find ) {
            Left = Mid + 1 ; 
        } 
        else {
            Right = Mid - 1 ; 
        }
    }
    
    return -1 ; 
}
```

## TEST CASE
### Input
```c++

```
### Output
```c++
Found 5 at 4 
```





