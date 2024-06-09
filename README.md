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
//// if its "helloworld" it will work
```
## QUES 9
```
#include<stdio.h>
main()
{
    int a = 3;
    switch(a)
    {
    case 1:
    case 5:
    case 6:printf("america");
        break;
    case 2:printf("india");
        break;
    case 3:
    case 7:printf("australia");
            break;
    default:printf("to the moon");
    }
}
// switchcase can be empty
// ans is australia
// fall through
```
## QUES 10
```
#include<stdio.h>
main()
{
    switch(printf("moon"))
    {
    case 4:printf("pie");
        break;
    default:printf("to the moon");
    }
}
// printf statement retuns an integer
// switch accepts only integer or char
// it returns the count of char it printed successfully
// its 4
// ans is moonpie
```
## QUES 11
```
#include<stdio.h>
main()
{
    switch(5)
    {
    case 4:printf("pie");
        break;
    }
}
// DEFAULT IS COMPLETELY OPTIONAL
// ANS IS NO ERROR NO OUTPUT
```
## QUES 12
```
#include<stdio.h>
main()
{
    switch(5)
    {

    }
}
// DEFAULT AND CASES ARE COMPLETELY OPTIONAL
// ANS IS NO ERROR NO OUTPUT
```
## QUES 13
```
#include<stdio.h>
main()
{
int n = 30;
if(n=10)
printf("true");
else
printf("false");
}
// assignment operator
// n = 10 , if its 1 or greater
// its a True value
// ans is true
// comparison operator n==10
// it will compare n with 10
// n is 30
// then ans is false
```
## QUES 14
```
#include<stdio.h>
#define STRING "%s\n"
#define NAME "WELCOME TO OUR CHANNEL"
int main()
{
    printf(STRING,NAME);
    return 0;
}
// macros are not evaluated they
// are replaced
// ans is WELCOME TO OUR CHANNEL
```
## QUES 15
```
#include<stdio.h>
int main()
{
    int i;
    for(i=0;i<20;++i)
    {
        switch(i)
        {
        case 0: i+=5;
        case 1: i+=2;
        case 5: i+=5;
        default:i+=4;

        }
        printf("%d ",i);
    }
}
// ans is 16 21
// at first i is 0
//  since there are no breaks in case, it will enter
// case 0 and also all cases below it
// so 0 + 5 + 2 + 5 + 4 = 16
// then next val of i is 16 
// increment in for loop to become 17
// no 17 in case label
// default 17 + 4 = 21
```
## QUES 16
```
#include<stdio.h>
int main()
{
  int i;
  for(i=-1;i<=10;++i)
  {
      if(i<3)
        continue;
      else
        break;
      printf("dogecoin");
  }
    return 0;
}
//// how many times dogecoin is printed
//// 0 times
//// continue skips the rest code and start the
//// next iteration
////in whole loop first continue skips to next iteraion
//// then break closes the loop

```
## QUES 17
```
#include<stdio.h>
main()
{
if(5)
    printf("IT");
else
    printf("CSE");
printf("ECE");

}
// 5 MEANS true
// IT WILL BE PRINTED
// IF ELSE WITHOUT CURLY TAKES ONLY ONE STATEMENT
// ECE IS OUTSIDE IF ELSE BLOCK
// ANS IS ITECE

```
# SWITCH ONLY TAKES INTEGER OR CHARACTER SO NO FLOAT
