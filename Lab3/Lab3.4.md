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

void Getstudent( struct student child[][ 10 ], int *room ) ;

int main() {
    struct student children[ 20 ][ 10 ] ;
    int group ;
    Getstudent( children, &group );

    for (int i = 0 ; i < group ; i++ ) {
        printf("\n Room : %d \n", i + 1);    
        for (int j = 0; j < 10; j++) {
            printf("Student %d : Name:%s  Age:%d  Sex:'%c'  GPA: %0.2f \n", j ,
                                children[i][j].name,
                                children[i][j].age,
                                children[i][j].sex,
                                children[i][j].gpa
                                );
        }
    }
    return 0 ;
}

void Getstudent( struct student child[][ 10 ], int *room ) {
    printf("Enter number of room : ");
    scanf("%d", room); 

    for (int i = 0 ; i < *room ; i++ ) {
        printf("\nRoom : %d \n", i + 1);    
        for (int j = 0; j < 10; j++) {
            printf("Student %d :Enter name, age, sex, gpa : ", j );
            scanf("%s %d %c %f", child[i][j].name,
                                &child[i][j].age,
                                &child[i][j].sex,
                                &child[i][j].gpa
                                );
        }
    }
}
```

## TEST CASE
### Input
```c++
Enter number of room : 1

Room : 1
Student 0 :Enter name, age, sex, gpa : Jonh 19 M 3.66
Student 1 :Enter name, age, sex, gpa : Rem 19 W 2.24
Student 2 :Enter name, age, sex, gpa : Faramour 2000 M 3.54
Student 3 :Enter name, age, sex, gpa : Guorgh 30 M 2.76
Student 4 :Enter name, age, sex, gpa : YRU 24 M 1.77
Student 5 :Enter name, age, sex, gpa : Yoru 17 M 3.34
Student 6 :Enter name, age, sex, gpa : KillarQreen 10 M 3.21
Student 7 :Enter name, age, sex, gpa : Lily 3 W 4.00
Student 8 :Enter name, age, sex, gpa : JoePaiNai 56 M 2.63
Student 9 :Enter name, age, sex, gpa : Tae 19 M 3.33

```
### Output
```c++
 Room : 1
Student 0 : Name:Jonh  Age:19  Sex:'M'  GPA: 3.66
Student 1 : Name:Rem  Age:19  Sex:'W'  GPA: 2.24
Student 2 : Name:Faramour  Age:2000  Sex:'M'  GPA: 3.54
Student 3 : Name:Guorgh  Age:30  Sex:'M'  GPA: 2.76
Student 4 : Name:YRU  Age:24  Sex:'M'  GPA: 1.77
Student 5 : Name:Yoru  Age:17  Sex:'M'  GPA: 3.34
Student 6 : Name:KillarQreen  Age:10  Sex:'M'  GPA: 3.21
Student 7 : Name:Lily  Age:3  Sex:'W'  GPA: 4.00
Student 8 : Name:JoePaiNai  Age:56  Sex:'M'  GPA: 2.63
Student 9 : Name:Tae  Age:19  Sex:'M'  GPA: 3.33
```





