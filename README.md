# **Constructors and Destructors in C++**

## **AIM**

Understand and implement the concepts of **constructors** and **destructors** in C++.

## **Software Used**

* Visual Studio Code (VS Code)

---

## **Constructors in C++**

A **constructor** is a special member function of a class that is executed automatically when an object is created. Its main role is to **initialize data members** so that the object starts in a valid state.

### **Key Properties**

* Constructor name must match the class name.
* No return type (not even `void`).
* Called automatically when the object is created.
* Can be **overloaded** with different parameter lists.
* If no constructor is defined, the compiler provides a **default constructor**.

### **Types of Constructors**

1. **Default Constructor**

   * Takes no parameters.
   * Initializes objects with default or user-defined values.

2. **Parameterized Constructor**

   * Accepts parameters to initialize objects with specific values.
   * Allows flexibility during object creation.

3. **Copy Constructor**

   * Creates a new object as a copy of an existing one.
   * Syntax:

     ```cpp
     ClassName (const ClassName &obj) { ... }
     ```
   * Useful in passing/returning objects by value or duplicating objects.

### **Advantages**

* Automatic initialization of objects.
* Improves readability and maintainability.
* Eliminates redundant initialization functions.
* Supports **overloading** for flexible object creation.

### **Limitations**

* Cannot be **virtual**.
* Cannot return values.
* Not inherited (but base constructors can be called in derived classes).
* Cannot be explicitly invoked like a normal function.

---

## **Destructors in C++**

A **destructor** is a special member function that is automatically executed when an object goes out of scope or is explicitly deleted.
Its role is to **free resources** (memory, file handles, network connections, etc.).

### **Key Properties**

* Same name as the class, but preceded with a tilde (`~`).
* Takes **no arguments** and returns **no value**.
* Only **one destructor** is allowed per class (cannot be overloaded).
* Called automatically in the **reverse order** of object creation.

### **Uses**

* Free dynamically allocated memory.
* Close files or release network connections.
* Release locks or synchronization primitives.
* Print debug/logging information.

### **Advantages**

* Automatic cleanup (memory, files, resources).
* Simplifies code (no need for explicit cleanup calls).
* Improves stability (prevents memory leaks).
* Encapsulates cleanup logic inside the class.

### **Limitations**

* Execution order in inheritance may cause issues.
* Cannot be overloaded.
* Destructor order for global/static objects across multiple files is undefined.
* Should not throw exceptions (unsafe).
* May cause performance overhead if heavy cleanup is required.

---

## **Programs and Algorithms**

### **1. Constructor Inside the Class**

**Summary:** Demonstrates a constructor defined inside the class for initializing student details.

**Algorithm:**

```
1. Start
2. Define class Student with private members
3. Create constructor inside the class → initializes details
4. Create display() to show details
5. In main(), create object → constructor called automatically
6. Call display()
7. End
```

---

### **2. Constructor Outside the Class**

**Summary:** Constructor declared inside the class but defined outside using the scope resolution operator.

**Algorithm:**

```
1. Start
2. Declare class Student with constructor prototype and display()
3. Define constructor outside class
4. Take input inside constructor
5. In main(), create object → constructor invoked
6. Call display()
7. End
```

---

### **3. Parameterized Constructor**

**Summary:** Initializes objects with specific values at creation.

**Algorithm:**

```
1. Start
2. Define class Practice with data members
3. Define constructor with parameters (m, n)
4. Assign values inside constructor
5. Define display() to show values
6. In main(), create object with arguments
7. Call display()
8. End
```

---

### **4. Copy Constructor (Student Example)**

**Summary:** Copies attributes of one student object into another.

**Algorithm:**

```
1. Start
2. Define class Student with name and age
3. Define parameterized constructor
4. Define copy constructor → copies details, prints message
5. Create object s1 using parameterized constructor
6. Create object s2 as a copy of s1 → copy constructor called
7. Display both objects
8. End
```

---

### **5. Copy Constructor (Car Example)**

**Summary:** Copies car details into another object, printing a custom message when invoked.

**Algorithm:**

```
1. Start
2. Define class Car with attributes
3. Define parameterized constructor
4. Define copy constructor → copy values, print message
5. Create object c1 with parameterized constructor
6. Create object copyC(c1) → invokes copy constructor
7. Display details of both objects
8. End
```

---

### **6. Destructor (Date Example)**

**Summary:** Shows destructor calls when objects go out of scope.

**Algorithm:**

```
1. Start
2. Define class Date with destructor ~Date()
3. In main(), create objects of Date
4. Use loop/block to create temporary objects
5. Destructor automatically invoked when objects go out of scope
6. End
```

---

### **7. Destructor (Object Counter Example)**

**Summary:** Tracks object creation and destruction using a counter.

**Algorithm:**

```
1. Start
2. Define class with constructor and destructor
3. Increment count in constructor, decrement in destructor
4. In main(), create multiple objects
5. Create block scope → observe destructor call for objects leaving scope
6. End
```

---

## **Final Conclusion**

* **Constructors** automate object initialization, supporting default, parameterized, and copy variations.
* **Destructors** handle automatic cleanup, ensuring resources are released properly.
* Together, they provide **robust lifecycle management** for objects in C++.
* These concepts form the **foundation of Object-Oriented Programming (OOP)** in C++, ensuring cleaner, safer, and more efficient code.

