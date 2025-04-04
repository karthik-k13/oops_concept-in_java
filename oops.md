
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


### Detailed Notes on **Polymorphism** in Java

Polymorphism is one of the core concepts in **Object-Oriented Programming (OOP)** and is fundamental to achieving flexibility and extensibility in software design. In simple terms, **polymorphism** allows one object to take many forms, which means that the same method or function can behave differently based on the object that is calling it.

Java supports polymorphism in two ways:
1. **Compile-time polymorphism** (also known as **Method Overloading**).
2. **Runtime polymorphism** (also known as **Method Overriding**).

### **1. What is Polymorphism?**
- **Definition**: Polymorphism allows a single entity (method, operator, etc.) to operate in multiple ways, depending on the context.
- The word "polymorphism" comes from Greek, where "poly" means "many" and "morph" means "forms." Therefore, polymorphism allows methods or objects to take on multiple forms.

In Java, polymorphism is often seen in method calls, where a method can perform different tasks based on the object invoking it or the parameters passed to it.

### **2. Types of Polymorphism in Java**

#### **2.1. Compile-time Polymorphism (Method Overloading)**
Compile-time polymorphism is achieved by **method overloading**, where multiple methods in the same class have the same name but differ in their parameter lists (number, type, or order of parameters).

- **Method Overloading** occurs when two or more methods in the same class have the same name but different parameters.
- This is resolved during **compilation**.

**Key Points:**
- Overloading is based on **method signature**, which includes the method name and the parameter list.
- Return type **does not** play a role in overloading.

**Example of Method Overloading:**
```java
class Calculator {
    // Overloaded methods with different parameter types
    int add(int a, int b) {
        return a + b;
    }

    double add(double a, double b) {
        return a + b;
    }

    int add(int a, int b, int c) {
        return a + b + c;
    }
}

public class Test {
    public static void main(String[] args) {
        Calculator calc = new Calculator();
        
        // Calling overloaded methods
        System.out.println(calc.add(10, 20));         // Calls int add(int, int)
        System.out.println(calc.add(10.5, 20.3));     // Calls double add(double, double)
        System.out.println(calc.add(10, 20, 30));     // Calls int add(int, int, int)
    }
}
```
Output:
```
30
30.8
60
```

Here, we see that the method `add` is overloaded with different parameter types and a different number of parameters.

#### **2.2. Runtime Polymorphism (Method Overriding)**
Runtime polymorphism, also known as **method overriding**, occurs when a subclass provides its specific implementation of a method that is already defined in its superclass. The decision of which method to call is made **at runtime** based on the object type.

- **Method Overriding** is when a subclass provides a specific implementation of a method that is already defined in its superclass.
- Overriding occurs at **runtime**, hence the name "runtime polymorphism."

**Key Points:**
- The method signature (name, return type, parameters) in the subclass must be the same as in the superclass.
- The subclass version of the method **replaces** the superclass version at runtime.
- The `@Override` annotation is optional but recommended to prevent mistakes.

**Example of Method Overriding:**
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

class Cat extends Animal {
    @Override
    void sound() {
        System.out.println("Cat meows");
    }
}

public class Test {
    public static void main(String[] args) {
        Animal myAnimal = new Animal();  // Animal object
        Animal myDog = new Dog();        // Dog object
        Animal myCat = new Cat();        // Cat object

        myAnimal.sound();  // Outputs: Animal makes a sound
        myDog.sound();     // Outputs: Dog barks
        myCat.sound();     // Outputs: Cat meows
    }
}
```
Output:
```
Animal makes a sound
Dog barks
Cat meows
```

In the example above, `sound()` is overridden in both the **Dog** and **Cat** classes. The type of object (`myDog` or `myCat`) determines which method is called, not the reference type (`Animal`). This is **runtime polymorphism**.

### **3. Method Overriding and the `super` Keyword**
When you override a method, you can still call the superclass's version of the method using the `super` keyword.

**Example**:
```java
class Animal {
    void sound() {
        System.out.println("Animal makes a sound");
    }
}

class Dog extends Animal {
    @Override
    void sound() {
        super.sound(); // Calls Animal's sound() method
        System.out.println("Dog barks");
    }
}

public class Test {
    public static void main(String[] args) {
        Dog dog = new Dog();
        dog.sound();  // Calls the Dog class's sound(), but Animal's sound() is also called.
    }
}
```
Output:
```
Animal makes a sound
Dog barks
```
Here, the `super.sound()` calls the method from the **Animal** class, followed by the method from the **Dog** class.

### **4. Polymorphism with Interfaces**
An interface allows you to define a contract that a class must follow. **Polymorphism** also works with interfaces in Java. A class can implement multiple interfaces, and different classes can provide different implementations of the same interface method.

**Example with Interfaces:**
```java
interface Animal {
    void sound();
}

class Dog implements Animal {
    public void sound() {
        System.out.println("Dog barks");
    }
}

class Cat implements Animal {
    public void sound() {
        System.out.println("Cat meows");
    }
}

public class Test {
    public static void main(String[] args) {
        Animal dog = new Dog();
        Animal cat = new Cat();
        
        dog.sound();  // Outputs: Dog barks
        cat.sound();  // Outputs: Cat meows
    }
}
```
In this case, both **Dog** and **Cat** implement the `Animal` interface, and polymorphism allows us to call `sound()` on different objects of type `Animal`.

### **5. Why is Polymorphism Important?**
- **Flexibility**: Polymorphism provides flexibility in designing systems. The same method can behave differently depending on the object invoking it, leading to more general and reusable code.
- **Extensibility**: With polymorphism, new classes can be introduced with minimal changes to existing code. This is particularly useful when extending frameworks or libraries.
- **Loose Coupling**: Polymorphism helps achieve loose coupling in programs, which makes the system more modular and easier to maintain.

### **6. The Role of Polymorphism in Java**
- **Method Overloading**: Allows multiple methods with the same name to behave differently based on the parameters.
- **Method Overriding**: Allows different classes to provide specific implementations of the same method.
- **Dynamic Method Dispatch**: In Java, polymorphism is implemented via dynamic method dispatch, which ensures that the correct method is called at runtime based on the object's type.

### **7. Real-World Example of Polymorphism**
Imagine a payment system where different types of payment methods (CreditCard, DebitCard, PayPal) are supported. All payment methods have a common interface `Payment`, and polymorphism is used to handle each type of payment differently.

```java
interface Payment {
    void pay();
}

class CreditCard implements Payment {
    public void pay() {
        System.out.println("Paying with Credit Card");
    }
}

class DebitCard implements Payment {
    public void pay() {
        System.out.println("Paying with Debit Card");
    }
}

class PayPal implements Payment {
    public void pay() {
        System.out.println("Paying with PayPal");
    }
}

public class PaymentTest {
    public static void main(String[] args) {
        Payment payment1 = new CreditCard();
        Payment payment2 = new DebitCard();
        Payment payment3 = new PayPal();

        payment1.pay();  // Outputs: Paying with Credit Card
        payment2.pay();  // Outputs: Paying with Debit Card
        payment3.pay();  // Outputs: Paying with PayPal
    }
}
```

### **8. Summary of Polymorphism**
- **Polymorphism** is the ability of an object to take many forms.
- **Compile-time polymorphism** is achieved through **method overloading**.
- **Runtime polymorphism** is achieved through **method overriding**.
- Polymorphism allows the same method name to be used for different types of objects, making the code more flexible and reusable.
- **Dynamic method dispatch** ensures that the correct version of the method is called at runtime.

### **Key Takeaways:**
- Polymorphism makes your Java code more flexible and extensible.
- It's a crucial feature in achieving **code reusability** and **loose coupling**.
- Mastering polymorphism will allow you to write **maintainable** and **scalable** Java applications.


### Detailed Notes on **Abstraction** in Java

**Abstraction** is one of the key concepts in Object-Oriented Programming (OOP) and refers to the process of hiding the implementation details from the user and showing only the essential features of the object. In Java, abstraction helps in reducing complexity and focusing on what an object does instead of how it does it.

In simple terms, abstraction allows you to define **what** an object can do (its functionality) without needing to know how it achieves that functionality.

### **1. What is Abstraction?**
- **Definition**: Abstraction is the concept of exposing only the relevant details of an object while hiding the unnecessary implementation details. It is one of the four pillars of OOP, alongside **Encapsulation**, **Inheritance**, and **Polymorphism**.
- **Purpose**: The goal of abstraction is to reduce complexity and allow the programmer to focus on the **interface** (what an object can do) rather than the **implementation** (how it does it).

### **2. Types of Abstraction in Java**
Abstraction in Java can be achieved in two ways:
1. **Abstract Classes**
2. **Interfaces**

#### **2.1. Abstract Classes**
An **abstract class** is a class that cannot be instantiated on its own and is meant to be extended by other classes. It allows you to define methods that must be implemented by subclasses (abstract methods), while also providing the option of defining methods with default behavior.

- **Key Characteristics of Abstract Classes**:
  - An abstract class can have **abstract methods** (methods without a body) and **concrete methods** (methods with a body).
  - An abstract class cannot be instantiated, meaning you cannot create an object of an abstract class directly.
  - Abstract methods in an abstract class must be implemented by any concrete (non-abstract) subclass.
  - An abstract class can have **fields** and **constructors**.

**Syntax of an Abstract Class**:
```java
abstract class Animal {
    // Abstract method (no implementation)
    abstract void sound();
    
    // Concrete method (with implementation)
    void sleep() {
        System.out.println("Animal is sleeping");
    }
}

class Dog extends Animal {
    // Providing implementation for abstract method
    @Override
    void sound() {
        System.out.println("Dog barks");
    }
}

public class Test {
    public static void main(String[] args) {
        Animal myDog = new Dog();
        myDog.sound();  // Outputs: Dog barks
        myDog.sleep();  // Outputs: Animal is sleeping
    }
}
```

In this example:
- `sound()` is an abstract method that has no implementation in the `Animal` class.
- The `Dog` class extends `Animal` and provides an implementation for the `sound()` method.
- The `sleep()` method is a concrete method and is inherited by the `Dog` class.

#### **2.2. Interfaces**
An **interface** in Java is a reference type, similar to a class, that can contain only abstract methods (methods without a body) and constants. Interfaces provide a way to define **what** actions an object can perform, but not **how** they perform those actions.

- **Key Characteristics of Interfaces**:
  - All methods in an interface are implicitly **abstract** (until Java 8, when default and static methods were introduced).
  - A class can implement multiple interfaces (supports **multiple inheritance**).
  - An interface cannot have **constructors** or **instance fields**.
  - Since Java 8, interfaces can also have **default methods** (methods with a body) and **static methods**.

**Syntax of an Interface**:
```java
interface Animal {
    // Abstract method (no implementation)
    void sound();
    
    // Default method (with implementation)
    default void sleep() {
        System.out.println("Animal is sleeping");
    }
}

class Dog implements Animal {
    // Providing implementation for abstract method
    @Override
    public void sound() {
        System.out.println("Dog barks");
    }
}

public class Test {
    public static void main(String[] args) {
        Animal myDog = new Dog();
        myDog.sound();  // Outputs: Dog barks
        myDog.sleep();  // Outputs: Animal is sleeping
    }
}
```

In this example:
- The `sound()` method is an abstract method in the `Animal` interface.
- The `Dog` class implements the `Animal` interface and provides an implementation for the `sound()` method.
- The `sleep()` method is a default method in the `Animal` interface, and it is inherited by the `Dog` class without needing to override it.

### **3. Benefits of Abstraction**
- **Reduces Complexity**: Abstraction helps in focusing only on the essential aspects of an object while hiding the unnecessary details, making it easier to work with complex systems.
- **Enhances Flexibility**: By abstracting the functionality, you can change the implementation without affecting the code that uses the abstract class or interface.
- **Promotes Code Reusability**: With abstraction, common functionality can be written once in a base class or interface and reused in derived classes.
- **Decouples Code**: It allows developers to write code that is not tightly coupled to specific implementations, making the code easier to maintain and extend.

### **4. Real-World Examples of Abstraction**
1. **Bank Account**:
   - You don’t need to know how the bank performs its internal operations (like maintaining balance, processing transactions). You only need to know that you can call methods like `deposit()`, `withdraw()`, and `getBalance()`. These methods represent the **abstract functionality** of a bank account.

2. **Vehicle**:
   - You don’t need to know the exact details of how a vehicle starts, accelerates, or stops. The abstract methods might include `start()`, `accelerate()`, and `stop()`, while the concrete implementations can vary based on whether the vehicle is a **Car**, **Bike**, or **Truck**.

### **5. Abstract Class vs Interface**
| Feature               | Abstract Class                         | Interface                           |
|-----------------------|----------------------------------------|-------------------------------------|
| **Methods**           | Can have both abstract and concrete methods | Can have only abstract methods (until Java 8) |
| **Multiple Inheritance** | A class can extend only one abstract class | A class can implement multiple interfaces |
| **Constructor**       | Can have constructors                  | Cannot have constructors           |
| **Fields**            | Can have instance variables            | Can only have constants (public, static, final) |
| **Default Method**    | Cannot have default methods             | Can have default methods (Java 8 and above) |
| **Access Modifiers**  | Can have various access modifiers for methods (public, protected, private) | All methods are implicitly `public` |

### **6. Key Concepts in Abstraction**
- **Encapsulation**: While abstraction hides the implementation details, **encapsulation** wraps the data and methods into a single unit (class) and restricts direct access to the data. Often, abstraction and encapsulation go hand in hand in OOP.
- **Interface Segregation Principle (ISP)**: In a well-designed system, abstraction via interfaces should focus on providing specific functionality, avoiding "fat" interfaces that try to do too much. This principle is part of the SOLID principles of object-oriented design.

### **7. Conclusion**
Abstraction in Java allows you to simplify complex systems by exposing only the necessary details. Through **abstract classes** and **interfaces**, Java provides powerful tools for abstraction, helping developers write cleaner, more maintainable, and more modular code.

- **Abstract Classes** are best used when you have common functionality to share across subclasses and need to provide default behavior.
- **Interfaces** are used when you want to specify a contract that multiple classes can implement, ensuring they provide certain methods.

By mastering abstraction, you can design flexible, extensible, and reusable Java applications.


### **Detailed Notes on Encapsulation in Java**

**Encapsulation** is one of the four fundamental Object-Oriented Programming (OOP) principles, along with **Inheritance**, **Polymorphism**, and **Abstraction**. It is a key concept that refers to the bundling of data (attributes) and methods (behaviors) into a single unit, known as a **class**. Furthermore, encapsulation also involves restricting direct access to some of an object's components, usually via **private access modifiers** and controlling access to them through **public getter and setter methods**.

Encapsulation serves to **protect** the internal state of an object by exposing only what is necessary and hiding the unnecessary details from the outside world. It provides a controlled interface to the object's data and behavior.

### **1. What is Encapsulation?**

**Definition**: Encapsulation is the process of hiding the implementation details of a class and exposing only the necessary parts through methods. This is typically done by making the class’s attributes private and providing **getter** and **setter** methods to access and update these attributes.

**Key Concepts**:
- **Private Fields**: The data of a class is made private, so it cannot be accessed directly from outside the class.
- **Public Methods (Getters and Setters)**: These methods are provided to allow access to the private fields in a controlled manner. They are often referred to as **accessor** (getter) and **mutator** (setter) methods.
- **Control Over Data**: Encapsulation allows for control over the data, ensuring that any changes or retrievals are done in a safe and validated manner.

### **2. Benefits of Encapsulation**

1. **Data Hiding**: By keeping fields private, encapsulation hides the internal details of the object. This prevents unauthorized access and modification, ensuring that the object's data cannot be directly changed or accessed in an unpredictable way.
   
2. **Improved Code Maintainability**: When changes are made to the internal workings of a class, they can be done without affecting other parts of the program that rely on the class, as the interaction happens through well-defined methods.

3. **Increased Flexibility**: Encapsulation allows you to change the internal implementation of the class (e.g., switching from one algorithm to another) without affecting the external code using the class.

4. **Easier Debugging**: By controlling access to class data and behavior through getters and setters, you can introduce validation and debugging processes, making it easier to manage and detect errors.

5. **Enhanced Security**: Sensitive data can be encapsulated, making it accessible only through specific methods, which can include validation, logging, or applying business logic.

### **3. Encapsulation Example in Java**

Below is a simple example that demonstrates how encapsulation works in Java. The example uses a `Person` class where the person's details (such as name and age) are kept private, and public methods (getter and setter) are provided to access or modify them.

```java
class Person {
    // Private fields (Encapsulation)
    private String name;
    private int age;

    // Getter method for 'name'
    public String getName() {
        return name;
    }

    // Setter method for 'name'
    public void setName(String name) {
        this.name = name;
    }

    // Getter method for 'age'
    public int getAge() {
        return age;
    }

    // Setter method for 'age'
    public void setAge(int age) {
        if (age > 0) {  // Adding validation logic
            this.age = age;
        } else {
            System.out.println("Age must be positive.");
        }
    }
}

public class Main {
    public static void main(String[] args) {
        // Create an object of the 'Person' class
        Person person = new Person();

        // Use setter methods to set values (Encapsulation in action)
        person.setName("John");
        person.setAge(25);

        // Use getter methods to retrieve values
        System.out.println("Name: " + person.getName());  // Outputs: John
        System.out.println("Age: " + person.getAge());    // Outputs: 25
    }
}
```

### **Explanation of the Code**:

- **Private Fields**: 
  - The `name` and `age` fields in the `Person` class are marked as `private`, meaning they cannot be accessed directly from outside the class.
  
- **Public Methods**:
  - **Getter Methods**: `getName()` and `getAge()` allow access to the private fields. These methods are used to retrieve the values of `name` and `age`.
  - **Setter Methods**: `setName(String name)` and `setAge(int age)` allow modification of the private fields. The `setAge()` method also includes a validation check to ensure that the age is positive.

This way, the internal state of the object is protected, and any changes to the fields are controlled through methods.

### **4. Real-World Examples of Encapsulation**

1. **Bank Account Class**:
   - **Private Fields**: Bank account balance should not be directly modified.
   - **Public Methods**: Deposit and withdraw methods allow controlled access to the account balance.

```java
class BankAccount {
    private double balance;

    // Constructor
    public BankAccount(double initialBalance) {
        balance = initialBalance;
    }

    // Getter method for balance
    public double getBalance() {
        return balance;
    }

    // Setter method for deposit
    public void deposit(double amount) {
        if (amount > 0) {
            balance += amount;
        }
    }

    // Setter method for withdrawal
    public void withdraw(double amount) {
        if (amount > 0 && amount <= balance) {
            balance -= amount;
        } else {
            System.out.println("Invalid withdrawal amount.");
        }
    }
}
```

2. **Car Class**:
   - **Private Fields**: The internal state of the car, such as fuel level, should be protected from direct access.
   - **Public Methods**: Methods like `refuel()` and `drive()` control how the car's fuel level is modified.

```java
class Car {
    private int fuelLevel;

    // Constructor
    public Car(int fuelLevel) {
        this.fuelLevel = fuelLevel;
    }

    // Getter method for fuel level
    public int getFuelLevel() {
        return fuelLevel;
    }

    // Setter method for refueling
    public void refuel(int amount) {
        if (amount > 0) {
            fuelLevel += amount;
        }
    }

    // Method for driving the car
    public void drive(int distance) {
        int fuelConsumed = distance / 10; // Assuming 1 unit of fuel per 10 km
        if (fuelConsumed <= fuelLevel) {
            fuelLevel -= fuelConsumed;
            System.out.println("Driven " + distance + " km");
        } else {
            System.out.println("Not enough fuel to drive.");
        }
    }
}
```

In both examples, encapsulation ensures that critical data (e.g., balance, fuel level) is protected from direct manipulation and that the state of the object is modified only through controlled and valid operations.

### **5. Best Practices for Encapsulation**

1. **Use Private Fields**: Always declare the fields of a class as private. This ensures that they cannot be accessed or modified directly from outside the class.
   
2. **Use Public Getter and Setter Methods**: Provide getter and setter methods to access and modify the private fields. This allows you to control how the fields are accessed or updated.

3. **Validation in Setter Methods**: If a field requires validation (e.g., an age should be positive), perform the validation inside the setter method to ensure the field’s value is always valid.

4. **Avoid Providing Public Setters for Sensitive Data**: For sensitive data like password or personal information, avoid providing setters to modify the fields directly. Instead, provide methods that perform the necessary business logic.

5. **Keep Methods Focused**: Keep getter and setter methods simple and avoid putting complex logic inside them. They should only be responsible for getting or setting the values of fields.

### **6. Conclusion**

Encapsulation is a powerful concept in Java that ensures data security, flexibility, and maintainability. By hiding the internal details of a class and exposing only the necessary functionality through public methods, you create a clean and controlled interface for the objects, ensuring the system remains robust and easy to maintain.

- **Benefits**: Encapsulation promotes code reusability, maintainability, and security.
- **Real-World Use**: Commonly used in cases where data integrity and validation are important, such as in banking systems, car systems, or any domain where sensitive or critical data is involved.

By applying the principle of encapsulation, Java developers can ensure that their systems are more reliable, easier to manage, and less prone to errors.
