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
## QUES 2
```
#include<stdio.h>
main()
{
    int n = 65;
    switch(n)
    {
        case 64: printf("case 64");
        break;
        case 'A':printf("case A");
        break;
        default:printf("default case");

    }
}
//// golden notes
//// ans is case A
//// in switch the compiler considers integer and char at the same time
//// if the integer is ascii value of an character
//// so here 65 is ascii character of A, so case A is printed
//// the compiler consider 65 to be an integer as well as A at the same time

```
