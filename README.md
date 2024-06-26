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
## QUES 3
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
## QUES 18
```
#include<stdio.h>
main()
{

printf("%f\n",5.3%5);

}
// modulo operator dont take float
// it gives remainder
// 53 % 50 = 3
```
## QUES 19
```
#include<stdio.h>
main()
{
    printf("%d",printf("%s","helloworld"));
}
//// ans is helloworld10
//// as printf also returns integer
//// no of char it succcessfully prints
//// it will return 10
```
## QUES 20
```
#include<stdio.h>
main()
{
    printf("%10s","hello");
}
//// ans is _____hello
////5 spaces and 
////%10s means width is 10
////but hello is 5 world long
//// so 5 spaces are prefixed
```
## QUES 21
```
#include<stdio.h>
main()
{
    int a;
    a =1,2,3,4,5;
    printf("%d",a);
}
// assignment operator > comma operaor
// ans is 1 
```
## QUES 22
```
#include<stdio.h>
main()
{
    int a;
    a =(1,2,3,4,5);
    printf("%d",a);
}
// parenthesis operator highest predecence
// ans is 5
// comma operator goes from left to right
// its within the parenthesis
// comma operator is more powerful than assignment
```
## QUES 23
```
#include<stdio.h>
main()
{
    int a = 2;
    int b = a + (1,2,3,4,5);
    printf("%d",b);
}
// ans is 7
// (1,2,3,4,5) = 5
// 2 + 5 = 7
```
## QUES 24
```
#include<stdio.h>
main()
{
    int x=1,y=0,n;
    n = !!x + !y;
    printf("%d",n);
}
// ans is 2
// !! evaluates to 1
// its like a not gate
```
## QUES 25
```
#include<stdio.h>
main()
{
    printf("%d",5%2);
    printf("%d",-5%2);
    printf("%d",5%-2);

}
// do normal remainder cal
// just give sign of dividend
// the number which is to be divided is the dividend
// give sign of dividend
// ans 1-11
```
## QUES 26
```
#include<stdio.h>
main()
{
    printf("%d",15 && 5);
    printf("%d",15 & 5);

}
// && and operator ans is 1
// & bitwise and
// 15 in hex to bin = 1111
// 5 in hex to bin = 0101
// do every bit and = 0101 = 5
// ans is 5 
```
## QUES 27
```
#include<stdio.h>
main()
{
    printf("%d",sizeof(int));
    printf("%d",sizeof(float));
    printf("%d",sizeof(char));

    int i = 5;
    printf("%d",sizeof(++i));
    printf("%d",i);

}
// sizeof returns in memory taken by datatypes in bytes
// int 4 bytes
//float 4 bytes
// bool 4 bytes
//char 1 byte

// sizeof(++i) = int = 4 bytes
// 5
```
## QUES 28
```
#include<stdio.h>
main()
{
    int x = 1;
    switch(x){
        x = x + 1;
        case 1:printf("one");break;
        case 2:printf("two");break;
        default:printf("three");break;
        x = x+1;
    }
    printf("%d",x);

}
// after switch it directly goes to case
// ans is one
// inside switch, control goes inside case only
/// if u do inside case, it will get modified
```
## QUES 29
```
#include<stdio.h>
main()
{
    int x = 1;
    switch(x){
        case1:printf("one");break;
        case2:printf("two");break;
        default:printf("three");break;
    }
//ans is three
//case1 -> no space between case and label
//it will not GIVE COMPILER ERROR
//IT WILL JUST NOT WORL
//DEFAULT WILL BE PRINTED
}
```
## QUES 30
```
#include<stdio.h>
main()
{
    int a,b,c;
        a=b=4;
        c=a==b;
        printf("%d",c);
}
// assignment operator < comparison opeartor
// a==b returns 1
// c = 1
//ans is 1
```
## QUES 31
```
#include<stdio.h>
main()
{
    int x;
    x == ++2;
    printf("%d",x);
}
// no ++ -- with constants or expressions
// only variables
```
## QUES 32
```

#include<stdio.h>
main()
{
    int a = 500,b = 100,c;
    if(!a>=400)
    {
        b=300;
    }
    c=200;
    printf("b=%d,c=%d",b,c);
}
// b=100 and c = 200
// c is 200 ofcourse
// relational > logical
// !(500>=400)
// !true
// false, will not enter ifelse block
```
## QUES 33
```

#include<stdio.h>
main()
{
  int a = b = c = 10;
}
// a is declared
// u are using b and c
// but u have not declared it
// compiler error
```
## QUES 34
```

#include<stdio.h>
main()
{
  int a,b,c;
  a=b=c=50;
  printf("%d%d%d",a,b,c);
}
// ans is 505050
```
## QUES 35
```

#include<stdio.h>
main()
{
  int a,b,c;
  int a;
  printf("%d%d%d",a,b,c);
}
// compiler error
// redeclaration in c is not allowed
```
## QUES 36
```

#include<stdio.h>
main()
{
  printf("abc\b\binfo");
  printf("abc\b\b\b");
}
// ans is info
// its backspace escape sequence
// cursor moves one char to left
// sec ans is abc as cursor moves three char to left 
// but nothing more char to overwrite the previous one
```
## QUES 37
```
#include<stdio.h>
main()
{
  int x[] = {1,2,3,4,5};
  printf("%d",x[0]);
  printf("%d",0[x]);
// both works in similar fashion
}
```
## %o = octal value
## %#o = octal value with prefixed 0
## %d = integer value(decimal)
## %f = float value
## %s = string and char
## %x = hexadecimal
## QUES 38
```

#include<stdio.h>
main()
{
  int x = 052;
  printf("%o\n",x);
  printf("%x\n",x);
  printf("%d",x);
}

// ans is 52(octal) 2a(octal to hex) 42(octal to int)
//%0 = octal value
//%d = integer value
//%f = float value
//%s = string and char
//%x = hexadecimal
```
## QUES 39
```
#include<stdio.h>
main()
{
  int x = 0x43ff;
  int y = 0x43FF;
  printf("%x\n",x);
  printf("%x\n",y);
}
// hex
// ans is 43ff in both cases
```
## if number starts from 0x it is hex, if starts from 0 it is octal
## QUES 40
```
#include<stdio.h>
main()
{
  int x = 0x10+010+10;
  printf("%d\n",x);
}
// hex
// ans is 43ff in both cases
// convert everyone to decimal
//  %d is for decimal
// 0x10 + 010 + 10 = 16 + 8 + 10 = 34
```
## QUES 41
```
#include<stdio.h>
main()
{
  int x = 010;
  printf("%f\n",x);
  printf("%d\n",x);
  printf("%o\n",x);
  printf("%#o\n",x);
}
// ans is 0.0000 8 10 010
```
## QUES 42
## postincrement vs preincrement
i++ is postincrement, the previous val of i is used and after that it is incremented<br/>
++i is preincrement, the previous val of i is first incremented and then it is used 
```
#include<stdio.h>
main()
{
  int x = 10;
  printf("%d\n",x++);
  printf("%d",x);

  int  y = 5;
  printf("%d\n",++y);
  printf("%d",y);

}
// ans is 10 and 11
// ans is 6 and 6
```
## QUES 43
```
#include<stdio.h>
main()
{
  int a = 5;
  a = ++a + ++a;
  printf("%d",a);

}
// ans is 14
// increment have more predecence than addition
// first a is 5
// in expression there are 2 increments changing a to 7
// 7  + 7 = 14 
```
## QUES 44
```
#include<stdio.h>
main()
{
  int a = 5;
  a = ++a + ++a;
  printf("%d",a);

}
// ans is 14
// increment have more predecence than addition
// first a is 5
// in expression there are 2 increments changing a to 7
// 7  + 7 = 14 
```
## QUES 45
```
#include<stdio.h>
main()
{
  int i;
  for(i=0;i<5;i++)
  {

      i =10;
      printf("%d",i);

  }
}
// ans is 10
```
## QUES 46
```

#include<stdio.h>
main()
{
  int i;
  for(i=0;i<5;i++)
  {
      int i;
      i =10;
      printf("%d",i);

  }
}
// ans is 1010101010
//When you declare a variable within a block (such as inside a loop), it shadows any variables with the same name in outer scopes. So, within the0 for loop, 
//the inner i variable is used, and the outer i variable remains unchanged.
```
## QUES 47
```
#include<stdio.h>
int i;
i =1000;
main()
{
      i =10;
      printf("%d",i);
}
// ans is 10
// assignment not possible in global scope
```
## QUES 48
```

#include<stdio.h>
int i = 1000;
main()
{
      int i =10;
      printf("%d",i);
}
// ans is 10
// assignment not possible in global scope
```
## QUES 49
```
#include<stdio.h>
int i = 1000;
main()
{
      int x = 3;
      if(x==2); x = 0 ;
      if(x==3) x++;
      else x+=2;
      printf("x=%d",x);
}
// ans is 2
// semicolon is used in  if
// it will end there
// x = 0 is not in if block
```
## QUES 50
```
#include<stdio.h>
int i = 1000;
main()
{
      int x = 3;
      float y = 3.0;
      if(y==x)
        printf("equal");
      else
      printf("not equal");
}
// equal
// implicit conversion of int to float to compare
```
## QUES 51
```
#include<stdio.h>
main()
{
for (int i=0;i<6;i++)
printf("hallo");
}
// if only one statement
// no need of curly brackets in for loop in c
```
## QUES 52
```
#include<stdio.h>
main()
{
int x  = 1;
if(x--)
    printf("hello");
--x;
else
    printf("helloworld");
}
// compiler error
// else without if block
```
## QUES 53
```
#include<stdio.h>
main()
{
int i = 0;
for(;i<=5;++i)
    printf("hello\n");
}
// i have declared assigned earlier
// the value of i
// it will as expected
// 6 times hello will be printed
```
## QUES 54
```
#include<stdio.h>
main()
{
int i = 0;
for(;i<=5;++i);
    printf("hello\n");
}
// hello is printed once
// as their is a semicolon outside for loop
// it send the for statement there
```
## QUES 55
```
int fun(int j)
static int i = 50;
int k;
if (i == j) {
printf("Hello");
k = fun(i);
return 0; }
else return 0;
//The function will exhaust the runtime stack or run Result
//infinite loop when j = 50
//look carefully
```
## QUES 56
```
#include<stdio.h>
main()
{
int a[3]= {10,4,4};
++a;
}
// compiler error
// only var
// no array and constant
```
## QUES 57
```
#include<stdio.h>
main()
{
++3;
}
// compiler error
// only var
// no array and constant
```
## QUES 58
```
#include<stdio.h>
main()
{
int arr[] = {3,4,5,6,7};
int brr[5] = {1,2,34,56,6};
printf("%d",arr[0]);
printf("%d",brr[0]);
}
// both type of declaration work
// compiler assign memory automatically
```
## QUES 59
```
#include<stdio.h>
main()
{
int arr[] = {3,4,5,6,7};
int brr[5] = {1,2,34,56,6};
printf("%d\n",arr);
printf("%d\n",brr);
}
//You are attempting to print the values of the arrays arr 
//and brr using the %d format specifier in the printf 
//function. However, this usage is incorrect because %d is 
//used to print integers, not arrays.
//When you provide an array name to printf without an index, 
//it's treated as a pointer to the first element of the array. Therefore, what you're actually printing here are the addresses of the first elements of the arrays, 
//not the values of the arrays themselves.
//To print the addresses of the arrays correctly, you should use the %p format specifier and cast the array names to void*:
// correct way
#include<stdio.h>
int main()
{
    int arr[] = {3,4,5,6,7};
    int brr[5] = {1,2,34,56,6};
    printf("%p\n", (void*)arr);
    printf("%p\n", (void*)brr);
    return 0;
}
```
#BITWISE OPERATORS
## right shift operator
(>>)<br/>
divide bt 2^b where b is the number of places u want to shift<br/>
num = num >> 3<br/>
num = num / 2^3<br/>
## left shift operator
(<<)<br/>
multiply bt 2^b where b is the number of places u want to shift<br/>
num = num << 3<br/>
num = num * 2^3<br/>
## QUES 60
```
int func(int num)
{
int count = 0;
while(num)
{
count++;
num >>= 1;
}
return count;
}
\\ num = num / 2
\\ ans is 9
\\ run loop until num becomes 0
```
## %s for printing and taking strings
## %c for printing and taking single character
## in printf and scanf
## no &operator required in strings, only for char
## double quotes for string, single quotes for character
## QUES 61
```
#include<stdio.h>
main()
{
char name[20]="hello";
printf("%s\n", name);
char names[20]={'h','e','l','l','o'};
printf("%s\n", names);
char a[20];
scanf("%s",a);
printf("%s",a);
}
/// ans is
hello
hello
anuragshelhar
anuragshelhar
```
## QUES 62
```
#include<stdio.h>
main()
{
char name = 'h';
printf("%c\n", name);
char a,b;
scanf("%c",&a);
printf("%c",a);
}
```
## QUES 63
```
#include<stdio.h>
main()
{
printf("%c","BHOPAL"[3]);
char a[] = "BHOPAL";
printf("%c\n",a[3]);
printf("%s","BHOPAL"+3);
printf("%s\n","anuragshekhar");
}
//ans  is PAL
// %s print strings not  char
//When you use %s in printf(), it expects a null-terminated 
//character array (string) as an argument. By passing 
//"BHOPAL" + 3, you're passing a pointer to the substring "PAL",
//which is treated as a string by printf().
//Therefore, the output of this printf statement will be PAL, 
//as it prints the substring starting from index 3 of the 
//original string "BHOPAL".
```
## QUES 64
```
#include<stdio.h>
main()
{
char arr[] = "computer science";
printf("%d",sizeof(arr));
}
// ans is 17 bytes
// sizeof return bytes in integer
// computerscience has 16 char
// one char takes one bytes
// also it has ending null character
// so total 17 bytes
```
## QUES 65
```
Predict the Output in C Programming
In the Below Code Snippet what would you put in place of (?) to
print "Hello"
#include<stdio.h>
char arr[] = "HelloWorldHello";
printf("s", ? );
^ Pull up for precise seeking
a) Compiler Error
b) arr
C) arr+10  (CORRECT ANSWER)
d) arr+5

BY DEFAULT THE POINTER POINTS TO FIRTS LETTER IN STRING, WE ADD 10 IN MEMORY TO GET TO 'H'
CHARACTER AND NOW THE POINTER POINTS TO H CHARACTER AND THEN IT PRINTS 'HELLO' ..
```
## QUES 66
```
#include<stdio.h>
void test(struct number n)
{
    n.x=100;
}
struct number{int x;};
int main()
{
    struct number num;
    test(num);
    printf("%d\n",num.x);
    return 0;
}
// compiler error
//In C, when you pass a structure as a parameter
// to a function, the structure needs to be either
// fully defined or declared before the function prototype.
```
## QUES 67
```
#include<stdio.h>

int main()
{
int x, y;
int *ptr;
x = 100;
ptr = &x;
y = *ptr;
printf("%d\n" , y);
printf("%d\n" , ptr);
}
//ans is 100
//pointers stores memory addresses
//to access val in that address use *ptr
// only ptr will give memory address
```
## QUES 68
```
#include<stdio.h>

int main()
{
printf("%d, %d, %d\n", sizeof(char*), sizeof(int*), sizeof(float*));
}
//Golden Statement: No matter which kind of pointer it is.
//Pointer variables takes same
//bytes in the memory. The Value may be 2, 4, 8 based on
//the computer architecture.
// mine one is 4 4 4 
```
## QUES 69
```
#include <stdio.h>
int main() {
int a, b;
а = -3 - -3;
b = -3 - -(-3);
printf("d %d", a , b);
}
// ans is a = 0 b = -6
// if no spaCE BW TWO CONSECUTIVE minus
// IT IS NOT DECREMENT operator
// DO NORMAL MATHS
// BY THE WAY PARENTHESIS HAS HIGHEST priority
```
## QUES 70
# THE TOUGH ONE
```
#include<stdio.h>
int func()
{
    static int num = 16;
    return num--;
}
main()
{
    for(func();func();func())
        printf("%d\n",func());
}
// 14 11 8 5 2
```
## QUES 71
```
#include<stdio.h>

main()
{
    float a = 9.0;
    printf("%f\n",a);
    printf("%d\n",a);
}
// a = 9.0
// a = 0
// unexpected results garbage value
// u are using %d for floating point numbers
// similar behaviour if condition is vice-versa
// like %f for int values gives garbage 

```
