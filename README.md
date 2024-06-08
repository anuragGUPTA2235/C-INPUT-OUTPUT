# C-INPUT-OUTPUT AND DEEP DIVE INTO C PROGRAMMING LANGUAGE
## QUES 1
```
#include<stdio.h>
#define y 6 + 6
main()
{
    int x = y * y * y;
    printf("the value is %d",x);
}
// golden notes
// macros are not evaluated, they are just replaced
// here y is a macro
// so x = 6+6 * 6+6 * 6+6
// x = 6 + 36 + 36 + 6
// x = 84
// also main can have return type or not, here main dont start with int, its completely fine
```
