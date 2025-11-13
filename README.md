# .NET Interview Questions

## 📑 Table of Contents
1. [What is .NET?](#1-what-is-net)
2. [Can you explain the Common Language Runtime (CLR)?](#2-can-you-explain-the-common-language-runtime-clr)
3. [What is the difference between managed and unmanaged code?](#3-what-is-the-difference-between-managed-and-unmanaged-code)
4. [Value Types and Reference Types in C#](#5-what-are-value-types-and-reference-types-in-c)
    - [Value Types](#value-types)
    - [Reference Types](#reference-types)
5. [Garbage Collection in .NET](#6-what-is-garbage-collection-in-net)

---

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
# C# Basics: Value Types, Reference Types, and Garbage Collection

## 4. What are Value Types and Reference Types in C#?

In C#, data types are divided into two categories: **Value Types** and **Reference Types**. This distinction affects how values are stored and manipulated within memory.

### Value Types

- **Storage:** Store data directly and are allocated on the stack.
- **Assignment:** When you assign one value type to another, a direct copy of the value is created.
- **Examples:** Basic data types (`int`, `double`, `bool`, etc.) and `structs`.
- **Performance:** Operations on value types are generally faster due to stack allocation.

**Example:**
```csharp
// Value type example
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
// Reference type example
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


### 🏁 End of Document
