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

struct student ( *Getstudent( int *room ) ) [10] ;

int main() {
    struct student ( *children )[ 10 ] ;
    int group ;
    children = Getstudent( &group ) ;

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
    delete [] children;
    return 0 ;
}

struct student ( *Getstudent( int *room ) ) [10] {
    printf("Enter number of room : ");
    scanf("%d", room); 

    struct student (*child)[ 10 ] = new struct student[ *room ][ 10 ];

    for (int i = 0 ; i < *room ; i++ ) {
        printf("\nRoom : %d \n", i + 1);    
        for (int j = 0; j < 10; j++) {
            printf("Student %d :Enter name, age, sex, gpa : ", j );
            scanf("%s %d  %c %f", child[i][j].name,
                                &child[i][j].age,
                                &child[i][j].sex,
                                &child[i][j].gpa
                                );
        }
    }
    return child;
}
```

## TEST CASE
### Input
```c++
Enter number of room : 1

Room : 1 
Student 0 :Enter name, age, sex, gpa : Rour 24 M 2.66
Student 1 :Enter name, age, sex, gpa : John 34 M 2.55
Student 2 :Enter name, age, sex, gpa : Ohm 23 M 1.55
Student 3 :Enter name, age, sex, gpa : MJ 19 W 2.67
Student 4 :Enter name, age, sex, gpa : Rew 18 W 1.42
Student 5 :Enter name, age, sex, gpa : Tae 19 M 4.00
Student 6 :Enter name, age, sex, gpa : Yao 38 M 1.65
Student 7 :Enter name, age, sex, gpa : Sett 500 M 1.78
Student 8 :Enter name, age, sex, gpa : Jony 14 F 3.67
Student 9 :Enter name, age, sex, gpa : Noer 35 W 2.63

```
### Output
```c++

 Room : 1 
Student 0 : Name:Rour  Age:24  Sex:'M'  GPA: 2.66 
Student 1 : Name:John  Age:34  Sex:'M'  GPA: 2.55 
Student 2 : Name:Ohm  Age:23  Sex:'M'  GPA: 1.55 
Student 3 : Name:MJ  Age:19  Sex:'W'  GPA: 2.67 
Student 4 : Name:Rew  Age:18  Sex:'W'  GPA: 1.42 
Student 5 : Name:Tae  Age:19  Sex:'M'  GPA: 4.00 
Student 6 : Name:Yao  Age:38  Sex:'M'  GPA: 1.65
Student 7 : Name:Sett  Age:500  Sex:'M'  GPA: 1.78
Student 8 : Name:Jony  Age:14  Sex:'F'  GPA: 3.67
Student 9 : Name:Noer  Age:35  Sex:'W'  GPA: 2.63
```





