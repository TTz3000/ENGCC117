## Computer Programming for Computer Engineer 

# CODE
```c++
#include <stdio.h>

long sumloop( int ) ;
long sumrecur( int ) ;

int main() {
    int n = 10;

    printf( "Sumloop(n) = %ld\n", sumloop( n ) ) ;
    printf( "Sumrecur(n) = %ld\n", sumrecur( n ) ) ;
    printf( "Sumrecur(255) = %lld\n" , sumrecur(255) ) ;
    
    return 0 ;
}

long sumloop( int n ) {
    long sum = 0;
    for (int i = 1; i <= n; i++) {
        sum += i; 
    }
    return sum;
}

long sumrecur( int n ) {
    if (n <= 0) {
        return 0; 
    }
    return n + sumrecur( n - 1 );
}
```

## TEST CASE
### Input
```c++

```
### Output
```c++
Sumloop(n) = 55
Sumrecur(n) = 55
Sumrecur(255) = 32640
```





