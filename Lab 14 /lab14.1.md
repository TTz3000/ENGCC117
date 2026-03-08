## Computer Programming for Computer Engineer 

# CODE
```c++
#include <stdio.h>

int KnapsackBT( int *w, int *v, int n, int wx, int i, int *x ) ;

int main() {
    int n = 5, wx = 11 ;
    int w[ 5 ] = { 1, 2, 5, 6, 7 } ;
    int v[ 5 ] = { 1, 6, 18, 22, 28 } ;
    int *x, vx ;
    
    x = new int[ n ] ;
    
    vx = KnapsackBT( w, v, n, wx, 0, x ) ;
    
    printf( "Value = %d\n", vx ) ; 
    for( int i = 0 ; i < n ; i++ ) {
        printf( "%d ", x[ i ] ) ;
    }
    printf( "\n" ) ;
    
    delete[] x ; 
    
    return 0 ;
}

int KnapsackBT( int *w, int *v, int n, int wx, int i, int *x ) {
    if ( i == n ) {
        return 0 ;
    }
    int *x_skip = new int[n]; 
    int *x_take = new int[n]; 

    int val_skip = KnapsackBT( w, v, n, wx, i + 1, x_skip ) ;
    
    int val_take = 0 ;
    if ( wx >= w[i] ) {
        val_take = v[i] + KnapsackBT( w, v, n, wx - w[i], i + 1, x_take ) ;
    }

    int best_val = 0 ;
    if ( val_take > val_skip ) {
        best_val = val_take ;
        x[i] = 1 ; 

        for ( int j = i + 1 ; j < n ; j++ ) {
            x[j] = x_take[j] ; 
        }
    } else {
        best_val = val_skip ;
        x[i] = 0 ; 
        
        for ( int j = i + 1 ; j < n ; j++ ) {
            x[j] = x_skip[j] ; 
        }
    }

    delete[] x_skip ;
    delete[] x_take ;

    return best_val ; 
}
```

## TEST CASE
### Input
```c++

```
### Output
```c++

```





