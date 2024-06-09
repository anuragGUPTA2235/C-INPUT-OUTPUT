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
# QUES 3
```
#include<stdio.h>
main()
{
    int n = 65;
    switch(n)
    {
        case 65: printf("case 64");
        break;
        case 'A':printf("case A");
        break;
        default:printf("default case");

    }
}
//// golden notes
//// ans is error - duplicate case value
//// in switch the compiler considers integer and char at the same time
//// if the integer is ascii value of an character
//// so here 65 is ascii character of A
//// the compiler consider 65 to be an integer as well as A at the same time
//// in switch duplicate case value are not accepted
//// each value must be unique
```
## QUES 4
```
#include<stdio.h>
main()
{
    int n = 65;
    switch(n)
    {
        case 65: printf("case 64");

        case 66 :printf("case A");

        default:printf("default case");

    }
}
//// golden notes
//// ans is case 64case Adefault case
//// this behaviour is known as fall through
//// see in switch its like a waterfall.if it enters a case it needs a break to stop, otherwise it will execute
//// every case from that entry case
```
## QUES 5 
```
#include<stdio.h>
main()
{
    int a= 5;
    int b = 10;
    switch(a)
    {
    case a: printf("hello");
    break;
    case b: printf("hello");
    break;
    case 3:
        default:printf("2");
    }
}
//// golden words
//// case label must be integer or character
//// they cant be variable
//// compilation error
```
## QUES 6
```
#include<stdio.h>
main()
{
    if('A'<'a')
        printf("TCS");
    else
        printf("CTS");
}
//// ans is TCS
//// compiler will look into ascii value
//// A : 65
//// a : 97
```
## QUES 7
```
#include<stdio.h>
#define TEST 5
main()
{
    printf("TEST");
}
//// ans is TEST
//// double quotes represent string
```
## OUES 8
```
#include<stdio.h>
main()
{
    printf('helloworld');
}
//// ans is no output
//// never use single quotes in printf
//// single quotes are used for char and not string
//// it will return a large number
//// which is a type of error
//// it tries to access memory it is not allowed
```
