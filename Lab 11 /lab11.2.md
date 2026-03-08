## Computer Programming for Computer Engineer 

# CODE
```c++
#include <stdio.h>

void mergsort( int t[], int k ) ;
void merge( int *u, int m, int *v, int n, int *t ) ;

int main() {
    int data[ 7 ] = { 4, 6, 1, 2, 5, 1, 8 } ;
    int n = 7 ;
    mergsort( data, n ) ;
    for( int i = 0 ; i < n ; i++ ) printf( "%d ", data[ i ] ) ;
    return 0 ;
}

void mergsort( int t[], int k ) {
    if ( k <= 1 ) {
        return ;
    }

    int mid = k / 2 ;
    int leftSize = mid ;
    int rightSize = k - mid ;

    int u[ leftSize ] ;
    int v[ rightSize ] ;

    for ( int i = 0 ; i < leftSize ; i++ ) {
        u[ i ] = t[ i ] ;
    }
    for ( int i = 0 ; i < rightSize ; i++ ) {
        v[ i ] = t[ mid + i ] ;
    }

    mergsort( u , leftSize ) ;
    mergsort( v , rightSize ) ;

    merge( u, leftSize, v, rightSize, t ) ;
}

void merge( int *u, int m, int *v, int n, int *t ) {
    int i = 0 ; 
    int j = 0 ; 
    int k = 0 ; 

    while ( i < m && j < n ) {
        if ( u[ i ] <= v[ j ] ) {
            t[ k ] = u[ i ] ;
            i++ ;
        } else {
            t[ k ] = v[ j ] ;
            j++ ;
        }
        k++ ;
    }

    while ( i < m ) {
        t[k] = u[i] ;
        i++ ;
        k++ ;
    }

    while ( j < n ) {
        t[k] = v[j] ;
        j++ ;
        k++ ;
    }
}
```

## TEST CASE
### Input
```c++

```
### Output
```c++
1 1 2 4 5 6 8 
```





