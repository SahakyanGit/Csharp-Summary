# SDFCS

<p align="center" style="color:red"><b>Value Types - Stack</b></p>


All numeric data types
Boolean, Char, andate
All structures, even if their members are reference types
Enumerations, since their underlying type is always SByte, Short, Integer, Long, Byte, UShort, UInteger, or ULong
 
```c#
int a =10;
int b = a;

a=20;
Console.WriteLine(b);     //output 10, because the assignment of a to b creates a copy of the value
```
Value types cannot be null.
Except :
```c#
int? = null;
```
<p align="center" style="color:red"><b>Reference Type - Heap</b></p>



String

All arrays, even if their elements are value types

Class types, such as Form

Delegates




