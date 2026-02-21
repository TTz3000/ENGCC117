## Computer Programming for Computer Engineer 

# CODE
```c++
#include <stdio.h>
#include <string.h>

struct StuNode {
    char name[20];
    int age;
    char sex;
    float gpa;
    StuNode *next;
};

class linklist {
    protected:
        StuNode *start, **now;
    public:
        linklist();
        virtual ~linklist(); 
        void insnode(const char n[], int a, char s, float g);
        void delnode();
        void gonext();
        virtual void shownode();
};

class newlist : public linklist {
    public:
        void gofirst();
        virtual void shownode(); 
};

int main() {

    linklist list1;
    newlist list2;
    linklist *list3;

    list1.insnode("one", 1, 'A', 1.1);
    list1.insnode("two", 2, 'B', 2.2);
    list1.insnode("three", 3, 'C', 3.3);
    list1.gonext();
    list1.shownode();

    list2.insnode("four", 4, 'D', 4.4);
    list2.insnode("five", 5, 'E', 5.5);
    list2.insnode("six", 6, 'F', 6.6);
    list2.gonext();
    list2.delnode();
    
    list2.gofirst();
    list2.shownode();

    list3 = &list1;
    list3->gonext();
    list3->shownode();

    list3 = &list2;
    list3->shownode();

    return 0;
}

void linklist::insnode(const char n[], int a, char s, float g) {
    StuNode *newNode = new StuNode; 
    strcpy(newNode->name, n);
    newNode->age = a;
    newNode->sex = s;
    newNode->gpa = g;
    newNode->next = *now;
    *now = newNode;
}

void linklist::shownode() {
    if (*now != NULL) {
        printf("%s %d %c %.2f\n", (*now)->name, (*now)->age, (*now)->sex, (*now)->gpa);
    }
}

void newlist::gofirst() {
    now = &start;
}

void newlist::shownode() {
    if (*now != NULL && (*now)->next != NULL) {
        printf("%s %s\n", (*now)->name, (*now)->next->name);
    }
}

linklist::linklist() {
    start = NULL;
    now = &start;
}

linklist::~linklist() {
    now = &start;
    while (start != NULL) {
        delnode();
    }
} 

void linklist::delnode() {
    if (*now != NULL) {
        StuNode *temp = *now;
        *now = (*now)->next;
        delete temp; 
    }
}

void linklist::gonext() {
    if (*now != NULL) {
        now = &((*now)->next);
    }
}


```

## TEST CASE
### Input
```c++
```
### Output
```c++
two 2 B 2.20
six four
one 1 A 1.10
six fou
```





