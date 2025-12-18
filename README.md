# 🧠 Abstraction in Java

> **Abstraction** is one of the core concepts of Object-Oriented Programming (OOP) in Java.

It means **showing only the required details** to the user and **hiding complex implementation logic**.

---

## 🌍 Real-Life Example: ATM Machine

When you use an **ATM**:

* You can **withdraw money**
* You can **deposit money**
* You can **check balance**

But ❌ you **don’t know**:

* How the ATM connects to the bank server
* How verification happens internally

✅ This hiding of internal complexity is called **Abstraction**.

---

## 🔑 How Abstraction is Achieved in Java

Java provides **two ways** to achieve abstraction:

1️⃣ **Abstract Class**
2️⃣ **Interface**

---

# 1️⃣ Abstract Class

### 📌 Definition

A class declared using the `abstract` keyword is called an **abstract class**.

```java
abstract class Bank {
    abstract void getInterestRate();

    void displayBankName() {
        System.out.println("Welcome to the Bank");
    }
}
```

---

### ⭐ Key Points

✔ Can have **abstract methods** and **concrete methods**
✔ **Abstract methods** have **no body**
✔ Cannot create an object of an abstract class
✔ Can have **constructors**
✔ Can have **instance blocks & static blocks**
✔ Used when **partial implementation is known**
❌ Does **not support multiple inheritance**

---

### 🔍 Abstract Method Rules

* Only method declaration
* No method body
* Cannot be:

  * `static`
  * `final`
  * `private`

---

### 🧪 Example: Abstract Class Implementation

```java
abstract class Vehicle {
    abstract void start();

    void fuelType() {
        System.out.println("Vehicle uses fuel");
    }
}

class Bike extends Vehicle {
    void start() {
        System.out.println("Bike starts with kick");
    }
}

public class Main {
    public static void main(String[] args) {
        Vehicle v = new Bike();
        v.start();
        v.fuelType();
    }
}
```

✅ **Output**

```
Bike starts with kick
Vehicle uses fuel
```

---

# 2️⃣ Interface

### 📌 Definition

An **interface** is a **blueprint of a class**.
Use it when you have **only requirements (specifications)** and **no implementation**.

```java
interface Payment {
    void pay();
}
```

---

### ⭐ Key Points

✔ All methods are **public & abstract by default**
✔ Provides **100% abstraction**
✔ Supports **multiple inheritance**
✔ Can have **default methods** (Java 8+)

❌ Cannot have:

* Constructors
* Instance blocks
* Static blocks

---

### 🔐 Method Rules in Interface

Methods **cannot be**:

* `private`
* `protected`
* `final`
* `static`
* `synchronized`

---

### 📦 Variable Rules in Interface

* Variables are always:

  * `public`
  * `static`
  * `final`
* Must be **initialized at declaration**

```java
interface Test {
    int x = 10; // valid
}
```

❌ This causes compile-time error:

```java
interface Test {
    int x; // ERROR
}
```

---

### 🧪 Example: Interface Implementation

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

public class Main {
    public static void main(String[] args) {
        Animal a1 = new Dog();
        Animal a2 = new Cat();

        a1.sound();
        a2.sound();
    }
}
```

✅ **Output**

```
Dog barks
Cat meows
```

---

### 🆕 Default Method Example

```java
interface Printer {
    default void print() {
        System.out.println("Printing document");
    }
}

class HPPrinter implements Printer {
}

public class Main {
    public static void main(String[] args) {
        Printer p = new HPPrinter();
        p.print();
    }
}
```

---

## 🔁 Abstract Class vs Interface

| Feature              | Abstract Class      | Interface                  |
| -------------------- | ------------------- | -------------------------- |
| Methods              | Abstract + Concrete | Abstract (default allowed) |
| Variables            | Any type            | public static final        |
| Constructors         | ✅ Yes               | ❌ No                       |
| Blocks               | Instance & Static   | ❌ Not allowed              |
| Multiple Inheritance | ❌ No                | ✅ Yes                      |
| Abstraction          | Partial             | 100%                       |

---

## 🎯 When to Use What?

✔ Use **Abstract Class** when:

* You want **partial implementation**
* Classes are **closely related**

✔ Use **Interface** when:

* You want **full abstraction**
* You need **multiple inheritance**
* You define **common behavior for unrelated classes**

---

## ✅ Conclusion

* **Abstraction improves security & flexibility**
* Helps in **loose coupling**
* Makes code **clean and maintainable**
* Abstract class & interface are **interview favorites** 🚀

---

✨ *Happy Coding with Java!* ✨
