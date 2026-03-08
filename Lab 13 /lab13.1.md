## Computer Programming for Computer Engineer 

# CODE
```c++
#include <stdio.h>

int *knapsaCKdp( int *w, int *v, int n, int wx ) ;

int main() {
    int n = 5, wx = 11 ;
    int w[ 5 ] = { 1, 2, 5, 6, 7 } ;
    int v[ 5 ] = { 1, 6, 18, 22, 28 } ;
    int *x ;
    
    x = knapsaCKdp( w, v, n, wx ) ;
    
    for( int i = 0 ; i < n ; i++ ) 
        printf( "%d ", x[ i ] ) ;
        
    printf("\n"); 
    delete[] x; 
    return 0 ;
}

int *knapsaCKdp( int *w, int *v, int n, int wx ) {
    int **dp = new int*[n + 1];
    for (int i = 0; i <= n; i++) {
        dp[i] = new int[wx + 1];
        for (int j = 0; j <= wx; j++) {
            dp[i][j] = 0; 
        }
    }

    for (int i = 1; i <= n; i++) {
        for (int w_curr = 1; w_curr <= wx; w_curr++) {
            if (w[i - 1] <= w_curr) {
                int not_include = dp[i - 1][w_curr];
                int include = dp[i - 1][w_curr - w[i - 1]] + v[i - 1];
                dp[i][w_curr] = (include > not_include) ? include : not_include;
            } else {
                dp[i][w_curr] = dp[i - 1][w_curr];
            }
        }
    }

    int *x = new int[n];
    for (int i = 0; i < n; i++) {
        x[i] = 0; 
    }
    int res = dp[n][wx];
    int curr_weight = wx;

    for (int i = n; i > 0 && res > 0; i--) {
        if (res != dp[i - 1][curr_weight]) {
            x[i - 1] = 1;     
            res -= v[i - 1];      
            curr_weight -= w[i - 1]; 
        }
    }

    for (int i = 0; i <= n; i++) {
        delete[] dp[i];
    }
    delete[] dp;

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





