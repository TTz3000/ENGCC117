## Computer Programming for Computer Engineer 

# CODE
```c++
#include <stdio.h>
#include <string.h>
#include <stdlib.h>

struct stunode {
    char name[ 20 ] ;
    int age ;
    char sex ;
    float gpa ;
    struct stunode *next ;
} ;

class linklist {
    protected :
        struct stunode *start, *now ;
    public :
        linklist() ;
        ~linklist() ;
        void insnode( char n[], int a, char s, float g ) ;
        void delnode() ;
        void gonext() ;
        void gofrist() ;
        void showall() ;
        int findnode( char n[] ) ;
        struct stunode *nownode() ;
        void edit( char n[], int a, char s, float g ) ;
} ;

linklist::linklist() {
    start = NULL;
    now = NULL;
}

linklist::~linklist() {
    struct stunode *temp;
    while(start != NULL) {
        temp = start;
        start = start->next;
        delete temp;
    }
}

void linklist::insnode( char n[], int a, char s, float g ) {
    struct stunode *newnode = new stunode;
    strcpy(newnode->name, n);
    newnode->age = a;
    newnode->sex = s;
    newnode->gpa = g;
    newnode->next = NULL;

    if (start == NULL) {
        start = newnode;
    } else {
        struct stunode *temp = start;
        while (temp->next != NULL) {
            temp = temp->next;
        }
        temp->next = newnode;
    }
}

void linklist::delnode() {
    char searchName[20];
    printf("Enter name to delete : ");
    scanf("%s", searchName);

    struct stunode *temp = start;
    struct stunode *prev = NULL;

    while (temp != NULL && strcmp(temp->name, searchName) != 0) {
        prev = temp;
        temp = temp->next;
    }

    if (temp == NULL) {
        printf("Not found\n");
        return;
    }

    if (prev == NULL) {
        start = temp->next;
    } else {
        prev->next = temp->next;
    }
    delete temp;
    printf("Delete success\n");
}

void linklist::showall() {
    struct stunode *temp = start;
    if (temp == NULL) {
        printf("List empty\n");
        return;
    }
    while (temp != NULL) {
        printf( " Name : %s , Age : %d , Sex : %c , GPA : %.2f\n" , temp ->name , temp ->age , temp ->sex , temp ->gpa );
        temp = temp->next;
    }
}

void linklist::gofrist() { now = start; }
void linklist::gonext() { if( now != NULL ) now = now->next; }
struct stunode* linklist::nownode() { return now; }

int linklist::findnode( char n[] ) {
    struct stunode *temp = start;
    while(temp != NULL) {
        if(strcmp(temp->name, n) == 0) {
            now = temp; 
            return 1;
        }
        temp = temp->next;
    }
    return 0; 
}

void linklist::edit( char n[], int a, char s, float g ) {
    if (now != NULL) {
        strcpy(now->name, n);
        now ->age = a;
        now ->sex = s;
        now ->gpa = g;
    }
}

void Editdata( linklist *ll ) {
    char search[20];
    printf("Enter name to edit : "); 
    scanf("%s", search);
    
    if(ll->findnode(search)) {
        char n[20]; int a; char s; float g;
        printf("New Name : "); scanf("%s", n);
        printf("New Age : "); scanf("%d", &a);
        printf("New Sex (M/F) : "); scanf(" %c", &s);
        printf("New GPA : "); scanf("%f", &g);
        ll->edit(n, a, s, g);
        printf("Edit success\n");
    } else {
        printf("Not found\n");
    }
}

void Adddata( linklist *ll ) {
    char n[20]; int a; char s; float g;
    printf("Enter Name : "); scanf("%s", n);
    printf("Enter Age : "); scanf("%d", &a);
    printf("Enter Sex (M/F) : "); scanf(" %c", &s);
    printf("Enter GPA : "); scanf("%f", &g);
    ll->insnode(n, a, s, g);
    printf("Add success\n");
}

void Finddata( linklist *ll ) {
    char search[20];
    printf("Enter name to find: "); 
    scanf("%s", search);
    
    if(ll->findnode(search)) {
        struct stunode *node = ll->nownode();
        printf("Name: %s, Age: %d, Sex: %c, GPA: %.2f\n", node->name, node->age, node->sex, node->gpa);
    } else {
        printf("Not found\n");
    }
}

void writefile( linklist *ll ) {
    FILE *f = fopen("stu_data.txt", "w");
    if (f == NULL) return;
    
    ll->gofrist();
    struct stunode *node = ll->nownode();
    while(node != NULL) {
        fprintf(f, "%s %d %c %.2f\n", node->name, node->age, node->sex, node->gpa);
        ll->gonext();
        node = ll->nownode();
    }
    fclose(f);
}

void readfile( linklist *ll ) {
    FILE *f = fopen("stu_data.txt", "r");
    if (f == NULL) return; 
    
    char n[20]; int a; char s; float g;
    while(fscanf(f, "%s %d %c %f", n, &a, &s, &g) != EOF) {
        ll->insnode(n, a, s, g);
    }
    fclose(f);
}

int main() {
    linklist listA ;
    int menu ;
    readfile( &listA ) ;
    printf( "Menu - (1) Add (2) Edit (3) Delete (4) Find (5) Show (0) Exit : " ) ;
    scanf( "%d", &menu ) ;
    
    while( menu != 0 ) {
        if ( menu == 1 ) {
            Adddata( &listA ) ;
        } 
        else if ( menu == 2 ) {
            Editdata( &listA ) ;
        } 
        else if ( menu == 3 ) {
            listA.delnode() ;
        } 
        else if ( menu == 4 ) {
            Finddata( &listA ) ;
        } 
        else if ( menu == 5 ) {
            listA.showall() ;
        }
        
        printf( "Menu - (1) Add (2) Edit (3) Delete (4) Find (5) Show (0) Exit : " ) ;
        scanf( "%d" , &menu ) ;
    }
    
    writefile( &listA ) ;
    return 0 ;
}


```

## TEST CASE
### Input Output
```c++
Menu - (1) Add (2) Edit (3) Delete (4) Find (5) Show (0) Exit : 1
Enter Name: Sar
Enter Age: 34
Enter Sex (M/F): m
Enter GPA: 3.8
Added successfully!
Menu - (1) Add (2) Edit (3) Delete (4) Find (5) Show (0) Exit : 2
Enter name to edit: Sat
Not found!
Menu - (1) Add (2) Edit (3) Delete (4) Find (5) Show (0) Exit : 2
Enter name to edit: Sar 
New Name: Matt
New Age: 47
New Sex (M/F): m
New GPA: 2
Edited successfully!
Menu - (1) Add (2) Edit (3) Delete (4) Find (5) Show (0) Exit : 3
Enter name to delete: mat
Not found!
Menu - (1) Add (2) Edit (3) Delete (4) Find (5) Show (0) Exit : 5
 Name : Matt , Age : 47 , Sex : m , GPA : 2.00
Menu - (1) Add (2) Edit (3) Delete (4) Find (5) Show (0) Exit : 4
Enter name to find: matt
Not found
Menu - (1) Add (2) Edit (3) Delete (4) Find (5) Show (0) Exit : 4
Enter name to find: Matt
Found -> Name: Matt, Age: 47, Sex: m, GPA: 2.00
Menu - (1) Add (2) Edit (3) Delete (4) Find (5) Show (0) Exit : 3
Enter name to delete: Matt
Delete success
Menu - (1) Add (2) Edit (3) Delete (4) Find (5) Show (0) Exit : 4
Enter name to find: Matt
Not found
Menu - (1) Add (2) Edit (3) Delete (4) Find (5) Show (0) Exit : 0
```





