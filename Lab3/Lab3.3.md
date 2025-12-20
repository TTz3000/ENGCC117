## Computer Programming for Computer Engineer 

# CODE
```c++
#include <stdio.h>
#include <string.h>

struct student {
    char name[20];
    int age ;
    char sex ;
    float gpa ;
};

struct student upgrade ( struct student child ) ;

int main() {
    struct student aboy ;
    aboy.sex = 'M';
    aboy.gpa = 3.00;
    printf("Aboy GPA : %.2f \n" , aboy.gpa);
    aboy = upgrade( aboy ) ;
    printf("Upgrade GPA : %.2f \n" , aboy.gpa);

    struct student agirl ;
    agirl.sex = 'W';
    agirl.gpa = 3.00;
    printf("Agirl GPA : %.2f \n" , agirl.gpa);
    agirl = upgrade( agirl ) ;
    printf("Upgrade GPA : %.2f \n" , agirl.gpa);

    return 0 ;
}

struct student upgrade ( struct student child ) {
    float upgpa = 0;

    if ( child.sex == 'M' ) {
        upgpa = child.gpa * 0.1;
    }

    if ( child.sex == 'W' ) {
        upgpa = child.gpa * 0.2;
    } 

    child.gpa = child.gpa + upgpa;

    return child;
}


```

## TEST CASE
### Input
```c++

```
### Output
```c++
Aboy GPA : 3.00 
Upgrade GPA : 3.30
Agirl GPA : 3.00
Upgrade GPA : 3.60
```





