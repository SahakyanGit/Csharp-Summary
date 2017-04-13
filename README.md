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

___


<h3 align="center">Compile-time </h3>      

<br/>

Compile time error -the time period in which you, the developer, are compiling your code.

<br/>

<h3 align="center"> Run-time</h3>    

<br/>

Run-time: the time period which a user is running your piece of software.
On the other hand, an error like the following can not be detected by the compiler. 
You will receive an error/exception at run-time (when the program is run).

___



<h3 align="center">Readonly vs Const</h3>    




`Readonly`: can change only in constructor or with defining some field.

`Const:`you must define it then use , but `readonly` can be defined later,`const` can’t be static.

___



<h3 align="center">Override vs Overload </h3>    
                                         


<b>What is  Method Overloading ?</b>
 
Creating a multiple methods in a class with same name but different parameters  and types is called as method 
overloading.method overloading is  the example of Compile time polymorphism which is  done at compile time.
 
` Method overloading can be achieved by using following things :`

	• By changing the number of parameters used.
 
	• By changing the order of parameters.
 
	• By using different data types  for the parameters.
 
e.g
```c#
	1. public class Methodoveloading    
	2.   {    
	3.     public  int  add(int a, int b)  //two int  type Parameters method  
	4.     {    
	5.         return a + b;    
	6.         
	7.     }    
	8.     public  int  add(int a, int b,int c)  //three int  type Parameters with same method same as above  
	9.     {    
	10.         return a + b+c;    
	11.     
	12.     }    
	13.     public  float  add(float a, float b,float c ,float d)  //four float type Parameters with same method same 
                //as above two method                
	14.     {    
	15.         return a + b+c+d;    
	16.     
	17.     }    
	18.   }  
 ```
 
 
In the above example ,there  are three methods with same method same but they differ with number of parameters and type 
of parameters ,hence this types of methods is called as method overloading.


<b>FAQ of Method Overloading </b>

<b>Question</b>-    Can method overloading has same numbers of parameters and Name with different return types?

<b>Answer</b>-  No, because conflict is happen in methods while ing the parameters .
 
Now let us learn about the Method overriding
  
<b>What is Method overriding ?</b>
 
Creating the method in a derived class with same name, same parameters and same return type as in base class is called as 
method overriding.
Method overriding is the example of run time polymorphism,how its is the part of run time polymorphism i will explain in
detail.
 
Some Key Points of  Method overriding
	•  Method overriding is only possible in derived class  not within the same class where the method is  declared.
 
	• Only those methods are overrides in the derived class which is declared in the base class with the help of
          virtual keyword or abstract keyword.
          
 e.g
 ```c#
	1. public class Account
	2.   {  
	3.     public  virtual int balance()  
	4.     {  
	5.         return 10;  
	6.     }  
	7.   }  
	8. public class  Amount:Account
	9. {  
	10.      
	11.     public override  int balance()  
	12.     {  
	13.         return 500;  
	14.     }  
	15. }
 ```
 Output of the above Program is
	• 10 and 500


In the above small program their are two classes `Account` and `Amount` and both the classes contain same method Name that 
`balance()` in which `Account` class method  `returns 10` and `Amount` class `returns 500` at run time because `Account` class  method 
is overridden in a class `Amount`.
The Method overriding is very useful when  we wants to return different output of same method in different class according 
to the need.
Let us consider the example I wants to provide the discount on particular product according to the Customer category that 
A,B,C in this scenario suppose A,B,C are the classes and `Discount` is the class which contains virtual `CustDiscount()`
method,then i simply override it on class A,B,C instead of writing three different methods for each class.


