# C# & .NET Basics: Concepts, Types, Memory, and More

## Table of Contents
## Table of Contents
1. [What is .NET?](#1-what-is-net)
2. [Common Language Runtime (CLR)](#2-can-you-explain-the-common-language-runtime-clr)
3. [Managed vs Unmanaged Code](#3-what-is-the-difference-between-managed-and-unmanaged-code)
4. [Value Types and Reference Types in C#](#4-what-are-value-types-and-reference-types-in-c)
    - [Value Types](#value-types)
    - [Reference Types](#reference-types)
5. [Garbage Collection in .NET](#5-what-is-garbage-collection-in-net)
6. [Exception Handling in C#](#6-explain-the-concept-of-exception-handling-in-c)
7. [Types of Classes in C#](#7-what-are-the-different-types-of-classes-in-c)
8. [Namespace in C#](#8-can-you-describe-what-a-namespace-is-and-how-it-is-used-in-c)
9. [Encapsulation](#9-what-is-encapsulation)
10. [Polymorphism and Its Types in C#](#10-explain-polymorphism-and-its-types-in-c)
11. [Delegates and Their Usage](#11-what-are-delegates-and-how-are-they-used-in-c)
12. [LINQ and Its Usage](#12-describe-what-linq-is-and-give-an-example-of-where-it-might-be-used)
13. [Abstract Class vs Interface](#13-what-is-the-difference-between-an-abstract-class-and-an-interface)
14. [Memory Management in .NET](#14-how-do-you-manage-memory-in-net-applications)
15. [Threading in .NET](#15-explain-the-concept-of-threading-in-net)
16. [Async/Await in C#](#16-what-is-asyncawait-and-how-does-it-work)
17. [Entity Framework](#17-describe-the-entity-framework-and-its-advantages)
18. [Extension Methods in C#](#18-what-are-extension-methods-and-where-would-you-use-them)
19. [How do you handle exceptions in a method that returns a Task?](#19-how-do-you-handle-exceptions-in-a-method-that-returns-a-task)
20. [What is reflection in .NET and how would you use it?](#20-what-is-reflection-in-net-and-how-would-you-use-it)
21. [Can you explain the concept of middleware in ASP.NET Core?](#21-can-you-explain-the-concept-of-middleware-in-aspnet-core)
22. [Describe the Dependency Injection (DI) pattern and how it's implemented in .NET Core.](#22-describe-the-dependency-injection-di-pattern-and-how-its-implemented-in-net-core)
23. [What are Service Lifetimes in .NET Core?](#23-what-are-service-lifetimes-in-net-core)
24. [How does garbage collection work in .NET and how can you optimize it?](#24-how-does-garbage-collection-work-in-net-and-how-can-you-optimize-it)
25. [Can you describe the process of code compilation in .NET?](#25-can-you-describe-the-process-of-code-compilation-in-net)
26. [What is the Global Assembly Cache (GAC) and when should it be used?](#26-what-is-the-global-assembly-cache-gac-and-when-should-it-be-used)
27. [How would you secure a web application in ASP.NET Core?](#27-how-would-you-secure-a-web-application-in-aspnet-core)
28. [What is MVC (Model-View-Controller)?](#28-what-is-mvc-model-view-controller)
29. [Can you explain the difference between Razor Pages and MVC in ASP.NET Core?](#29-can-you-explain-the-difference-between-razor-pages-and-mvc-in-aspnet-core)
30. [How do you perform validations in ASP.NET Core?](#30-how-do-you-perform-validations-in-aspnet-core)
31. [Describe SignalR and its use cases.](#31-describe-signalr-and-its-use-cases)
32. [What is Routing in ASP.NET Core?](#32-what-is-routing-in-aspnet-core)
33. [What is Minimal API in ASP.NET Core?](#33-what-is-minimal-api-in-aspnet-core)
34. [What is async/await?](#34-what-is-asyncawait)
35. [Why API Versioning? Strategies and Implementation](#35-why-api-versioning-strategies-and-implementation)

## 1. What is .NET?
**Answer:**  
.NET is a comprehensive development platform used for building a wide variety of applications, including web, mobile, desktop, and gaming. It supports multiple programming languages, such as C#, F#, and Visual Basic.  
.NET provides a large class library called Framework Class Library (FCL) and runs on a Common Language Runtime (CLR) which offers services like memory management, security, and exception handling.

---

## 2. Can you explain the Common Language Runtime (CLR)?
**Answer:**  
The CLR is a virtual machine component of the .NET framework that manages the execution of .NET programs.  
It provides important services such as memory management, type safety, exception handling, garbage collection, and thread management.  
The CLR converts Intermediate Language (IL) code into native machine code through a process called **Just-In-Time (JIT)** compilation.  
This ensures that .NET applications can run on any device or platform that supports the .NET framework.

---

## 3. What is the difference between managed and unmanaged code?
**Answer:**  
Managed code is executed by the CLR, which provides services like garbage collection, exception handling, and type checking.  
It's called **"managed"** because the CLR handles functionalities that developers would otherwise need to implement themselves.  
Unmanaged code, on the other hand, is executed directly by the operating system, and all memory allocation, type safety, and security must be handled by the programmer.  
Examples of unmanaged code include applications written in **C** or **C++**.

---

## 4. What are Value Types and Reference Types in C#?

In C#, data types are divided into two categories: **Value Types** and **Reference Types**. This distinction affects how values are stored and manipulated within memory.

### Value Types

- **Storage:** Store data directly and are allocated on the stack.
- **Assignment:** When you assign one value type to another, a direct copy of the value is created.
- **Examples:** Basic data types (`int`, `double`, `bool`, etc.) and `structs`.
- **Performance:** Operations on value types are generally faster due to stack allocation.

**Example:**
```csharp
int a = 10;
int b = a;
b = 20;
Console.WriteLine(a); // Output: 10
Console.WriteLine(b); // Output: 20
```
Changing `b` does not affect `a` because `b` is a separate copy.

---

### Reference Types

- **Storage:** Store a reference (pointer) to the actual data, which is allocated on the heap.
- **Assignment:** When you assign one reference type to another, both refer to the same object in memory. Changes made through one reference affect the other.
- **Examples:** Classes, arrays, delegates, and strings.
- **Behavior:** Changes made via one reference are visible through any other reference to the same object.

**Example:**
```csharp
var list1 = new List<int> { 1, 2, 3 };
var list2 = list1;
list2.Add(4);
Console.WriteLine(list1.Count); // Output: 4
Console.WriteLine(list2.Count); // Output: 4
```
`list2` is another reference to the same list object as `list1`; changes made via `list2` are reflected in `list1`.

---

## 5. What is Garbage Collection in .NET?

**Garbage Collection (GC)** in .NET is an automatic memory management feature that frees up memory used by objects that are no longer accessible. Key points include:

- **Purpose:** Eliminates the need for manual memory release, helping to prevent memory leaks and other memory-related errors.
- **Operation:** The GC runs on a separate thread and performs memory cleanup in three phases:
  1. **Marking:** Identifies which objects in the heap are still in use.
  2. **Relocating:** Updates references to objects that will be compacted.
  3. **Compacting:** Reclaims space from garbage objects and compacts remaining objects to make memory allocation more efficient.

Garbage collection helps .NET developers by automatically managing memory, allowing them to focus more on application logic and less on resource management.

---

## 6. Explain the concept of exception handling in C#

Exception handling in C# is a mechanism to handle runtime errors, allowing a program to continue running or fail gracefully instead of crashing. It is done using the `try`, `catch`, and `finally` blocks. The try block contains code that might throw an exception, catch blocks are used to handle the exception, and the finally block contains code that is executed whether an exception is thrown or not.

```csharp
try {
    // Code that may cause an exception
    int divide = 10 / 0;
}
catch (DivideByZeroException ex) {
    // Code to handle the exception
    Console.WriteLine("Cannot divide by zero. Please try again.");
}
finally {
    // Code that executes after try/catch, regardless of an exception
    Console.WriteLine("Operation completed.");
}
```

---

## 7. What are the different types of classes in C#?

In C#, classes can be categorized based on their functionality and accessibility:

- **Static classes:** Cannot be instantiated and can only contain static members.
- **Sealed classes:** Cannot be inherited from.
- **Abstract classes:** Cannot be instantiated and are meant to be inherited from.
- **Partial classes:** Allow the splitting of a class definition across multiple files.
- **Generic classes:** Allow the definition of classes with placeholders for the type of its fields, methods, parameters, etc.

Each type serves different purposes in the context of object-oriented programming and design patterns.

---

## 8. Can you describe what a namespace is and how it is used in C#?

A namespace in C# is used to organize code into a hierarchical structure. It allows the grouping of logically related classes, structs, interfaces, enums, and delegates. Namespaces help avoid naming conflicts by qualifying the uniqueness of each type.

**Example:**
```csharp
using System;

namespace MyApplication
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("Hello, World!");
        }
    }
}
```
In this example, the `System` namespace is used to access the `Console` class, and `MyApplication` is a custom namespace for organizing the application's code. Namespaces are essential for managing the scope of names in larger programming projects to avoid name collisions.

---

## 9. What is encapsulation?

Encapsulation is a fundamental principle of object-oriented programming (OOP) that involves bundling the data (attributes) and methods (operations) that operate on the data into a single unit, or class, and restricting access to the internals of that class. This is typically achieved through the use of access modifiers such as `private`, `public`, `protected`, and `internal`. Encapsulation helps to protect an object's internal state from unauthorized access and modification by external code, promoting data integrity and security.

Encapsulation allows the internal representation of an object to be hidden from the outside, only allowing access through a public interface. This concept is also known as data hiding.

**Example:**
```csharp
public class Person
{
    private string name; // Private field, encapsulated data

    public string Name // Public property, access to the name field
    {
        get { return name; }
        set { name = value; }
    }

    public Person(string name) // Constructor
    {
        this.name = name;
    }
}

class Program
{
    static void Main(string[] args)
    {
        Person person = new Person("John");
        Console.WriteLine(person.Name); // Accessing name through a public property
    }
}
```
In this example, the `name` field of the `Person` class is encapsulated and only accessible via the `Name` property.

---

## 10. Explain polymorphism and its types in C#

Polymorphism is a core concept in object-oriented programming (OOP) that allows objects to be treated as instances of their parent class rather than their actual derived class. This enables methods to perform different tasks based on the object that invokes them, enhancing flexibility and enabling code reusability. In C#, polymorphism can be implemented in two ways: static (compile-time) polymorphism and dynamic (runtime) polymorphism.

- **Static Polymorphism:** Achieved through method overloading and operator overloading. It allows multiple methods or operators with the same name but different parameters to coexist, with the specific method or operator being invoked determined at compile time based on the arguments passed.

- **Dynamic Polymorphism:** Achieved through method overriding. It allows a method in a derived class to have the same name and signature as a method in its base class, but with different implementation details. The method that gets executed is determined at runtime, depending on the type of the object.

**Example:**
```csharp
// Static Polymorphism (Method Overloading)
public class Calculator
{
    public int Add(int a, int b)
    {
        return a + b;
    }

    public int Add(int a, int b, int c)
    {
        return a + b + c;
    }
}

// Dynamic Polymorphism (Method Overriding)
public class Animal
{
    public virtual void Speak()
    {
        Console.WriteLine("The animal speaks");
    }
}

public class Dog : Animal
{
    public override void Speak()
    {
        Console.WriteLine("Dog barks");
    }
}

class Program
{
    static void Main(string[] args)
    {
        Calculator calc = new Calculator();
        Console.WriteLine(calc.Add(2, 3)); // Calls the first Add method
        Console.WriteLine(calc.Add(2, 3, 4)); // Calls the second Add method

        Animal myAnimal = new Animal();
        myAnimal.Speak(); // Output: The animal speaks

        Dog myDog = new Dog();
        myDog.Speak(); // Output: Dog barks

        Animal mySecondAnimal = new Dog();
        mySecondAnimal.Speak(); // Output: Dog barks
    }
}
```
The Calculator class demonstrates static polymorphism through method overloading, and the Animal/Dog classes illustrate dynamic polymorphism.

---

## 11. What are delegates and how are they used in C#?

Delegates in C# are type-safe function pointers or references to methods with a specific parameter list and return type. They allow methods to be passed as parameters, stored in variables, and returned by other methods, which enables flexible and extensible programming designs such as event handling and callback methods.

**Types of delegates in C#:**
- **Single-cast delegates:** Point to a single method at a time.
- **Multicast delegates:** Can point to multiple methods on a single invocation list.
- **Anonymous methods/Lambda expressions:** Allow inline methods or lambda expressions to be used wherever a delegate is expected.

**Example:**
```csharp
public delegate void Operation(int num);

class Program
{
    static void Main(string[] args)
    {
        Operation op = Double;
        op(5);  // Output: 10

        op = Triple;
        op(5);  // Output: 15

        // Multicast delegate
        op = Double;
        op += Triple; // Combines Double and Triple methods
        op(5);  // Output: 10 followed by 15
    }

    static void Double(int num)
    {
        Console.WriteLine($"{num} * 2 = {num * 2}");
    }

    static void Triple(int num)
    {
        Console.WriteLine($"{num} * 3 = {num * 3}");
    }
}
```

---

## 12. Describe what LINQ is and give an example of where it might be used

LINQ (Language Integrated Query) is a powerful feature in C# that allows developers to write expressive, readable code to query and manipulate data from various sources, such as collections, databases, or XML. LINQ queries are strongly typed, offer compile-time checking, and support IntelliSense.

**Example:**
```csharp
using System;
using System.Linq;
using System.Collections.Generic;

class Program
{
    static void Main(string[] args)
    {
        List<int> numbers = new List<int> { 1, 2, 3, 4, 5, 6, 7, 8, 9, 10 };

        // Use LINQ to find all even numbers
        var evenNumbers = from num in numbers
                          where num % 2 == 0
                          select num;

        Console.WriteLine("Even numbers:");
        foreach (var num in evenNumbers)
        {
            Console.WriteLine(num);
        }
    }
}
```
A LINQ query is used to filter a list of integers, selecting only the even numbers.

---

## 13. What is the difference between an abstract class and an interface?

- **Abstract Class:**
    - Can contain implementation of methods, properties, fields, or events.
    - Can have access modifiers (public, protected, etc.).
    - A class can inherit from only one abstract class.
    - Can contain constructors.
    - Used when shared implementation is needed.

- **Interface:**
    - Cannot contain implementations, only declarations.
    - Members are implicitly public.
    - A class or struct can implement multiple interfaces.
    - Cannot contain fields or constructors.
    - Used to define a contract for classes.

**Example:**
```csharp
public abstract class Animal
{
    public abstract void Eat();
    public void Sleep()
    {
        Console.WriteLine("Sleeping");
    }
}

public interface IMovable
{
    void Move();
}

public class Dog : Animal, IMovable
{
    public override void Eat()
    {
        Console.WriteLine("Dog is eating");
    }

    public void Move()
    {
        Console.WriteLine("Dog is running");
    }
}

class Program
{
    static void Main(string[] args)
    {
        Dog myDog = new Dog();
        myDog.Eat();
        myDog.Sleep();
        myDog.Move();
    }
}
```
In this example, Animal is an abstract class and IMovable is an interface.

---

## 14. How do you manage memory in .NET applications?

Memory management in .NET applications is primarily handled automatically by the Garbage Collector (GC). Key aspects:

- **Garbage Collection:** Automatically reclaims memory occupied by unreachable objects.
- **Dispose Pattern:** Implementing IDisposable interface and Dispose method for cleanup of unmanaged resources.
- **Finalizers:** Defined to perform cleanup operations before an object is collected.
- **Using Statements:** Ensures resources are freed as soon as they are no longer needed.
- **Large Object Heap (LOH) Management:** Large objects are allocated on a separate heap.

**Example:**
```csharp
public class ResourceHolder : IDisposable
{
    private bool disposed = false;

    // Simulate an unmanaged resource.
    IntPtr unmanagedResource = Marshal.AllocHGlobal(100);

    public void Dispose()
    {
        Dispose(true);
        GC.SuppressFinalize(this);
    }

    protected virtual void Dispose(bool disposing)
    {
        if (!disposed)
        {
            if (disposing)
            {
                // Dispose managed resources.
            }

            // Free unmanaged resources
            Marshal.FreeHGlobal(unmanagedResource);
            disposed = true;
        }
    }

    ~ResourceHolder()
    {
        Dispose(false);
    }
}

class Program
{
    static void Main(string[] args)
    {
        using (ResourceHolder holder = new ResourceHolder())
        {
            // Use the resource
        } // Automatic disposal here
    }
}
```

---

## 15. Explain the concept of threading in .NET

Threading in .NET allows for the execution of multiple operations simultaneously within the same process. It enables background tasks, UI responsiveness, and parallel computations.

- **System.Threading.Thread:** Low-level approach for direct thread management.
- **ThreadPool:** Collection of worker threads for execution of background tasks.
- **Task Parallel Library (TPL):** Provides higher-level abstraction using tasks.
- **async and await:** Keywords for simplified asynchronous programming.

**Example:**
```csharp
using System;
using System.Threading;

class Program
{
    static void Main(string[] args)
    {
        Thread thread = new Thread(new ThreadStart(DoWork));
        thread.Start();

        Console.WriteLine("Main thread does some work, then waits.");
        thread.Join();
        Console.WriteLine("Background thread has completed. Main thread ends.");
    }

    static void DoWork()
    {
        Console.WriteLine("Background thread is working.");
        Thread.Sleep(1000);
        Console.WriteLine("Background thread has finished.");
    }
}
```

---

## 16. What is async/await and how does it work?

In C#, async and await simplify asynchronous code, making it readable and maintainable. The async modifier declares that a method is asynchronous, and await pauses the method until the awaited task completes. This approach allows non-blocking operations without complex callback code.

**Example:**
```csharp
using System;
using System.Net.Http;
using System.Threading.Tasks;

class Program
{
    static async Task Main(string[] args)
    {
        string result = await DownloadContentAsync();
        Console.WriteLine(result);
    }

    static async Task<string> DownloadContentAsync()
    {
        using HttpClient client = new HttpClient();
        string result = await client.GetStringAsync("http://example.com");
        return result;
    }
}
```
Async/await improves application responsiveness and scalability.

---

## 17. Describe the Entity Framework and its advantages

Entity Framework (EF) is an open-source object-relational mapping (ORM) framework for .NET. Advantages:

- **Increased Productivity:** Generates classes based on database schemas.
- **Maintainability:** Schema changes can be easily propagated through migrations.
- **LINQ Support:** Type-safe queries for data access.
- **Database Agnostic:** Works with various databases via providers.
- **Caching, Lazy Loading, Eager Loading:** Improves performance.

**Example:**
```csharp
using System;
using System.Linq;
using System.Data.Entity;

public class BloggingContext : DbContext
{
    public DbSet<Blog> Blogs { get; set; }
}

public class Blog
{
    public int BlogId { get; set; }
    public string Name { get; set; }
}

class Program
{
    static void Main(string[] args)
    {
        using (var db = new BloggingContext())
        {
            // Create and save a new Blog
            Console.Write("Enter a name for a new Blog: ");
            var name = Console.ReadLine();
            var blog = new Blog { Name = name };
            db.Blogs.Add(blog);
            db.SaveChanges();

            // Display all Blogs from the database
            var query = from b in db.Blogs
                        orderby b.Name
                        select b;

            Console.WriteLine("All blogs in the database:");
            foreach (var item in query)
            {
                Console.WriteLine(item.Name);
            }
        }
    }
}
```

---

## 18. What are extension methods and where would you use them?

Extension methods in C# allow developers to add new methods to existing types without modifying, deriving from, or recompiling the original types. They are static methods in a static class, but called as if they were instance methods on the extended type.

**Advantages:**
- Enhance libraries or built-in .NET types without access to the source code.
- Improve code readability by encapsulating complex operations.
- Facilitate fluent interface style coding.

**Example:**
```csharp
using System;

namespace ExtensionMethods
{
    public static class StringExtensions
    {
        // Extension method for the String class
        public static string ToPascalCase(this string input)
        {
            if (string.IsNullOrEmpty(input))
                return input;

            string[] words = input.Split(new char[] { ' ', '-' }, StringSplitOptions.RemoveEmptyEntries);
            for (int i = 0; i < words.Length; i++)
            {
                words[i] = char.ToUpper(words[i][0]) + words[i].Substring(1).ToLower();
            }
            return string.Join("", words);
        }
    }
}

class Program
{
    static void Main(string[] args)
    {
        string title = "the quick-brown fox";
        string pascalCaseTitle = title.ToPascalCase();
        Console.WriteLine(pascalCaseTitle); // Outputs: TheQuickBrownFox
    }
}
```
Extension methods are a powerful feature for extending the capabilities of types, especially when direct modifications to the class are not possible or desirable.

## 19. How do you handle exceptions in a method that returns a Task?

In asynchronous programming with C#, when a method returns a `Task` or `Task<T>`, exceptions should be handled within the task to avoid unhandled exceptions that can crash the application. Exceptions thrown in a task are captured and placed on the returned task object. You can handle these exceptions using several approaches:

### Inside the Asynchronous Method
Use a try-catch block inside the `async` method to catch exceptions directly.

```csharp
public async Task PerformOperationAsync()
{
    try
    {
        // Async operation that may throw an exception
    }
    catch (Exception ex)
    {
        // Handle exception
    }
}
```

### When Awaiting the Task
Await the task inside a try-catch block to catch exceptions when the task is awaited.

```csharp
try
{
    await PerformOperationAsync();
}
catch (Exception ex)
{
    // Handle exception
}
```

### Using Task.ContinueWith
Use the `ContinueWith` method to attach a continuation task that can handle exceptions.

```csharp
PerformOperationAsync().ContinueWith(task =>
{
    if (task.Exception != null)
    {
        // Handle exception
        var exception = task.Exception.InnerException;
    }
}, TaskContinuationOptions.OnlyOnFaulted);
```

### Using Task.WhenAny
Useful for handling exceptions from multiple tasks.

```csharp
var task = PerformOperationAsync();
await Task.WhenAny(task); // Wait for task to complete

if (task.IsFaulted)
{
    // Handle exception
    var exception = task.Exception.InnerException;
}
```

**Example:**

```csharp
public async Task<int> DivideAsync(int numerator, int denominator)
{
    return await Task.Run(() =>
    {
        if (denominator == 0)
            throw new DivideByZeroException("Denominator cannot be zero.");

        return numerator / denominator;
    });
}

public async Task ExecuteAsync()
{
    try
    {
        int result = await DivideAsync(10, 0);
        Console.WriteLine($"Result: {result}");
    }
    catch (DivideByZeroException ex)
    {
        Console.WriteLine($"Error: {ex.Message}");
    }
}
```

Handling exceptions in tasks is crucial for writing robust and error-resistant asynchronous C# applications, ensuring that your application can gracefully recover from errors encountered during asynchronous operations.

---

## 20. What is reflection in .NET and how would you use it?

Reflection in .NET is a powerful feature that allows runtime inspection of assemblies, types, and their members (such as methods, fields, properties, and events). It enables creating instances of types, invoking methods, and accessing fields and properties dynamically, without knowing the types at compile time. Reflection is used for various purposes, including building type browsers, dynamically invoking methods, and reading custom attributes.

**Common use cases:**
- Dynamically loading and using assemblies.
- Implementing object browsers or debuggers.
- Creating instances of types for dependency injection frameworks.
- Accessing and manipulating metadata for assemblies and types.

**Example:**

```csharp
using System;
using System.Reflection;

public class MyClass
{
    public void MethodToInvoke()
    {
        Console.WriteLine("Method Invoked.");
    }
}

class Program
{
    static void Main(string[] args)
    {
        // Obtaining the Type object for MyClass
        Type myClassType = typeof(MyClass);
        
        // Creating an instance of MyClass
        object myClassInstance = Activator.CreateInstance(myClassType);
        
        // Getting the MethodInfo object for MethodToInvoke
        MethodInfo methodInfo = myClassType.GetMethod("MethodToInvoke");
        
        // Invoking the method on the instance
        methodInfo.Invoke(myClassInstance, null);
    }
}
```

Using reflection comes with a performance cost, so it should be used judiciously, especially in performance-critical paths of an application.

---

## 21. Can you explain the concept of middleware in ASP.NET Core?

Middleware in ASP.NET Core is software that's assembled into an application pipeline to handle requests and responses. Each component in the middleware pipeline is responsible for invoking the next component in the sequence or short-circuiting the chain if necessary. Middleware components can perform a variety of tasks, such as authentication, routing, session management, and logging.

**Key characteristics:**
- Enables custom request/response logic.
- Executed in the order added to the pipeline.
- Can short-circuit the pipeline and prevent downstream middleware from running.

**Example:**

```csharp
public class CustomMiddleware
{
    private readonly RequestDelegate _next;

    public CustomMiddleware(RequestDelegate next)
    {
        _next = next;
    }

    public async Task InvokeAsync(HttpContext context)
    {
        // Do something with the context before the next middleware
        Console.WriteLine("Before next middleware");

        await _next(context); // Call the next middleware in the pipeline

        // Do something with the context after the next middleware
        Console.WriteLine("After next middleware");
    }
}

// Extension method to register middleware
public static class CustomMiddlewareExtensions
{
    public static IApplicationBuilder UseCustomMiddleware(this IApplicationBuilder builder)
    {
        return builder.UseMiddleware<CustomMiddleware>();
    }
}

public class Startup
{
    public void Configure(IApplicationBuilder app)
    {
        app.UseCustomMiddleware();
        // Other middleware registrations
    }
}
```

Middleware components in ASP.NET Core provide a powerful way to compose your application's request-handling pipeline, allowing for modular and reusable components.

---

## 22. Describe the Dependency Injection (DI) pattern and how it's implemented in .NET Core.

**Dependency Injection (DI)** is a design pattern that facilitates loose coupling between software components by removing the direct dependencies among them. Instead of instantiating dependencies directly, components receive their dependencies from an external source (often an inversion of control container). DI makes your code more modular, easier to test, maintain, and extend.

.NET Core has built-in support for dependency injection, which allows services to be registered and resolved through an IoC (Inversion of Control) container. The container manages object creation and injects dependencies where required. This mechanism is central to ASP.NET Core applications.

**Key concepts:**
- **Service registration:** Services are registered with the DI container, typically in `Startup.ConfigureServices`, specifying their lifetime (singleton, scoped, or transient).
- **Service resolution:** Services are resolved either through constructor injection, method call injection, or property injection.

**Example:**

```csharp
public interface IGreetingService
{
    string Greet(string name);
}

public class GreetingService : IGreetingService
{
    public string Greet(string name)
    {
        return $"Hello, {name}!";
    }
}

public class HomeController : Controller
{
    private readonly IGreetingService _greetingService;

    public HomeController(IGreetingService greetingService)
    {
        _greetingService = greetingService;
    }

    public IActionResult Index()
    {
        var greeting = _greetingService.Greet("World");
        return Content(greeting);
    }
}

public class Startup
{
    public void ConfigureServices(IServiceCollection services)
    {
        services.AddControllersWithViews();
        services.AddTransient<IGreetingService, GreetingService>();
    }

    public void Configure(IApplicationBuilder app, IWebHostEnvironment env)
    {
        // Configure the request pipeline.
        app.UseRouting();

        app.UseEndpoints(endpoints =>
        {
            endpoints.MapDefaultControllerRoute();
        });
    }
}
```

DI in .NET Core supports the development of decoupled and easily testable applications.
## 23. What are Service Lifetimes in .NET Core?

In ASP.NET Core, Dependency Injection (DI) controls how and when service instances are created. When you register a service in DI, you specify its *lifetime*—how long the object lives and who shares it.

### The Three Service Lifetimes

| Lifetime   | Created                      | Shared                | Example Use                              |
|------------|-----------------------------|-----------------------|------------------------------------------|
| Transient  | Every time it’s requested   | ❌ No                 | Stateless services (helper, formatter)   |
| Scoped     | Once per HTTP Request        | ✅ Yes (per request)  | Per-request data (DbContext, business)   |
| Singleton  | Once for the entire app      | ✅ Yes (global)       | Logging, configuration, caching          |

#### 1. Transient
- **Meaning:** New instance every time it’s requested (not shared).
- **Registration:**  
  ```csharp
  services.AddTransient<IMyService, MyService>();
  ```
- **Uses:** Lightweight, stateless logic (helpers, converters, formatters).
- **Caution:** For heavy or stateful services, avoid transient.

#### 2. Scoped
- **Meaning:** One instance per HTTP request; shared within that request.
- **Registration:**  
  ```csharp
  services.AddScoped<IOrderService, OrderService>();
  ```
- **Uses:** Data consistency per request (DbContext, repositories).
- **Caution:** Don’t inject a scoped service into a singleton.

#### 3. Singleton
- **Meaning:** Single instance for the whole app; shared across all requests.
- **Registration:**  
  ```csharp
  services.AddSingleton<ILoggingService, LoggingService>();
  ```
- **Uses:** Shared, read-only, thread-safe services (logging, config, cache).
- **Caution:** Must not hold per-user/per-request data.

#### Service Lifetime Example
```csharp
public interface IGuidService { Guid Id { get; } }
public class GuidService : IGuidService
{
    public Guid Id { get; } = Guid.NewGuid();
}

// Register in DI:
builder.Services.AddTransient<IGuidService, GuidService>();
builder.Services.AddScoped<IGuidService, GuidService>();
builder.Services.AddSingleton<IGuidService, GuidService>();
```
Injected in controller:
```csharp
public class TestController : ControllerBase
{
    private readonly IGuidService _service1, _service2;
    public TestController(IGuidService service1, IGuidService service2)
    {
        _service1 = service1;
        _service2 = service2;
    }

    [HttpGet]
    public string Get() => $"Service1: {_service1.Id}\nService2: {_service2.Id}";
}
```
| Lifetime   | Output (same request)  | Output (next request)   |
|------------|------------------------|------------------------|
| Transient  | Different each time    | Different again        |
| Scoped     | Same in request        | New in next request    |
| Singleton  | Same always            | Same for all users     |

---

## 24. How does garbage collection work in .NET and how can you optimize it?

Garbage Collection (GC) in .NET is an automatic process that reclaims memory used by objects no longer accessible, preventing memory leaks.

### How GC Works

- **Mark:** GC identifies all objects reachable from root references; these are marked as “live”.
- **Compact:** Removes unreachable objects, compacts live objects to minimize heap fragmentation.
- **Generations:** GC uses three generations for efficiency:
  - Generation 0: Short-lived (collected most often).
  - Generation 1: Medium-lived.
  - Generation 2: Long-lived/large objects (collected least often).

### Optimizing GC

- **Minimize Allocations:** Avoid unnecessary allocations, especially in loops or performance-critical paths; reuse objects when possible.
- **Understand Generations:** Minimize allocation of large objects (go directly to Gen 2).
- **Use Structs Wisely:** Use small structs for quick stack allocation, but large structs can be inefficient.
- **Implement IDisposable:** Free unmanaged resources with the `IDisposable` pattern.
- **Monitor/Analyze:** Use profiling tools like Visual Studio Diag Tools, dotMemory, and System.GC APIs.

#### Example: Implementing IDisposable
```csharp
public class ResourceWrapper : IDisposable
{
    private bool disposed = false;
    private IntPtr _resource;

    public ResourceWrapper()
    {
        _resource = /* Allocate resource */;
    }

    protected virtual void Dispose(bool disposing)
    {
        if (!disposed)
        {
            if (disposing)
            {
                // Dispose managed resources.
            }
            if (_resource != IntPtr.Zero)
            {
                // Free the unmanaged resource.
                _resource = IntPtr.Zero;
            }
            disposed = true;
        }
    }

    public void Dispose()
    {
        Dispose(true);
        GC.SuppressFinalize(this);
    }

    ~ResourceWrapper()
    {
        Dispose(false);
    }
}
```

---

## 25. Can you describe the process of code compilation in .NET?

Compilation in .NET converts source code (C#, VB, F#) into *Intermediate Language (IL)*, then into platform-specific machine code for execution.

### Steps:

1. **Source to IL:**
   - The language compiler (e.g., csc.exe for C#) translates your code to IL.
   - Metadata describing types, members, references is generated.
2. **IL to Native Code:**
   - The CLR uses the Just-In-Time (JIT) compiler to convert IL to native machine code *at runtime*, when a method is first called.
   - Native code is cached; subsequent calls skip JIT.
3. **Execution:**
   - The native code runs directly on hardware.

### Concepts

- **Assemblies:** Compiled units (.dll/.exe) with IL and metadata; building blocks for deployment/versioning.
- **Metadata:** Describes all types, methods, used for reflection and execution.
- **Strong Naming & GAC:** Assemblies can be strong-named (unique, secure) for sharing in the Global Assembly Cache (GAC).
- **Optimizations & NGEN:** JIT optimizations; the Native Image Generator (NGEN) can pre-compile assemblies to native code for faster starts.

#### Example
```csharp
public class Program
{
    public static void Main(string[] args)
    {
        Console.WriteLine("Hello, World!");
    }
}
```
This code is compiled to IL (.exe/.dll) and JIT-compiled to native code at runtime.

---

## 26. What is the Global Assembly Cache (GAC) and when should it be used?

The **Global Assembly Cache (GAC)** is a machine-wide code cache for the .NET Framework (not .NET Core). It stores *strong-named* assemblies so they can be shared by multiple apps.

### Key Points

- **Sharing Assemblies:** Allows apps to use the same library (memory & consistency).
- **Strong Naming:** Assemblies in GAC must have a strong name (identity, versioning, security).
- **Versioning:** Supports side-by-side multiple versions.

### When to Use

- For libraries shared by many apps on a machine.
- To manage complex versioning.
- To secure common libraries at the admin/system level.

#### Example: Add to GAC
```sh
gacutil -i MyAssembly.dll
```

**Note:** Modern .NET (Core, 5+) apps use NuGet and local dependencies, *not* the GAC.

---

## 27. How would you secure a web application in ASP.NET Core?

Securing ASP.NET Core web apps involves **authentication, authorization, data protection, and enforcing HTTPS**.

### Example: Enforcing HTTPS & Middleware

```csharp
public void Configure(IApplicationBuilder app, IWebHostEnvironment env)
{
    app.UseHttpsRedirection();   // Redirect to HTTPS
    app.UseAuthentication();     // Enable authentication middleware
    app.UseAuthorization();      // Enable authorization middleware
}
```

- **Authentication:** User identity (cookies, JWT, OAuth).
- **Authorization:** Control what users can do.
- **Data Protection:** Secure cookies, tokens, secrets.
- **Enforce HTTPS:** Protect data in transit.

---

## 28. What is MVC (Model-View-Controller)?

**MVC** is a pattern that splits apps into:
- **Model:** Data & logic.
- **View:** User interface.
- **Controller:** Handles input, manages models/views.

#### Example: MVC Controller
```csharp
public class HomeController : Controller
{
    public IActionResult Index()
    {
        return View();
    }
}
```

---

## 29. Can you explain the difference between Razor Pages and MVC in ASP.NET Core?

- **MVC** uses controllers and views; best for complex apps with reusable logic and views.
- **Razor Pages** use page handlers (`OnGet`, `OnPost`...)—great for simple, page-focused apps.

#### Example: Razor Page Handler
```csharp
public class IndexModel : PageModel
{
    public void OnGet()
    {
        // Handle GET request
    }
}
```

---

## 30. How do you perform validations in ASP.NET Core?

Validation uses **Data Annotations** or **Fluent Validation**.

### Example: Data Annotations
```csharp
public class UserModel
{
    [Required]
    [EmailAddress]
    public string Email { get; set; }

    [Required]
    [MinLength(6)]
    public string Password { get; set; }
}
```
- `[Required]`, `[EmailAddress]`, etc. validate input.
- Server- and client-side validation is supported.

---

## 31. Describe SignalR and its use cases.

**SignalR** is a library for real-time web communication—push updates instantly to clients (chat, notifications, live dashboards).

#### Example: SignalR Hub
```csharp
public class ChatHub : Hub
{
    public async Task SendMessage(string user, string message)
    {
        await Clients.All.SendAsync("ReceiveMessage", user, message);
    }
}
```

**Use Cases:**
- Chat apps
- Live notifications
- Collaborative editing
- Real-time dashboards

## 32. What is Routing in ASP.NET Core?

**Routing** is the process of matching incoming HTTP requests (URL and method) to specific controllers, actions, or endpoints in your ASP.NET Core application.

### How Routing Works
1. Request arrives at the server.
2. Routing middleware checks route patterns.
3. Matches request to defined route.
4. Executes the corresponding controller/action/endpoint.
5. Returns the response.

### Types of Routing

#### A. Convention-based Routing (Traditional)
- Defined in Program.cs / Startup.cs.
- Uses patterns to match URLs to controllers/actions.

**Example:**
```csharp
app.UseRouting();

app.UseEndpoints(endpoints =>
{
    endpoints.MapControllerRoute(
        name: "default",
        pattern: "{controller=Home}/{action=Index}/{id?}");
});
// /Products/Details/5 → ProductsController.Details(5)
// / → HomeController.Index()
```
**Pros:** Centralized, easy for simple apps  
**Cons:** Less control for complex routes.

#### B. Attribute Routing
- Routes defined on controllers/actions using attributes.

**Example:**
```csharp
[Route("products")]
public class ProductsController : Controller
{
    [Route("details/{id}")]
    public IActionResult Details(int id) => Ok($"Product ID: {id}");

    [Route("all")]
    public IActionResult List() => Ok("All products");
}
```
**Pros:** Flexible and readable, custom routes per action  
**Cons:** Can be scattered in large apps.

#### C. Endpoint Routing (ASP.NET Core 3.0+)
- Modern system, unifies convention and attribute routing.
- Allows route-based middleware.

**Example:**
```csharp
var builder = WebApplication.CreateBuilder(args);
var app = builder.Build();

app.MapControllers(); // Enables endpoint routing

app.Run();
```

### Routing Summary Table

| Routing Type         | Where Defined              | Flexibility | Example URL           |
|----------------------|---------------------------|-------------|-----------------------|
| Convention-based     | Program.cs or Startup.cs  | Medium      | /Products/Details/5   |
| Attribute routing    | [Route()] on controllers  | High        | /products/details/5   |
| Endpoint routing     | Unified, modern system    | Very High   | /products/details/5   |

**Key Points:**
- Routing matches requests to endpoints using patterns.
- Convention-based: centralized and pattern-based.
- Attribute routing: flexible, fine-grained.
- Endpoint routing: modern, combines both, supports middleware.

---

## 33. What is Minimal API in ASP.NET Core?

Minimal API is a lightweight way to build HTTP APIs in ASP.NET Core (introduced in .NET 6), without controllers.

- Ideal for small services, microservices, quick prototyping.
- Everything can be in one file (Program.cs), fast and simple.

**Example:**
```csharp
var builder = WebApplication.CreateBuilder(args);
var app = builder.Build();

app.MapGet("/hello", () => "Hello World!");
app.MapGet("/products/{id}", (int id) => $"Product ID: {id}");

app.MapPost("/orders", (Order order) =>
{
    // Save order logic
    return Results.Created($"/orders/{order.Id}", order);
});

app.Run();
```

### Comparison: Minimal API vs Controllers

| Feature           | Minimal API           | Controllers                        |
|-------------------|----------------------|-------------------------------------|
| File structure    | Program.cs           | Controllers, Models, etc.           |
| Boilerplate       | Minimal              | More (attributes, classes)          |
| Features          | Routing, DI, MW      | Full MVC: filters, binding, attrs   |
| Best use case     | Small/micro APIs     | Large, complex APIs                 |
| Endpoint grouping | Limited              | [Route], [ApiController], areas     |
| DI, middleware    | Supported            | Supported                           |

- Use Minimal API for small, focused API services.
- Use Controllers for large/more complex APIs with MVC features.

**Key Takeaways:**  
Minimal API = simple, lightweight, ideal for small services  
Controllers = structured, feature-rich, ideal for larger applications  
Both support DI, middleware, and endpoint routing.

---

## 34. What is async/await?

**async/await** is C# syntax for writing asynchronous code that looks synchronous.

- `async` makes a method asynchronous.
- `await` pauses method execution until the awaited task completes, without blocking the thread.

**Example:**
```csharp
public async Task<string> GetDataAsync()
{
    await Task.Delay(1000); // Simulate delay
    return "Data fetched!";
}
```

- The thread can do other work while waiting.
- Improves scalability for web apps (especially on I/O: DB calls, HTTP, file).

**Why use async/await?**
- Scalability: more concurrent operations, no thread blocking.
- Readability: code looks linear, avoids callbacks and .ContinueWith.

---

## 35. Why API Versioning? Strategies and Implementation

**Why version APIs?**  
APIs evolve; clients may break if APIs change. Versioning allows multiple versions to coexist, with clients choosing what to use.

### Common API Versioning Strategies

#### A. URL Path
Version part of URL:
- **Example:** `GET /api/v1/products`, `GET /api/v2/products`

**Implementation:**
```csharp
[ApiController]
[Route("api/v{version:apiVersion}/[controller]")]
[ApiVersion("1.0")]
public class ProductsController : ControllerBase
{
    [HttpGet]
    public IActionResult GetV1() => Ok("V1 Products");
}

[ApiController]
[Route("api/v{version:apiVersion}/[controller]")]
[ApiVersion("2.0")]
public class ProductsV2Controller : ControllerBase
{
    [HttpGet]
    public IActionResult GetV2() => Ok("V2 Products");
}
```

#### B. Query String
Pass version as query parameter.
- **Example:** `GET /api/products?api-version=1.0`

**Implementation:**
```csharp
services.AddApiVersioning(options =>
{
    options.ApiVersionReader = new QueryStringApiVersionReader("api-version");
});
```

#### C. Header Versioning
Version passed in HTTP header.
- **Example:**  
  Header: x-api-version: 1.0

**Implementation:**
```csharp
services.AddApiVersioning(options =>
{
    options.ApiVersionReader = new HeaderApiVersionReader("x-api-version");
});
```

#### D. Media Type (Content Negotiation)
Version in Accept Header.
- **Example:**  
  `Accept: application/json;v=1.0`

**Implementation:**
```csharp
services.AddApiVersioning(options =>
{
    options.ApiVersionReader = new MediaTypeApiVersionReader("v");
});
```

### Default Configuration

```csharp
services.AddApiVersioning(options =>
{
    options.AssumeDefaultVersionWhenUnspecified = true;
    options.DefaultApiVersion = new ApiVersion(1, 0);
    options.ReportApiVersions = true;
});
```
- `AssumeDefaultVersionWhenUnspecified`: Backward compatibility.
- `ReportApiVersions`: Adds available versions to response headers.

### Strategy Comparison

| Strategy         | Pros               | Cons                | Best Use                    |
|------------------|--------------------|---------------------|-----------------------------|
| URL Path         | Clear, explicit    | URL structure change| Public APIs                 |
| Query String     | Clean URLs         | Less visible        | Internal APIs               |
| Header           | Hidden version     | Harder to test      | SDK/Enterprise clients      |
| Media Type       | Negotiation focus  | More complex        | Multiple formats (JSON/XML) |

### Tips
- Keep old versions active during migration.
- Use ReportApiVersions = true for client info.
- Document using Swagger/OpenAPI with versioning.

---
