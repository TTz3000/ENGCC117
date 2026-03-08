## Computer Programming for Computer Engineer 

# CODE
```c++
#include <stdio.h>

int *knapsack( int *w, int *v, int n, int wx ) ;

int main() {
    int n = 5, wx = 11 ;
    int w[ 5 ] = { 1, 2, 5, 6, 7 } ;
    int v[ 5 ] = { 1, 6, 18, 22, 28 } ;
    
    int *x = knapsack( w, v, n, wx ) ;
    
    for( int i = 0 ; i < n ; i++ ) 
        printf( "%d ", x[ i ] ) ;
        
    printf("\n"); 
    
    delete[] x; 
    
    return 0 ;
}

int *knapsack( int *w, int *v, int n, int wx ) {
    int *x = new int[n];
    for (int i = 0; i < n; i++) {
        x[i] = 0;
    }

    int *indices = new int[n];
    float *ratios = new float[n];
    
    for (int i = 0; i < n; i++) {
       indices[i] = i;
        ratios[i] = (float)v[i] / w[i]; 
    }

    for (int i = 0; i < n - 1; i++) {
        for (int j = i + 1; j < n; j++) {
            if (ratios[indices[i]] < ratios[indices[j]]) {
                int temp =indices[i];
               indices[i] =indices[j];
               indices[j] = temp;
            }
        }
    }

    int curWigth = 0;
    for (int i = 0; i < n; i++) {
        int idx =indices[i]; 
        
        if (curWigth + w[idx] <= wx) {
            x[idx] = 1;                 
            curWigth += w[idx];   
        }
    }

    delete[]indices;
    delete[] ratios;

    return x;
}
```

## TEST CASE
### Input
```c++

```
### Output
```c++

```





