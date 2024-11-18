# C#
Here’s a detailed explanation of the **C# basics**, advantages, structure, and core concepts mentioned:

---

### **Basics**

#### **Console Application**  
A console application is a program that runs in a command-line interface (CLI) or terminal. It allows for simple input/output interactions and is often used to learn the basics of a language.  
- **Example**:  
  ```csharp
  using System;

  class Program
  {
      static void Main(string[] args)
      {
          Console.WriteLine("Hello, World!");
      }
  }
  ```

#### **Case Sensitivity**  
C# is a case-sensitive language. This means that `myVariable` and `MyVariable` are treated as distinct identifiers.  
- **Example**:  
  ```csharp
  int value = 10;
  int Value = 20;
  Console.WriteLine(value); // Outputs: 10
  Console.WriteLine(Value); // Outputs: 20
  ```

---

### **Advantages**

#### **1. Platform Independence**  
- With the .NET Core runtime, C# applications can run on multiple platforms such as Windows, macOS, and Linux.
- Applications can also run in the cloud with .NET.

#### **2. Multithreading**  
- C# supports multithreading, allowing programs to perform multiple tasks simultaneously.
- **Example**: Using `System.Threading` to create threads.

#### **3. Simple to Learn**  
- C# has a clean and intuitive syntax, making it easy for beginners.
- It also offers extensive documentation and tooling support in Visual Studio.

---

### **Structure or Flow of a C# Program**

#### **1. Imports (Libraries)**  
Libraries (namespaces) are imported at the top of the program using the `using` keyword to provide access to predefined classes and methods.  
- **Example**: `using System;` provides access to classes like `Console`.

#### **2. Namespace**  
Namespaces are containers that organize classes and avoid name conflicts.  
- **Example**:  
  ```csharp
  namespace MyApp
  {
      class Program { }
  }
  ```

#### **3. Class**  
A C# program consists of one or more classes, which are building blocks that contain methods and data members.  

#### **4. Main Method**  
The `Main` method is the entry point of a C# application. It’s where the program starts execution.  
- **Example**:  
  ```csharp
  static void Main(string[] args) { }
  ```

---

### **Data Members**

#### **1. Pre-defined**  
These are built-in data members provided by C# (e.g., `int`, `string`, `float`).  
- **Example**:  
  ```csharp
  int number = 10;
  ```

#### **2. User-defined**  
These are created by the programmer, such as custom objects or classes.  
- **Example**:  
  ```csharp
  class Employee
  {
      public string Name;
  }
  ```

#### **3. Pointers**  
Pointers store memory addresses and are used in unsafe contexts.  
- **Example** (Advanced):  
  ```csharp
  unsafe
  {
      int x = 10;
      int* p = &x;
      Console.WriteLine((int)p);
  }
  ```

---

### **Console Methods**

#### **1. Write**  
Outputs text to the console without a new line.  
- **Example**:  
  ```csharp
  Console.Write("Hello");
  Console.Write("World");
  // Output: HelloWorld
  ```

#### **2. WriteLine**  
Outputs text followed by a new line.  
- **Example**:  
  ```csharp
  Console.WriteLine("Hello");
  Console.WriteLine("World");
  ```

#### **3. Read**  
Reads the next character from the input.  
- **Example**:  
  ```csharp
  int value = Console.Read();
  ```

#### **4. ReadLine**  
Reads a line of text from the input.  
- **Example**:  
  ```csharp
  string input = Console.ReadLine();
  ```

#### **5. ReadKey**  
Captures a single key press.  
- **Example**:  
  ```csharp
  ConsoleKeyInfo key = Console.ReadKey();
  Console.WriteLine($"\nYou pressed: {key.KeyChar}");
  ```

#### **6. Clear**  
Clears the console window.  
- **Example**:  
  ```csharp
  Console.Clear();
  ```

---

### **Constructor**  
A constructor is a special method used to initialize objects of a class. It has the same name as the class and no return type.  
- **Example**:  
  ```csharp
  class Person
  {
      public string Name;

      // Constructor
      public Person(string name)
      {
          Name = name;
      }
  }

  Person p = new Person("John");
  Console.WriteLine(p.Name); // Outputs: John
  ```

---

### **Variable**

#### **Definition**  
A variable is a storage location identified by a name that holds data.

#### **Types of Variables**
1. **Static Variables**  
   Shared among all instances of a class.
   ```csharp
   class MyClass
   {
       public static int Count = 0;
   }
   ```

2. **Instance Variables**  
   Unique to each object of a class.
   ```csharp
   class MyClass
   {
       public int InstanceValue;
   }
   ```

3. **Const Variables**  
   Cannot be changed after being initialized.  
   ```csharp
   const double Pi = 3.14;
   ```

4. **Readonly Variables**  
   Can be assigned only once, typically in the constructor.  
   ```csharp
   readonly int Year = 2024;
   ```

--- 

Would you like practical examples or tasks for hands-on practice?
