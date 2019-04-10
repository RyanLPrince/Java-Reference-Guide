# Operators

## Summary

|Operator Type |                                                                                               |
|-             |-                                                                                              |
|Unary         | (Postfix) *expr*++, *expr*--; (Prefix) ++*expr*, --*expr*, +*expr*, -*expr*, !*expr*,  ~*expr*|
|Artithmetic   | *  /  +  -  %                                                                                 |
|Relational    | <  >  <=  >=  instanceof  ==  !=                                                              |
|Bitwise       | & ^ \|                                                                                        |
|Logical       | &&   \|\|                                                                                     |
|Ternary       |  ? :                                                                                          |
|Assignment    | =  +=  -=  /=  *=   %=  &=  ^=   \|=      <<=     >>=     >>>=                                           |
|Shift         | >>    <<     >>>                                                                              |
  
## Unary 

* The Java unary operators require only one operand. 
* Unary operators are used to perform various operations:
  - Incrementing and decrementing a value by one
  - Negating an expression
  - Inverting the value of a boolean
  
~~~
int a = 10;
int b = 10;
boolean c = true;

System.out.println(++a); // increment before print operation (11)
System.out.println(a++); // increment after print operation (11)
System.out.println(a); // 12
System.out.println(--a); // decrement before print operation(11)

System.out.println(++b + b++) // 11 + 11 

System.out.println(!c); // false
~~~
> The unary bitwise complement operator `~` inverts a bit pattern; it can be applied to any of the integral types, making every "0" a "1" and every "1" a "0". For example, a byte contains 8 bits; applying this operator to a value whose bit pattern is "00000000" would change its pattern to "11111111".

## Arithmetic 

~~~
int a = 10;
int b = 5;

System.out.println( a + b); //15
System.out.println( a - b); //5
System.out.println( a * b); //50
System.out.println( a / b); //2
System.out.println( a % b); //0 modulo remainder of 10/5
~~~

## Relational 
~~~
int a = 10;
int b = 5;
String d = "Hello"

System.out.println(a>b); //true
System.out.println(a==a); //true
System.out.println(d instanceof String); //true
System.out.println(b<=a); //true
~~~

## Bitwise and Logical

~~~
boolean a = true;
boolean b = true;

System.out.println(a & b); // true
System.out.println(a | b); // true
System.out.println(a ^ b); // false. Checks if exactly one condition is true (exclusive or).

System.out.println(a && c); // true
System.out.println(a || c); // true
System.out.println(c || a); // null pointer exception because there is no variable c
~~~
* Logical `&&` operator does not check the second operand if the first operand is false.
* Logical `||` operator does not check the second oepramd if the first operand is true.
* The bitwise `&` and `|` operator always checks both conditions whether first condition is true or false.

# Ternary 
* Java Ternary operator is used as one liner replacement for if-then-else statement and used a lot in java programming. it is the only conditional operator which takes three operands.

~~~
int price =10;
String affordable = "Price is affordable";
String unaffordable = "Price is unaffordable";

if ( price <5 ){
  System.out.println(affordable);
}
else{
  System.out.println(unaffordable);
}

System.out.println(price<5 ? affordable : unaffordable);
~~~
~~~
return_value = (true/false condition)? (if true return) : (else return)
~~~

## Assignment

~~~
int a=10;   
boolean b= false;
a+=4; //a=a+4 (a=10+4)  
a-=4; //a=a-4 (a=10-4)
a*=4; //a=a*4 
b&=true; // false (b & true) 
b|=true; // true (b | true)
~~~

