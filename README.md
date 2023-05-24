# C# Interview Questions And Answers

Most targeted up-to-date C# interview questions and answers list

# Table of Contents

1. [What is C#?](#1-what-is-c)
2. [What are the access modifiers in C#?](#2-what-are-the-access-modifiers-in-c)
3. [What is the difference between readonly and const in C#?](#3-what-is-the-difference-between-readonly-and-const-in-c)
4. [Explain the difference between String and StringBuilder in C#.](#4-explain-the-difference-between-string-and-stringbuilder-in-c)
5. [What is a delegate in C#?](#5-what-is-a-delegate-in-c)
6. [What are nullable types in C#?](#6-what-are-nullable-types-in-c)
7. [Explain the concept of inheritance in C#.](#7-explain-the-concept-of-inheritance-in-c)
8. [What is the difference between ref and out parameters in C#?](#8-what-is-the-difference-between-ref-and-out-parameters-in-c)
9. [What is the purpose of the using statement in C#?](#9-what-is-the-purpose-of-the-using-statement-in-c)
10. [What are the different types of exceptions in C#?](#10-what-are-the-different-types-of-exceptions-in-c)
11. [Explain the concept of interfaces in C#.](#11-explain-the-concept-of-interfaces-in-c)
12. [What is the difference between == and Equals() in C#?](#12-what-is-the-difference-between--and-equals-in-c)
- [Whats more?](#whats-more)
- [Contributing](#contributing)
- [License](#license)

## 1. What is C#?

C# is a modern, object-oriented programming language developed by Microsoft. It is widely used for developing a variety of applications, including desktop, web, and mobile applications.

## 2. What are the access modifiers in C#?

C# provides several access modifiers to control the accessibility of classes, methods, and variables. The commonly used access modifiers are public, private, protected, and internal.

Example:

```csharp
public class MyClass
{
    public int publicVar;
    private int privateVar;
    protected int protectedVar;
    internal int internalVar;
}
```

## 3. What is the difference between readonly and const in C#?

The readonly keyword is used to declare a variable whose value can be assigned only once, either at the time of declaration or in the constructor. The const keyword is used to declare a variable whose value remains constant throughout the program.

Example:

```csharp
public class MyClass
{
    public readonly int readOnlyVar = 10;
    public const int constantVar = 20;
}
```

## 4. Explain the difference between String and StringBuilder in C#.

String is an immutable type, meaning its value cannot be changed once it is created. StringBuilder, on the other hand, is a mutable type that allows efficient string manipulation by appending, inserting, or modifying the contents.

Example using StringBuilder:

```csharp
StringBuilder sb = new StringBuilder();
sb.Append("Hello");
sb.Append(" World");
string result = sb.ToString();
// result will be "Hello World"
```

## 5. What is a delegate in C#?

A delegate in C# is a type that represents a reference to a method. It allows methods to be passed as parameters or stored in variables, enabling functional programming concepts like callbacks and event handling.
Example:

```csharp
public delegate void MyDelegate(string message);

public class MyClass
{
    public static void PrintMessage(string message)
    {
        Console.WriteLine(message);
    }
}

public static void Main()
{
    MyDelegate delegateObj = MyClass.PrintMessage;
    delegateObj("Hello, delegates!");
}
```

## 6. What are nullable types in C#?

Nullable types allow variables to have an additional null value along with their normal value range. They are useful when a variable needs to represent the absence of a value.

Example:

```csharp
int? nullableInt = null;
if (nullableInt.HasValue)
{
    int value = nullableInt.Value;
}
else
{
    Console.WriteLine("nullableInt is null");
}
```

## 7. Explain the concept of inheritance in C#.

Inheritance is a fundamental concept of object-oriented programming that allows a class to inherit properties and methods from another class. The derived class (child class) inherits the members of the base class (parent class) and can extend or override them.

Example:

```csharp
public class Animal
{
    public virtual void MakeSound()
    {
        Console.WriteLine("Animal makes a sound.");
    }
}

public class Cat : Animal
{
    public override void MakeSound()
    {
        Console.WriteLine("Cat meows.");
    }
}

public static void Main()
{
    Animal animal = new Cat();
    animal.MakeSound(); // Output: Cat meows.
}
```

## 8. What is the difference between ref and out parameters in C#?

Both ref and out parameters are used to pass arguments by reference, allowing the method to modify the value of the original variable. However, out parameters are used when the method guarantees to assign a new value to the variable, whereas ref parameters can be assigned a value before being passed to the method.

Example using ref parameter:

```csharp
public void ModifyValue(ref int value)
{
    value += 10;
}

public static void Main()
{
    int num = 5;
    ModifyValue(ref num);
    Console.WriteLine(num); // Output: 15
}
```

Example using out parameter:

```csharp
public void GetSumAndDifference(int a, int b, out int sum, out int difference)
{
    sum = a + b;
    difference = a - b;
}

public static void Main()
{
    int num1 = 10;
    int num2 = 5;
    int resultSum, resultDifference;
    GetSumAndDifference(num1, num2, out resultSum, out resultDifference);
    Console.WriteLine(resultSum); // Output: 15
    Console.WriteLine(resultDifference); // Output: 5
}
```

## 9. What is the purpose of the using statement in C#?

The using statement in C# is used to ensure that an object is properly disposed of after it is no longer needed. It simplifies resource management by automatically calling the Dispose() method of an object that implements the IDisposable interface.

Example:

```csharp
using (StreamReader reader = new StreamReader("file.txt"))
{
    string line = reader.ReadLine();
    Console.WriteLine(line);
} // reader.Dispose() is called automatically
```

## 10. What are the different types of exceptions in C#?

In C#, exceptions are divided into two types: system exceptions (derived from System.Exception) and application exceptions (derived from System.ApplicationException). System exceptions include common exceptions like NullReferenceException, ArgumentException, and InvalidOperationException.

Example:

```csharp
try
{
    int[] numbers = { 1, 2, 3 };
    Console.WriteLine(numbers[4]); // Throws an IndexOutOfRangeException
}
catch (Exception ex)
{
    Console.WriteLine("Exception: " + ex.Message);
}
```

## 11. Explain the concept of interfaces in C#.

An interface in C# is a reference type that defines a contract for classes to implement. It contains method signatures, properties, events, or indexers that implementing classes must provide. Interfaces allow for polymorphism and abstraction.

Example:

```csharp
public interface IShape
{
    void Draw();
}

public class Circle : IShape
{
    public void Draw()
    {
        Console.WriteLine("Drawing a circle.");
    }
}

public static void Main()
{
    IShape shape = new Circle();
    shape.Draw(); // Output: Drawing a circle.
}
```

## 12. What is the difference between == and Equals() in C#?

The == operator is used to compare the values of two variables for equality, whereas the Equals() method is used to compare the contents of two objects. The behavior of the == operator can be overridden by the Equals() method.

Example:

```csharp
string str1 = "Hello";
string str2 = "Hello";

bool result1 = (str1 == str2); // true
bool result2 = str1.Equals(str2); // true
```

## What's more?
<a href="https://interviewplus.ai/developers-and-programmers/c-sharp/questions">A comprehensive list of questions and answers</a>

## Contributing
We welcome contributions from our users to help make this resource as comprehensive and useful as possible. If you have been recently interviewed and encountered a question that is not currently covered on our website, feel free to suggest it as a new question. Your contributions will be added to our platform, and we will make sure to credit you for your contributions. We appreciate your help in making our platform a valuable tool for all job seekers.

## License
MIT License
