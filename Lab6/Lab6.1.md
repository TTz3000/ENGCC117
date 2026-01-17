## Computer Programming for Computer Engineer 

# CODE
```c++
#include <stdio.h>
#include <string.h>

using namespace std;

struct studentNode {
    char name[ 20 ];
    int age;
    char sex;
    float gpa;
    struct studentNode *next;
    struct studentNode *back;
};

void ShowAll( studentNode *walk );
void GoBack( studentNode **now );
void DelNode( studentNode **start, studentNode **now );
studentNode *AddNode( studentNode **start, const char *n, int a, char s, float g );
void InsNode( studentNode **start, studentNode *now, const char *n, int a, char s, float g );

int main() {
    studentNode *start, *now;
    start = NULL; 
    now = AddNode(&start , "one" , 6, 'M', 3.11 ); ShowAll( start );
    now = AddNode(&start , "two" , 8, 'F', 3.22 ); ShowAll( start );

    InsNode(&start , now , "three" , 10 , 'M' , 3.33 ); ShowAll( start );
    InsNode(&start , now , "four" , 12 , 'F' , 3.44 ); ShowAll( start );

    GoBack( &now );

    DelNode(&start , &now ); ShowAll( start );
    DelNode(&start , &now ); ShowAll( start );
    DelNode(&start , &now ); ShowAll( start );

    return 0;
}

void ShowAll( studentNode *walk ) {
    while ( walk != NULL ) {
        printf( "%s ", walk->name );
        walk = walk -> next;
    }
    printf("\n");
}

studentNode *AddNode(studentNode **start, const char *n, int a, char s, float g) {
    // เปลี่ยนจาก malloc เป็น new
    studentNode *newnode = new studentNode;
    strcpy( newnode -> name , n );
    newnode -> age = a;
    newnode -> sex = s;
    newnode -> gpa = g;
    newnode -> next = NULL;
    newnode -> back = NULL;

    if (*start == NULL) {
        *start = newnode;
    } else {
        studentNode *temp = *start;
        while (temp -> next != NULL ) {
            temp = temp->next;
        }
        temp -> next = newnode;
        newnode -> back = temp;
    }
    return newnode;
}

void InsNode(studentNode **start, studentNode *now, const char *n, int a, char s, float g) {
    if ( now == NULL ) {
       return ; 
    }

    studentNode *newnode = new studentNode;
    strcpy(newnode->name, n);
    newnode -> age = a;
    newnode -> sex = s;
    newnode -> gpa = g;

    newnode -> next = now;
    newnode -> back = now->back;

    if ( now -> back != NULL ) {
        now -> back -> next = newnode;
    } else {
        *start = newnode;
    }
    now -> back = newnode;
}

void GoBack(studentNode **now) {
    if (*now != NULL && ( *now ) -> back != NULL ) {
        *now = ( *now ) -> back;
    }
}

void DelNode(studentNode **start, studentNode **now) {
    studentNode *ptr = *now;
    if ( ptr == NULL ) {
        return;
    }

    if ( ptr -> back != NULL ) {
        ptr -> back -> next = ptr -> next;
    } else {
        *start = ptr -> next;
    }

    if ( ptr -> next != NULL ) {
        ptr -> next -> back = ptr -> back;
        *now = ptr -> next;
    } else {
        *now = ptr -> back;
    }
    delete ptr ;
}
```

## TEST CASE
### Input
```c++
```
### Output
```c++
one 
one two
one three two
one three four two
one three two
one three
one
```





