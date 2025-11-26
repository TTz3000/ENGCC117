<img width="1272" height="74" alt="image" src="https://github.com/user-attachments/assets/c2b01482-3c30-4a92-a7ea-2e104b2ba40b" />

## โจทย์
จงแก้ไขโค้ดต่อไปนี้ ให้สามารถรับค่าจากผู้ใช้ เพื่อแสดงผลบนหน้าจอคอมพิวเตอร์ให้ได้ พร้อมทั้งจัดรูปแบบให้ตรงตาม Syntax ที่เรียนมาในห้องเรียน

```c++
#include <stduio.h>

int main() {
    char Name[50] ;
    int  Age = 0 ;
    printf( "Enter your name: " ) 
    scanf( "%s", Name ) ;
    printf( "Enter your age: " ) ;
    scanf( "%d", Age ) ;
    print( "- - - - - -\n" ) ;
    printf( "Hello %s \n", ___ ) ; 
    printf( "Age = %d\n", ___ ) ; 
    
}//end main function
```


## FIX CODE
```c++
#include <stdio.h>

int main() {
    char name[50] ;
    int  age = 0 ;
    printf( "Enter your name : " ) ;
    scanf( "%s", name ) ;
    printf( "Enter your age : " ) ;
    scanf( "%d", &age ) ;
    printf( "------------------\n" ) ;
    printf( "Hello %s \n", name ) ; 
    printf( "Age = %d\n", age ) ; 
    
}
```
![image](https://github.com/user-attachments/assets/a918e892-efb8-4fba-9f6f-0d32202414a0)

## TEST CASE
### Input
### Output

![image](https://github.com/user-attachments/assets/4c6b308c-3f2a-43fb-a37d-752466397c68)





