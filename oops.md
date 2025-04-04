
### 1. **Classes and Objects**
   - **Class**: A blueprint or template for creating objects. It defines a datatype by bundling data (variables) and methods (functions) that operate on the data.
     ```java
     class Car {
         String model;
         int year;

         void start() {
             System.out.println("Car started");
         }
     }
     ```
   - **Object**: An instance of a class.
     ```java
     Car myCar = new Car();  // Creating an object of the Car class
     myCar.start();          // Calling the method using the object
     ```

### 2. **Encapsulation**
   - **Encapsulation** refers to the concept of wrapping data (variables) and methods (functions) into a single unit, i.e., a class. It also restricts direct access to some of the object's components and protects the integrity of the data by providing access through getter and setter methods.
   - **Example**: Making variables private and accessing them through public methods.
     ```java
     class Employee {
         private String name;
         private int age;

         public String getName() {
             return name;
         }

         public void setName(String name) {
             this.name = name;
         }

         public int getAge() {
             return age;
         }

         public void setAge(int age) {
             if (age > 0) {
                 this.age = age;
             }
         }
     }
     ```

### 3. **Inheritance**
   - **Inheritance** allows one class to inherit the properties and behaviors (fields and methods) of another class. It promotes code reuse.
   - The class that is inherited from is called the **parent class** or **superclass**, and the class that inherits is called the **child class** or **subclass**.
   - **Example**:
     ```java
     class Animal {
         void eat() {
             System.out.println("Eating...");
         }
     }

     class Dog extends Animal {  // Inheriting from Animal
         void bark() {
             System.out.println("Barking...");
         }
     }

     public class Test {
         public static void main(String[] args) {
             Dog d = new Dog();
             d.eat();  // Inherited method from Animal class
             d.bark(); // Dog-specific method
         }
     }
     ```
   - **Key points**:
     - Java supports **single inheritance**.
     - A subclass can call methods and access fields of the superclass.
     - The **`super`** keyword is used to refer to the superclass methods and constructors.

### 4. **Polymorphism**
   - **Polymorphism** allows one object to take many forms. It enables methods to do different things based on the object it is acting upon.
   - **Types of Polymorphism**:
     - **Compile-time polymorphism** (Method Overloading)
     - **Runtime polymorphism** (Method Overriding)
   
   - **Method Overloading** (Compile-time Polymorphism): Multiple methods with the same name but different parameters.
     ```java
     class MathOperations {
         int add(int a, int b) {
             return a + b;
         }

         double add(double a, double b) {
             return a + b;
         }
     }
     ```

   - **Method Overriding** (Runtime Polymorphism): A subclass provides a specific implementation of a method that is already provided by its superclass.
     ```java
     class Animal {
         void sound() {
             System.out.println("Animal makes sound");
         }
     }

     class Dog extends Animal {
         @Override
         void sound() {
             System.out.println("Dog barks");
         }
     }
     ```

   - **Key points**:
     - **Overloading** occurs at compile-time, and **overriding** occurs at runtime.
     - The `@Override` annotation is used to indicate that a method is overriding a superclass method.

### 5. **Abstraction**
   - **Abstraction** is the concept of hiding the complex implementation details and showing only the necessary features of an object. This is typically achieved using **abstract classes** and **interfaces**.
   - **Abstract Class**: A class that cannot be instantiated but can be subclassed. It can have both abstract (without a body) and concrete methods.
     ```java
     abstract class Animal {
         abstract void sound();  // Abstract method

         void breathe() {        // Concrete method
             System.out.println("Breathing...");
         }
     }

     class Dog extends Animal {
         void sound() {
             System.out.println("Barking...");
         }
     }
     ```

   - **Interface**: An interface is a contract that a class must follow. It only contains abstract methods (prior to Java 8) and constants.
     ```java
     interface Animal {
         void sound();  // Abstract method
     }

     class Dog implements Animal {
         public void sound() {
             System.out.println("Barking...");
         }
     }
     ```

   - **Key points**:
     - Abstract classes can have both abstract and concrete methods.
     - Interfaces can only have abstract methods (except in Java 8 and above, which allow default and static methods).
     - A class can implement multiple interfaces but can inherit only one abstract class.

### 6. **Constructors**
   - A **constructor** is a special method used to initialize objects. It is called when an object of a class is created.
   - **Types**:
     - **Default constructor**: A constructor that doesn’t take any arguments. It is provided by default if no constructors are defined in the class.
     - **Parameterized constructor**: A constructor that takes arguments to initialize an object with specific values.
   - **Example**:
     ```java
     class Car {
         String model;
         int year;

         Car(String model, int year) {
             this.model = model;
             this.year = year;
         }
     }
     ```

### 7. **The `this` Keyword**
   - **`this`** refers to the current object of the class. It is used to:
     - Refer to instance variables.
     - Invoke current class methods.
     - Pass the current object as a parameter to another method.

### 8. **The `super` Keyword**
   - **`super`** refers to the superclass of the current object. It is used to:
     - Call superclass methods.
     - Access superclass constructors.

### Key Interview Tips:
- **Example-driven answers**: Always try to demonstrate your understanding of OOP concepts with simple code examples.
- **Clarify concepts**: Be ready to explain the difference between abstract classes and interfaces, or method overloading vs method overriding.
- **Real-world analogy**: Using real-world analogies can help explain complex OOP concepts easily. For example, you can explain **inheritance** as how a child inherits traits from a parent.

### Detailed Notes on **Inheritance** in Java

Inheritance is one of the core concepts in **Object-Oriented Programming (OOP)**, and it allows a class to inherit properties and behaviors (fields and methods) from another class. In Java, inheritance enables a hierarchical relationship between classes, making code more reusable and extensible.

### **1. What is Inheritance?**
- **Definition**: Inheritance is the mechanism in Java that allows one class (the **child** or **subclass**) to inherit fields and methods from another class (the **parent** or **superclass**).
- **Purpose**: The main advantage of inheritance is **code reuse**. The subclass can reuse the methods and fields defined in the superclass, reducing redundancy.

### **2. Types of Inheritance in Java**
1. **Single Inheritance**:
   - In **single inheritance**, a subclass inherits from only one superclass.
   - Java supports **single inheritance**. This allows a class to inherit properties from one class only.
   - **Example**:
     ```java
     class Animal {
         void eat() {
             System.out.println("Eating...");
         }
     }

     class Dog extends Animal {  // Dog inherits from Animal
         void bark() {
             System.out.println("Barking...");
         }
     }

     public class Test {
         public static void main(String[] args) {
             Dog dog = new Dog();
             dog.eat();   // Inherited from Animal class
             dog.bark();  // Specific to Dog class
         }
     }
     ```
     Here, the **Dog** class inherits the `eat()` method from the **Animal** class.

2. **Multilevel Inheritance**:
   - A form of inheritance where a class inherits from a subclass, creating a chain of inheritance.
   - Java supports multilevel inheritance, but it's important to note that Java does **not support multiple inheritance** (inheriting from more than one class directly).
   - **Example**:
     ```java
     class Animal {
         void eat() {
             System.out.println("Eating...");
         }
     }

     class Dog extends Animal {  // Inheriting Animal
         void bark() {
             System.out.println("Barking...");
         }
     }

     class Puppy extends Dog {  // Inheriting Dog
         void play() {
             System.out.println("Playing...");
         }
     }

     public class Test {
         public static void main(String[] args) {
             Puppy puppy = new Puppy();
             puppy.eat();   // Inherited from Animal
             puppy.bark();  // Inherited from Dog
             puppy.play();  // Specific to Puppy
         }
     }
     ```
     The **Puppy** class inherits from **Dog**, and **Dog** inherits from **Animal**, forming a multilevel inheritance chain.

3. **Hierarchical Inheritance**:
   - A subclass can inherit from multiple classes. While Java doesn't allow multiple inheritance (inheritance from more than one class directly), **hierarchical inheritance** involves one superclass and multiple subclasses.
   - **Example**:
     ```java
     class Animal {
         void eat() {
             System.out.println("Eating...");
         }
     }

     class Dog extends Animal {  // Dog inherits Animal
         void bark() {
             System.out.println("Barking...");
         }
     }

     class Cat extends Animal {  // Cat inherits Animal
         void meow() {
             System.out.println("Meowing...");
         }
     }

     public class Test {
         public static void main(String[] args) {
             Dog dog = new Dog();
             dog.eat();  // Inherited from Animal
             dog.bark();

             Cat cat = new Cat();
             cat.eat();  // Inherited from Animal
             cat.meow();
         }
     }
     ```
     Both **Dog** and **Cat** inherit from the same superclass **Animal**, demonstrating **hierarchical inheritance**.

### **3. Key Terminology in Inheritance**
- **Superclass (Parent Class)**: The class from which properties and methods are inherited.
- **Subclass (Child Class)**: The class that inherits the properties and behaviors of the superclass.
- **`extends` Keyword**: In Java, the `extends` keyword is used to define inheritance. It is used in the subclass to specify the superclass it inherits from.

### **4. Constructor Inheritance**
- Constructors are **not inherited** by subclasses, but the subclass can call the constructor of the superclass using the `super()` keyword.
- **Constructor Chaining**: This is the process of calling a superclass constructor from the subclass constructor.
- **Example**:
  ```java
  class Animal {
      Animal() {
          System.out.println("Animal constructor called");
      }
  }

  class Dog extends Animal {
      Dog() {
          super();  // Calling Animal's constructor
          System.out.println("Dog constructor called");
      }
  }

  public class Test {
      public static void main(String[] args) {
          Dog dog = new Dog();  // Calls both Animal's and Dog's constructors
      }
  }
  ```
  Output:
  ```
  Animal constructor called
  Dog constructor called
  ```

### **5. Overriding Methods in Inheritance**
- **Method Overriding** occurs when a subclass provides a specific implementation for a method that is already defined in its superclass.
- The method in the subclass must have the same signature as the method in the superclass.
- **`@Override` Annotation**: This annotation is used to indicate that a method is being overridden in the subclass.
- **Example**:
  ```java
  class Animal {
      void sound() {
          System.out.println("Animal makes a sound");
      }
  }

  class Dog extends Animal {
      @Override
      void sound() {
          System.out.println("Dog barks");
      }
  }

  public class Test {
      public static void main(String[] args) {
          Animal animal = new Dog();
          animal.sound();  // Calls the Dog's overridden method
      }
  }
  ```
  Here, the `sound()` method is overridden in the **Dog** class, and it outputs "Dog barks".

### **6. The `super` Keyword in Inheritance**
- **`super`** is used to refer to the immediate parent class and can be used to:
  1. Call the superclass's method.
  2. Access the superclass's constructor.
- **Example**:
  ```java
  class Animal {
      void sound() {
          System.out.println("Animal sound");
      }
  }

  class Dog extends Animal {
      void sound() {
          super.sound();  // Calling superclass method
          System.out.println("Dog barks");
      }
  }

  public class Test {
      public static void main(String[] args) {
          Dog dog = new Dog();
          dog.sound();
      }
  }
  ```
  Output:
  ```
  Animal sound
  Dog barks
  ```

### **7. Benefits of Inheritance**
- **Code Reusability**: Inheritance allows code to be reused. You can reuse the methods and properties of the superclass in the subclass, avoiding code duplication.
- **Extensibility**: With inheritance, you can easily extend functionality without modifying existing code.
- **Polymorphism**: Inheritance forms the foundation for **runtime polymorphism**, allowing methods in subclasses to override methods in the superclass.

### **8. Limitations of Inheritance**
- **Single Inheritance**: Java does not support multiple inheritance (i.e., a class cannot directly inherit from more than one class). However, multiple interfaces can be implemented.
- **Tight coupling**: Overuse of inheritance can lead to tightly coupled code, making it difficult to maintain and extend.

### **9. Access Modifiers in Inheritance**
- In Java, inheritance respects the **access modifiers** of fields and methods.
  - **Public** members are accessible from anywhere.
  - **Protected** members are accessible within the same package and subclasses.
  - **Default** (no modifier) members are accessible only within the same package.
  - **Private** members are not accessible in subclasses.

### **10. Example of Inheritance with Access Modifiers**
```java
class Animal {
    public String name;
    protected int age;
    private String species;

    public void display() {
        System.out.println("Animal name: " + name);
        System.out.println("Animal age: " + age);
    }

    private void secret() {
        System.out.println("This is a private method");
    }
}

class Dog extends Animal {
    void show() {
        name = "Dog";  // Accessible because it's public
        age = 5;        // Accessible because it's protected
        // species = "Canine";  // Error: species is private in Animal

        display();      // Inherited public method
        // secret();     // Error: secret() is private in Animal
    }
}

public class Test {
    public static void main(String[] args) {
        Dog dog = new Dog();
        dog.show();
    }
}
```

### **Conclusion**
Inheritance is a powerful concept in Java that enhances the reusability and extendibility of code. It allows new classes to adopt the properties and behaviors of existing classes, thereby creating a natural hierarchical relationship between classes. Understanding how inheritance works and how to implement it properly is crucial for writing clean, efficient, and maintainable Java code.
