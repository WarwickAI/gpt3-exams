# Question 5 (6/20)

### 5a
Explain what is meant by generics and how they can be used in a program. Generics have been added to Java quite recently; explain how you could implement the functionality of generics in Java while avoiding using generics explicitly, using a linked list as an example?

```
Generics are used to create generic classes and methods. A generic class is a class that can be parameterized to accept multiple types. A generic method is a method that can be parameterized to accept multiple types.
```

(2/10)

### 5b
Consider the code below that uses exceptions:

```Java
try {
	for (int x = 4; x >= 0; x--) {
		int y = 5 / x;
		System.out.println("*");
	} }
catch (ArithmeticException ae) {
	System.out.println("A");
}
catch (Exception  e) {
	System.out.println("B");
}
System.out.println("C");
```

Describe what happens when the code is run and show the output from running this program?

```
The code will print:
*
*
*
*
A
C
```

(5/10) - Correct output, no description of what will happen
