# Primitives

* A primitive data type is predefined by java. Not created from a class.

|Type|Bit|Range|Default|Wrapper Class|
|-|-|-|-|-|
| boolean | | true or false | false | Boolean  |
| byte | 8 bit | -128 to 127 | 0 | Byte |
| char | 16 bit unicode | u/0000 to \uff | u\0000| Character |
| short | 16 bit | -32768 to 32767 | 0 | Short|
| int | 32 bit | -2×10^9 to 2×10^9 | 0 | Integer|
| long | 64 bit | -9×10^17 to 9×10^17 | 0l | Long|
| float | 32 bit | 3×10^38 to 1.4×10^-45| 0.0f| Float|
|double | 64 bit | 1.7×10^308 to 4.9×10^-324| 0.0d| Double|

* Wrapper classes are objects that encapsulate primitives. 
Q: Why not use primitives directly?
A: Generic classes work with objects and not primitives e.g. maps. 

* Underscores can appear in numeral literals to improve readibility.
  * Only in between, not at the beginning, end, not next to f, l or decimal point.
e.g. 

~~~
int cost = 899_999_873; //improves readability 
~~~
* Is much easier to read that there are five 9s than below.

~~~
int cost = 899999873
~~~

