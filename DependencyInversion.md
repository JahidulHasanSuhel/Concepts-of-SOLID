# **`Dependency Inversion Principle`**
## What is DIP?
The Dependency Inversion Principle states that **high-level modules should not depend on low-level modules**, but rather both should depend on abstractions. Furthermore, abstractions should not depend on details, but rather details should depend on abstractions.

For example:
```
public class ClassA {
    ClassB objectB;

    public ClassA(ClassB objectB) {
        this.objectB = objectB;
    }

    public void foo() {
        // Some code
        // And then call the method of ClassB
        objectB.doSomething();
    }
}
```
In the above example, `ClassA` is a high-level module and `ClassB` is a low-level module. `ClassA` is directly dependent on `ClassB`.

But, DIP is telling us to invert the dependency using an abstraction. So, we can do it by creating an interface:
```
public interface InterfaceB {
    public void doSomething();
}
```
By doing this, we can change the `ClassA` to use the InterfaceB instead of `ClassB`:
```
public class ClassA {
    InterfaceB objectB;

    public ClassA(InterfaceB objectB) {
        this.objectB = objectB;
    }

    public void foo() {
        // Some code
        // And then call the method of InterfaceB
        objectB.doSomething();
    }
}
```
Now, `ClassA` is not directly dependent on `ClassB`, but rather on `InterfaceB`, the same goes for `ClassB`. This is the essence of DIP.
- [source code.](https://github.com/JahidulHasanSuhel/SOLID-Principles/tree/main/DependencyInversion)
## **`Goal`**:
This principle aims at reducing the dependency of a high-level Class on the low-level Class by introducing an interface.
