# .NET Interview Questions

## 📑 Table of Contents
1. [What is .NET?](#1-what-is-net)
2. [Can you explain the Common Language Runtime (CLR)?](#2-can-you-explain-the-common-language-runtime-clr)
3. [What is the difference between managed and unmanaged code?](#3-what-is-the-difference-between-managed-and-unmanaged-code)

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

### 🏁 End of Document
