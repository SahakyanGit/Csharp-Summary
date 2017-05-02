# Summary on C# <img src="https://github.com/SahakyanGit/SDFCS/blob/master/C%23pic.png" align="right" width="120px" height="120px" /> 
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

___



<h3 align="center"> Struct vs Class </h3>    




In .NET, there are two categories of types, reference types and value types.

Structs are value types and classes are reference types.

The general difference is that a reference type lives on the heap, and a value type lives inline, that is, wherever it 
is your variable or field is defined.

A variable containing a value type contains the entire value type value. For a struct, that means that the variable 
contains the entire struct, with all its fields.

A variable containing a reference type contains a pointer, or a reference to somewhere else in memory where the actual 
value resides.

This has one benefit, to begin with:

value types always contains a value
reference types can contain a null-reference, meaning that they don't refer to anything at all at the moment
Internally, reference types are implemented as pointers, and knowing that, and knowing how variable assignment works, 
there are other behavioral patterns:

copying the contents of a value type variable into another variable, copies the entire contents into the new variable, 
making the two distinct. In other words, after the copy, changes to one won't affect the other
copying the contents of a reference type variable into another variable, copies the reference, which means you now have 
two references to the same somewhere else storage of the actual data. In other words, after the copy, changing the data 
in one reference will appear to affect the other as well, but only because you're really just looking at the same data 
both places
When you declare variables or fields, here's how the two types differ:

variable: value type lives on the stack, reference type lives on the stack as a pointer to somewhere in heap memory 
where the actual memory lives (though note Eric Lippert's article series: The Stack Is An Implementation Detail.)
class/struct-field: value type lives completely inside the type, reference type lives inside the type as a pointer 
to somewhere in heap memory where the actual memory lives.

<b>Classes Only:</b>

Can support inheritance
Are reference (pointer) types
The reference can be null
Have memory overhead per new instance

<b>Structs Only:</b>

Cannot support inheritance
Are value types
Are passed by value (like integers)
Cannot have a null reference (unless Nullable is used)
Do not have a memory overhead per new instance - unless 'boxed'

<b>Both Classes and Structs:</b>

Are compound data types typically used to contain a few variables that have some logical relationship
Can contain methods and events
Can support interfaces
___



<h3 align="center">Abstract vs Interface </h3>    







<b>Abstract class:</b>


A class that cannot be instantiated.  An abstract class is a class that must be inherited and have the methods overridden.
An abstract class is essentially a blueprint for a class without any implementation.



An abstract class is a special kind of class that cannot be instantiated. It normally contains one or more abstract 
methods or abstract properties. It provides body to a class.



<b>Interface:</b>


An interface has no implementation; it only has the signature or in other words, just the definition of the methods without 
the body.



It's an abstract class with public abstract methods all of which must be implemented in the inherited classes.



<b>Abstract or Interface:</b>

Interfaces, like classes, define a set of properties, methods, and events. But unlike classes, interfaces do not provide 
implementation. They are implemented by classes, and defined as separate entities from classes. Even though class 
inheritance allows your classes to inherit implementation from a base class, it also forces you to make most of your 
design decisions when the class is first published.

Abstract classes are useful when creating components because they allow you specify an invariant level of functionality 
in some methods, but leave the implementation of other methods until a specific implementation of that class is needed. 
They also version well, because if additional functionality is needed in derived classes, it can be added to the base 
class without breaking code.



<b>Difference between Abstract class and Interface: </b>


<b>Abstract Class: </b>

1) An abstract method is created by specifying the abstract type modifier.

2) An abstract method contains no body.

3) An abstract method is not implemented by the base class.

4) An abstract method is automatically virtual.

5) A derived class must override it.

6) Abstract class can have modifiers for methods,properties etc.,

7) An abstract class can implement a property.

8) The abstract modifier cannot be applied to static methods.

9) Properties can also be abstract.

10) A class containing abstract methods must be declared as abstract with the abstract specifier.

11) There can be no objects of an abstract class.

12) If a derived class doesn't implement all of the abstract methods in the base class, then the derived class must also       
be specified as abstract.

13) An abstract class can inherit from a class and one or more interfaces.

14) An abstract class can implement code with non-Abstract methods.

15) Abstract class can have constant and fields.

16) An abstract class can have constructors or destructors.

17) An abstract class cannot be inherited from by structures.

18) An abstract class cannot support multiple inheritance.

19) If we add a new method to an abstract class then we have the option of providing default implementation and 
therefore all the existing code might work properly.



<b>Interface:</b>

1) Interfaces cannot be instantiated directly.

2) Interfaces can contain events, method, indexer and properties.

3) An Interface can contain property definitions.

4) Interfaces contain no implementation of methods.

5) Classes and Structs can implement more than one interface.

6) An Interface can be inherited from by structures.

7) An interface itself can inherit from multiple interfaces (Interface can support multiple inheritance).

8) An abstract class can implement a property.

9) If we add a new method to an Interface then we have to track down all the implementations of the interface and define 
implementation for the new method.
___



<h3 align="center">Operators</h3>    









`x?.y` – `null` conditional member access. Returns null if the left hand operand is null.

`x ?? y` – returns `x` if it is `non-null`; otherwise, returns `y`.

`Typeof` – returns the `System.Type` object representing the operand.

`Checked` – enables overflow checking for integer operations.

`Unchecked` – disables overflow checking for integer operations. This is the default compiler behavior.

`default(T)` – returns the default initialized value of type `T`, `null` for reference types, `zero` for numeric types, and `zero/null` filled in members for struct types.

`Sizeof` – returns the size in bytes of the type operand.

`->` – pointer dereferencing combined with member access.

`Is` – type compatibility. Returns `true` if the evaluated left operand can be cast to the type specified in the right operand (a `static` type).

`As` –`SomeClass someObject = obj as SomeClass`.-it seems to return `null` if obj isn't a `SomeClass`.




<b>SomeClass someObject = (SomeClass) obj; VS SomeClass someObject = obj as SomeClass;</b>

With the "classic" method, if the cast fails, an exception is thrown. With the as method, it results in null, which can be checked for, and avoid an exception being thrown.
Also, you can only use "as" with reference types, so if you are typecasting to a value type, you must still use the "classic" method.
Note:
The as method can only be used for types that can be assigned a null value. That use to only mean reference types, but when .NET 2.0 came out, it introduced the concept of a nullable value type. Since these types can be assigned a null value, they are valid to use with the as operator.

___







<h3 align="center">C# Keywords</h3>  




[C# all keywords link](https://docs.microsoft.com/en-us/dotnet/articles/csharp/language-reference/keywords/)

___





<h3 align="center">Nullable<T> class </h3> 
  

`Nullable` types are instances of the `System.Nullable<T> struct`. A nullable type can represent the correct range of values for its underlying `value type`, plus an additional `null` value. For example, a `Nullable<Int32>`, pronounced "Nullable of Int32," can be assigned any value from `-2147483648 to 2147483647`, or it can be assigned the `null` value. A `Nullable<bool>` can be assigned the values `true`, `false`, or `null`. The ability to assign `null` to `numeric` and `Boolean` types is especially useful when you are dealing with databases and other data types that contain elements that may not be assigned a value. For example, a `Boolean` field in a database can store the values `true` or `false`, or it may be undefined.


`Nullable` types represent `value-type` variables that can be assigned the value of `null`. You cannot create a nullable type based on `reference type`. (Reference types already support the null value.)
The syntax `T?` is shorthand for Nullable<T> , where `T` is a value type. The two forms are interchangeable.
 ```c#
Nullable<int> num =5;
//is the same as 
int? num=5;
 ```
 
 ___





<h3 align="center">Generics class</h3> 
  
 
  
```c#
Public class MyClass<T> where T : struct
{
      Public MyClass<T> {}
}

MyClass<SomeStruct> a = new MyClass();   it requires struct.
```

If you delete `where T` : struct this part of code then you can drop `<HERE>` any type.

 ___





<h3 align="center">Constraints</h3> 

<br/>

| Code            | Definition     | 
| -------------   |:-------------: | 
| where T: struct | The type argument must be a value type. Any value type except Nullable can be specified. See Using Nullable Types for more information.
| where T : class    |The type argument must be a reference type; this applies also to any class, interface, delegate, or array type.
| where T : new() | The type argument must have a public parameterless constructor. When used together with other constraints, the new() constraint must be specified last.
| where T : `<base class name>`       | The type argument must be or derive from the specified base class.     | 
| where T : `<interface name>`   |The type argument must be or implement the specified interface. Multiple interface constraints can be specified. The constraining interface can also be generic.|  
| where T : U | The type argument supplied for T must be or derive from the argument supplied for U.|


[More Info](https://docs.microsoft.com/en-us/dotnet/articles/csharp/programming-guide/generics/constraints-on-type-parameters)

 ___





<h3 align="center">Extension Methods</h3> 




```c#
Public static string MyMethod(this string str)
{
     return str; 
}

String s = “some string”;
s.MyMethod();
```

 ___





<h3 align="center">Action And Func</h3> 
                                         


Lambda expressions that don't return a value correspond to a specific `Action` delegate, depending on its number of parameters. Lambda expressions that return a value correspond to a specific `Func` delegate, depending on its number of parameters. For example, a lambda expression that has two parameters but returns no value corresponds to an `Action<T1, T2>` delegate. A lambda expression that has one parameter and returns a value corresponds to `Func<T, TResult>` delegate.

```c#
Static void Main(string[] args)
{ 
    Func<int,int> square = x = > x*x;    //x is parameter, it should return x*x,square is name of the method;
    Console.WriteLine(square(25));
    Action<string> method = x=> Console>WriteLine(x); 
    method(“a”);
} 
```

`Action` is a delegate (pointer) to a method, that takes `zero`, `one` or `more` input parameters, but does not return anything.

`Func` is a delegate (pointer) to a method, that takes `zero`, `one` or `more` input parameters, and returns a value (or reference).

`Predicate` is a special kind of Func often used for comparisons.

 ___





<h3 align="center">Indexers</h3> 

                                                       

`Indexers` are similar to properties. In many ways indexers build on the same language features as `properties`. `Indexers` enable indexed properties: properties referenced using one or more arguments. Those arguments provide an index into some collection of values.

```c#
private string[] arr = new string[100];

        public string this[int i]
        {
            get
            {
                // This indexer is very simple, and just returns or sets
                // the corresponding element from the internal array.
                return arr[i];
            }
            set
            {
                arr[i] = value;
            }
        }

        static void Main(string[] args)
        {
            Operation o = new Operation();
            o[5] = "key";
            Console.WriteLine(o[5]);
            o[101] = "s";
            Console.WriteLine(o[101]);         //System.IndexOutOfRangeException

            Console.ReadKey();
        } 
```

 ___





<h3 align="center">Deeper Dive into foreach</h3> 

```c#  
    var enumerator = collection.GetEnumerator();
    try 
    {
        while (enumerator.MoveNext())
        {
            var item = enumerator.Current;
            Console.WriteLine(item.ToString());
        }
    } 
    finally 
    {
        // dispose of enumerator.
    }
```

 ___





<h3 align="center">UpCast and DownCast</h3> 
  
```c#
DerivedClass instance = new DerivedClass();
instance.Method();

//upcast
BaseClass instanceUp = instance;
instanceUp.Method();

//DownCast
DerivedClass instanceDown = (DerivedClass)instanceUp;
instanceDown.Method();
```
<b>DownCast can’t work without Upcast.</b>

<br/>

# Updates will be soon.









