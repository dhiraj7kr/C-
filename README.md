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
 Here is an example of a **basic C# program structure** with all the essential elements including imports, namespace, class, and method. This example will provide the starting skeleton for any C# program:

```csharp
// Importing necessary namespaces
using System;

// Defining a namespace for the program
namespace BasicProgramStructure
{
    // Defining a class
    class Program
    {
        // The Main method - entry point of the program
        static void Main(string[] args)
        {
            // Printing a simple message to the console
            Console.WriteLine("Hello, World!");

            // Calling another method
            GreetUser("John");
        }

        // A custom method that accepts a string parameter and prints a greeting message
        static void GreetUser(string name)
        {
            Console.WriteLine("Hello, " + name + "!");
        }
    }
}
```

---

### **Explanation:**

1. **Imports (`using` statements)**:
   - `using System;` is used to include the **System namespace**, which contains essential classes like `Console` for input/output operations.
   - Additional `using` statements can be added if needed for other libraries.

2. **Namespace (`namespace`)**:
   - A **namespace** is a container for classes and other types, helping to organize code and avoid naming conflicts. In this example, `BasicProgramStructure` is the namespace that wraps the program.

3. **Class (`class`)**:
   - A **class** is the blueprint for creating objects (though we don't use objects here, it is still necessary for code organization). `Program` is the class that contains the methods.

4. **Main Method (`Main`)**:
   - The **Main method** is the entry point of any C# program. It's where the execution starts.
   - The `static` keyword means this method belongs to the class itself rather than an instance of the class.
   - The `void` keyword indicates that this method does not return any value.
   - `string[] args` is a parameter that can hold command-line arguments when the program starts (though not used here).

5. **Custom Method (`GreetUser`)**:
   - A simple **custom method** is defined outside the `Main` method. It takes a `string` argument (the user's name) and prints a personalized greeting.
   - `static` means that this method belongs to the `Program` class itself, not to any object created from the `Program` class.

---

### **Output Example:**
When you run the program, the console will display:
```
Hello, World!
Hello, John!
```

This structure is the foundation for most C# programs and can be expanded as you add more classes, methods, and logic to your application.

---

### **Data Members in C#: Pre-defined, User-defined, and Pointers**

Data members are variables or references declared inside a class or structure that store data. In C#, these can be categorized into **pre-defined**, **user-defined**, and **pointers**.

---

### **1. Pre-defined Data Members**

#### **Explanation**  
- These are variables that use C#'s built-in data types.
- Pre-defined data types include primitives like `int`, `float`, `bool`, `string`, etc., which are part of the .NET framework.
- They provide basic functionality for common operations and memory-efficient storage.

#### **Example**  
```csharp
class Demo
{
    public int number;      // Integer (whole numbers)
    public float price;     // Floating-point (decimals)
    public bool isActive;   // Boolean (true/false)
    public string message;  // String (text data)
}

class Program
{
    static void Main(string[] args)
    {
        Demo obj = new Demo();
        obj.number = 100;
        obj.price = 12.99f;
        obj.isActive = true;
        obj.message = "Hello, World!";
        
        Console.WriteLine($"Number: {obj.number}");
        Console.WriteLine($"Price: {obj.price}");
        Console.WriteLine($"Is Active: {obj.isActive}");
        Console.WriteLine($"Message: {obj.message}");
    }
}
```

#### **Key Characteristics**
- Part of the **System** namespace.
- No custom behavior, only basic storage.

---

### **2. User-defined Data Members**

#### **Explanation**  
- These are variables that are **custom objects or structures** created by the programmer.
- You can define your own class or struct to represent specific types of data.
- They allow for more complex and domain-specific behavior.

#### **Example**  
```csharp
class Employee
{
    public int ID;              // User-defined data member
    public string Name;         // User-defined data member
    public string Department;   // User-defined data member
}

class Program
{
    static void Main(string[] args)
    {
        Employee emp = new Employee();
        emp.ID = 101;
        emp.Name = "John Doe";
        emp.Department = "IT";

        Console.WriteLine($"Employee ID: {emp.ID}");
        Console.WriteLine($"Name: {emp.Name}");
        Console.WriteLine($"Department: {emp.Department}");
    }
}
```

#### **Key Characteristics**
- Defined by the user for specific needs.
- May include additional functionality (methods, constructors).
- Enables reuse and modularity.

---

### **3. Pointers**

#### **Explanation**  
- Pointers store the **memory address** of another variable. They are used in **unsafe** code blocks in C#.
- Pointers are less commonly used in C# because managed code (using garbage collection) is the default, and pointers can bypass safety.
- You must enable `unsafe` code to use pointers.

#### **Syntax for Pointer**
- Use the `*` operator to declare a pointer.
- Use the `&` operator to get the address of a variable.
- Use the `->` operator for accessing members via a pointer.

#### **Example**  
```csharp
using System;

class Program
{
    unsafe static void Main(string[] args)
    {
        int num = 100;
        int* ptr = &num; // Pointer to the address of num

        Console.WriteLine($"Value: {num}");
        Console.WriteLine($"Address: {(long)ptr}"); // Prints memory address
        Console.WriteLine($"Value via Pointer: {*ptr}"); // Access value via pointer
    }
}
```

#### **Key Characteristics**
- Must use the `unsafe` keyword.
- Provides low-level memory control.
- Rarely used in managed environments but useful for scenarios like hardware-level programming.

---

### **Differences Between Pre-defined, User-defined, and Pointers**

| Feature                | Pre-defined Data Members           | User-defined Data Members          | Pointers                          |
|------------------------|------------------------------------|------------------------------------|-----------------------------------|
| **Definition**          | Built-in data types like `int`, `float`, `string`. | Custom objects/classes/structs defined by the user. | Memory addresses pointing to variables. |
| **Complexity**          | Simple and lightweight.            | More complex, can include behavior (methods). | Low-level programming, unsafe context required. |
| **Use Case**            | Storing basic data.                | Representing domain-specific data structures. | Special scenarios like direct memory access. |
| **Memory Control**      | Managed by C# runtime.             | Managed by C# runtime.             | Direct, manual memory handling.  |
| **Example Usage**       | `int age = 25;`                   | `Employee emp = new Employee();`  | `int* p = &age;`                 |

---



### **Console Methods**

### **Console in C#**

The `Console` class in C# provides methods for input and output operations in console applications. It belongs to the `System` namespace. Below is a detailed explanation of the common `Console` methods:

---

### **1. `Write`**
- **Purpose**: Outputs text to the console without appending a new line at the end. The cursor remains on the same line.
- **Usage**: Often used for inline outputs where a newline is not required.

#### **Example**:
```csharp
Console.Write("Enter your name: ");
string name = Console.ReadLine();
Console.Write("Hello ");
Console.Write(name); // Cursor stays on the same line
```

**Output**:
```
Enter your name: John
Hello John
```

---

### **2. `WriteLine`**
- **Purpose**: Outputs text to the console and appends a new line. The cursor moves to the next line after printing.
- **Usage**: Preferred for outputs that need to appear line by line.

#### **Example**:
```csharp
Console.WriteLine("Welcome to C# programming!");
Console.WriteLine("This is the next line.");
```

**Output**:
```
Welcome to C# programming!
This is the next line.
```

---

### **3. `Read`**
- **Purpose**: Reads the next character from the input buffer (keyboard input).
- **Usage**: Typically used when only a single character needs to be captured.

#### **Example**:
```csharp
Console.Write("Press any key: ");
int charValue = Console.Read(); // Reads a single character as its ASCII value
Console.WriteLine($"\nYou pressed: {(char)charValue}");
```

**Output**:
```
Press any key: A
You pressed: A
```

---

### **4. `ReadLine`**
- **Purpose**: Reads a line of input from the console until the Enter key is pressed.
- **Usage**: Commonly used to capture string or numeric inputs.

#### **Example**:
```csharp
Console.Write("Enter your age: ");
string age = Console.ReadLine(); // Reads the entire input line
Console.WriteLine($"You entered: {age}");
```

**Output**:
```
Enter your age: 25
You entered: 25
```

---

### **5. `ReadKey`**
- **Purpose**: Captures a single key press from the user without waiting for the Enter key.
- **Usage**: Useful for navigation or capturing user input in interactive applications.

#### **Example**:
```csharp
Console.Write("Press any key to continue...");
ConsoleKeyInfo keyInfo = Console.ReadKey(); // Captures the key pressed
Console.WriteLine($"\nYou pressed: {keyInfo.Key}");
```

**Output**:
```
Press any key to continue... (User presses 'Enter')
You pressed: Enter
```

---

### **6. `Clear`**
- **Purpose**: Clears all content displayed in the console window.
- **Usage**: Useful to reset the console screen during execution.

#### **Example**:
```csharp
Console.WriteLine("This message will be cleared...");
Console.Clear(); // Clears the console screen
Console.WriteLine("Console is now cleared!");
```

**Output**:
```
This message will be cleared...
Console is now cleared!
```

---

### **Other Useful `Console` Methods**

#### **7. `Beep`**
- **Purpose**: Produces a beep sound through the system speaker.
- **Usage**: Often used for notifications or warnings.
- **Example**:
  ```csharp
  Console.Beep(); // Default beep sound
  ```

#### **8. `SetCursorPosition`**
- **Purpose**: Sets the position of the cursor in the console window.
- **Usage**: Useful for creating custom layouts in console applications.
- **Example**:
  ```csharp
  Console.SetCursorPosition(10, 5); // Moves the cursor to column 10, row 5
  Console.WriteLine("Cursor moved here!");
  ```

#### **9. `BackgroundColor` and `ForegroundColor`**
- **Purpose**: Changes the background or text color in the console.
- **Usage**: Used to enhance the appearance of console applications.
- **Example**:
  ```csharp
  Console.BackgroundColor = ConsoleColor.Blue;
  Console.ForegroundColor = ConsoleColor.White;
  Console.Clear(); // Apply background color to the entire console
  Console.WriteLine("Text with a blue background!");
  Console.ResetColor(); // Reset to default colors
  ```

#### **10. `Title`**
- **Purpose**: Sets the title of the console window.
- **Example**:
  ```csharp
  Console.Title = "My Console Application";
  ```

#### **11. `WindowHeight` and `WindowWidth`**
- **Purpose**: Adjust the size of the console window.
- **Example**:
  ```csharp
  Console.WindowHeight = 30;
  Console.WindowWidth = 80;
  ```

#### **12. `Error`**
- **Purpose**: Writes text to the standard error stream.
- **Example**:
  ```csharp
  Console.Error.WriteLine("This is an error message.");
  ```

---

### **Summary Table**

| Method            | Purpose                                                   | Example Usage                           |
|--------------------|-----------------------------------------------------------|-----------------------------------------|
| **Write**          | Writes text without a new line                            | `Console.Write("Text");`                |
| **WriteLine**      | Writes text with a new line                               | `Console.WriteLine("Text");`            |
| **Read**           | Reads a single character (ASCII value)                   | `Console.Read();`                       |
| **ReadLine**       | Reads an entire line of text                              | `Console.ReadLine();`                   |
| **ReadKey**        | Captures a single key press                               | `Console.ReadKey();`                    |
| **Clear**          | Clears the console screen                                 | `Console.Clear();`                      |
| **Beep**           | Produces a beep sound                                     | `Console.Beep();`                       |
| **SetCursorPosition** | Moves the cursor to a specific position                 | `Console.SetCursorPosition(10, 5);`     |
| **BackgroundColor** | Changes console background color                         | `Console.BackgroundColor = ConsoleColor.Blue;` |
| **ForegroundColor** | Changes console text color                               | `Console.ForegroundColor = ConsoleColor.Red;`   |
| **Title**          | Sets the title of the console window                      | `Console.Title = "My App";`             |
| **Error**          | Outputs text to the error stream                          | `Console.Error.WriteLine("Error!");`    |


 

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

### **Types of Variables in C#**

In C#, variables can be categorized based on their behavior and how they are declared. The most common types are **Static**, **Instance**, **Const**, and **Readonly** variables. Below is a detailed explanation of each with examples.

---

### **1. Static Variables**
- **Definition**: 
  - A static variable belongs to the class rather than any object.
  - It is shared among all instances of the class.
  - It retains its value throughout the program's lifetime.

- **Key Features**:
  - Declared using the `static` keyword.
  - Memory is allocated only once at the class level.
  - Can be accessed without creating an instance of the class.

#### **Example**:
```csharp
class Counter
{
    public static int count = 0; // Static variable

    public Counter()
    {
        count++;
    }

    public static void DisplayCount()
    {
        Console.WriteLine($"Total Objects Created: {count}");
    }
}

class Program
{
    static void Main(string[] args)
    {
        Counter obj1 = new Counter();
        Counter obj2 = new Counter();
        Counter obj3 = new Counter();

        // Access static variable using class name
        Counter.DisplayCount();
    }
}
```

**Output**:
```
Total Objects Created: 3
```

---

### **2. Instance Variables**
- **Definition**:
  - An instance variable is unique to each object of the class.
  - Every object maintains its own copy of instance variables.

- **Key Features**:
  - Declared without the `static` keyword.
  - Memory is allocated each time an object is created.
  - Values are specific to the instance of the class.

#### **Example**:
```csharp
class Student
{
    public string name; // Instance variable

    public Student(string studentName)
    {
        name = studentName;
    }

    public void Display()
    {
        Console.WriteLine($"Student Name: {name}");
    }
}

class Program
{
    static void Main(string[] args)
    {
        Student student1 = new Student("Alice");
        Student student2 = new Student("Bob");

        student1.Display(); // Displays Alice
        student2.Display(); // Displays Bob
    }
}
```

**Output**:
```
Student Name: Alice
Student Name: Bob
```

---

### **3. Constant Variables**
- **Definition**:
  - A constant variable's value is set at the time of declaration and cannot be changed.
  - It is implicitly static (can be accessed without creating an object).

- **Key Features**:
  - Declared using the `const` keyword.
  - Value must be assigned during declaration.
  - Cannot be modified during runtime.

#### **Example**:
```csharp
class Circle
{
    public const double Pi = 3.14159; // Constant variable

    public static double CalculateArea(double radius)
    {
        return Pi * radius * radius; // Use of constant
    }
}

class Program
{
    static void Main(string[] args)
    {
        double radius = 5.0;
        double area = Circle.CalculateArea(radius);
        Console.WriteLine($"Area of Circle: {area}");
    }
}
```

**Output**:
```
Area of Circle: 78.53975
```

---

### **4. Readonly Variables**
- **Definition**:
  - A readonly variable's value can be assigned either at the time of declaration or within the constructor.
  - Once assigned, its value cannot be modified.

- **Key Features**:
  - Declared using the `readonly` keyword.
  - Can have different values for different objects.
  - Value cannot be changed after initialization.

#### **Example**:
```csharp
class Product
{
    public readonly string productName; // Readonly variable

    public Product(string name)
    {
        productName = name; // Value assigned in constructor
    }

    public void Display()
    {
        Console.WriteLine($"Product Name: {productName}");
    }
}

class Program
{
    static void Main(string[] args)
    {
        Product product1 = new Product("Laptop");
        Product product2 = new Product("Tablet");

        product1.Display(); // Displays Laptop
        product2.Display(); // Displays Tablet
    }
}
```

**Output**:
```
Product Name: Laptop
Product Name: Tablet
```

---

### **Differences Between Static, Instance, Const, and Readonly**

| Feature            | Static                | Instance               | Const                  | Readonly                 |
|---------------------|-----------------------|------------------------|------------------------|--------------------------|
| **Keyword**         | `static`             | None                  | `const`               | `readonly`              |
| **Scope**           | Class-level          | Object-level           | Class-level           | Object-level            |
| **Initialization**  | At class level       | Per object instance    | At declaration         | At declaration or in constructor |
| **Value Change**    | Can be changed       | Can be changed         | Cannot be changed      | Cannot be changed after initialization |
| **Access**          | ClassName.Variable   | ObjectName.Variable    | ClassName.Variable     | ObjectName.Variable      |
| **Memory**          | Shared across objects| Separate for each object| Shared across objects | Separate for each object |

---

### **Key Points to Remember**
1. Use **static** variables for data that needs to be shared across all instances of a class.
2. Use **instance** variables for data specific to each object.
3. Use **const** for values that will never change and are known at compile time.
4. Use **readonly** when the value can only be set at runtime during object creation or declaration.


### **Constructor in C#**

#### **What is a Constructor?**
- A **constructor** is a special method in a class that is automatically called when an object of the class is created.
- It is primarily used to initialize the object's properties (data members) with default or specific values.
- The name of the constructor **must match the class name**, and it **does not have a return type**, not even `void`.

---

### **Key Characteristics of Constructors**
1. **Automatic Invocation**: Called automatically at the time of object creation.
2. **Same Name as Class**: Its name must be the same as the class it belongs to.
3. **No Return Type**: Constructors do not have a return type.
4. **Can Be Overloaded**: You can define multiple constructors with different parameters (constructor overloading).
5. **Types of Constructors**:
   - Default Constructor
   - Parameterized Constructor
   - Static Constructor
   - Private Constructor
6. **Access Modifiers**: Can have access modifiers (e.g., `public`, `private`, `protected`).

---

### **1. Default Constructor**
A default constructor takes no parameters and initializes fields with default values.

#### **Example**:
```csharp
class Car
{
    public string brand;
    public int year;

    // Default Constructor
    public Car()
    {
        brand = "Unknown";
        year = 0;
    }

    public void Display()
    {
        Console.WriteLine($"Brand: {brand}, Year: {year}");
    }
}

class Program
{
    static void Main(string[] args)
    {
        Car car = new Car(); // Default constructor is called
        car.Display();
    }
}
```

**Output**:
```
Brand: Unknown, Year: 0
```

---

### **2. Parameterized Constructor**
A parameterized constructor allows passing arguments to initialize data members with specific values.

#### **Example**:
```csharp
class Car
{
    public string brand;
    public int year;

    // Parameterized Constructor
    public Car(string brandName, int manufactureYear)
    {
        brand = brandName;
        year = manufactureYear;
    }

    public void Display()
    {
        Console.WriteLine($"Brand: {brand}, Year: {year}");
    }
}

class Program
{
    static void Main(string[] args)
    {
        Car car = new Car("Toyota", 2020); // Parameterized constructor is called
        car.Display();
    }
}
```

**Output**:
```
Brand: Toyota, Year: 2020
```

---

### **3. Static Constructor**
- A static constructor is used to initialize static data members or perform an action only once.
- It is automatically called **before the first instance of the class is created** or any static member is accessed.
- A static constructor cannot have access modifiers or parameters.

#### **Example**:
```csharp
class Car
{
    public static string companyName;

    // Static Constructor
    static Car()
    {
        companyName = "Global Motors";
        Console.WriteLine("Static Constructor Called");
    }

    public static void DisplayCompany()
    {
        Console.WriteLine($"Company: {companyName}");
    }
}

class Program
{
    static void Main(string[] args)
    {
        Car.DisplayCompany(); // Static constructor is invoked
    }
}
```

**Output**:
```
Static Constructor Called
Company: Global Motors
```

---

### **4. Private Constructor**
- A private constructor is used to restrict the creation of objects outside the class.
- Commonly used in **singleton patterns**.

#### **Example**:
```csharp
class Singleton
{
    private static Singleton instance = null;

    // Private Constructor
    private Singleton()
    {
        Console.WriteLine("Singleton Instance Created");
    }

    public static Singleton GetInstance()
    {
        if (instance == null)
        {
            instance = new Singleton();
        }
        return instance;
    }
}

class Program
{
    static void Main(string[] args)
    {
        Singleton obj1 = Singleton.GetInstance();
        Singleton obj2 = Singleton.GetInstance();

        Console.WriteLine(obj1 == obj2); // True, both refer to the same instance
    }
}
```

**Output**:
```
Singleton Instance Created
True
```

---

### **5. Constructor Overloading**
- Constructor overloading allows defining multiple constructors with different parameter lists in the same class.

#### **Example**:
```csharp
class Car
{
    public string brand;
    public int year;

    // Default Constructor
    public Car()
    {
        brand = "Unknown";
        year = 0;
    }

    // Parameterized Constructor
    public Car(string brandName, int manufactureYear)
    {
        brand = brandName;
        year = manufactureYear;
    }

    public void Display()
    {
        Console.WriteLine($"Brand: {brand}, Year: {year}");
    }
}

class Program
{
    static void Main(string[] args)
    {
        Car car1 = new Car(); // Calls default constructor
        Car car2 = new Car("Tesla", 2023); // Calls parameterized constructor

        car1.Display();
        car2.Display();
    }
}
```

**Output**:
```
Brand: Unknown, Year: 0
Brand: Tesla, Year: 2023
```

---

### **Key Points to Remember**
1. **Default Constructor**: Initializes fields with default values if not explicitly assigned.
2. **Parameterized Constructor**: Allows custom initialization by passing arguments.
3. **Static Constructor**: Used for initializing static members; only called once.
4. **Private Constructor**: Restricts object creation; often used for patterns like Singleton.
5. **Overloading**: Enables multiple ways of creating objects based on different initialization needs.

---

### **Example: Class with Object and Constructor**

Here’s a simple example to illustrate how to define a class, create objects, and use constructors in C#:

---

#### **Code Example**:
```csharp
using System;

class Person
{
    // Instance variables (fields)
    public string Name;
    public int Age;

    // Constructor
    public Person(string name, int age)
    {
        // Assign values to instance variables
        Name = name;
        Age = age;
    }

    // Method to display person's details
    public void DisplayDetails()
    {
        Console.WriteLine($"Name: {Name}, Age: {Age}");
    }
}

class Program
{
    static void Main(string[] args)
    {
        // Creating objects using the constructor
        Person person1 = new Person("Alice", 25);
        Person person2 = new Person("Bob", 30);

        // Calling the method to display details
        person1.DisplayDetails();
        person2.DisplayDetails();
    }
}
```

---

#### **Explanation**:

1. **Class Definition**:
   - The `Person` class has two instance variables, `Name` and `Age`, which store the name and age of a person.
   - The class includes a **constructor** (`Person(string name, int age)`) that initializes these variables when an object is created.

2. **Constructor**:
   - The constructor takes two parameters: `name` and `age`.
   - These parameters are assigned to the instance variables `Name` and `Age` using the `this` keyword implicitly.

3. **Object Creation**:
   - Objects `person1` and `person2` are created using the `new` keyword, passing the required arguments to the constructor.

4. **Method**:
   - The `DisplayDetails` method is used to print the details of the person.

---

#### **Output**:
```
Name: Alice, Age: 25
Name: Bob, Age: 30
```

---



