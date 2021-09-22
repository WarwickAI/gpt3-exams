# Question 3 (10/20)
### 3a
For the following pair, explain similarities and differences between them, and discuss when you would use one rather than the other:
protected and private data fields?

```
Both are used to restrict access to a class.
Protected members can be accessed by subclasses of the class in which the members are defined.
Private members can be accessed only within the class in which they are defined.
```

(1/4) - Did not discuss when you would use one rather than the other.

I prompted after the response with ```You would use protected rather than private when``` and ```You would use private rather than protected when you want``` to obtain the following:

```
You would use protected rather than private when you want to allow access to a class from a subclass.
You would use private rather than protected when you want to ensure that the class cannot be instantiated.
```

(2/4) - Still doesn't have exhaustive answer for protected vs. private

### 3b
For the following pair, explain similarities and differences between them, and discuss when you would use one rather than the other:
interfaces and abstract classes?

```
Both interfaces and abstract classes are used to define a contract. An interface is a set of methods that a class must implement. An abstract class is a class that can't be instantiated. You would use interfaces rather than abstract classes when you want to define a contract. You would use abstract classes rather than interfaces when you want to define a contract and also want to provide some implementation.
```

(2/4)

### 3c
For the following pair, explain similarities and differences between them, and discuss when you would use one rather than the other:
static and non-static?

```
A static method is a method that is bound to the class rather than to an object of the class. A non-static method is a method that is bound to the object. You would use static methods when you want to define a method that doesn't need to access any instance variables. You would use non-static methods when you want to define a method that needs to access instance variables.
```

(1/4)

### 3d
For the following pair, explain similarities and differences between them, and discuss when you would use one rather than the other:
overloading and overriding?

```
Overloading is a feature of object-oriented programming in which a class has two or more methods with the same name but different parameters or argument types. Overriding is a feature of object-oriented programming in which a subclass overrides a method of its superclass. You would use overloading instead of overriding when you want to provide more than one implementation of a method. You would use overriding instead of overloading when you want to provide only one implementation of a method.
```

(4/4)

### 3e
For the following pair, explain similarities and differences between them, and discuss when you would use one rather than the other:
array declaration and array creation?

```
Array declaration is a way to declare an array and initialize it with a value. Array creation is a way to create an array and initialize it with a value. You would use array declaration when you want to declare an array and initialize it with a value. You would use array creation when you want to create an array and initialize it with a value.
```

(?/4)