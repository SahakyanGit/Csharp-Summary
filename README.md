# Short Documentation For C# <img src="https://github.com/SahakyanGit/SDFCS/blob/master/C%23pic.png" align="right" width="120px" height="120px" /> 
<br/>
<br/>
<br/>





<h3 align="center">Value Types - Stack</h3>


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

___
<h3 align="center">Reference Type - Heap</h3>


String

All arrays, even if their elements are value types

Class types, such as Form

Delegates

___

<h3 align="center">Boxing</h3>

```c#
int i = 123;
// The following line boxes i.
object o = i;
 ```
 <h5>Boxing: value type to reference type<h5>

<h3 align="center">Unboxing</h3>


```c#
o = 123;
i = (int)o;  // unboxing
 ```
<h5>Unboxing: reference type to value type<h5>



