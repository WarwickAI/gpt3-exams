# Question 5 (12/20)
## QUESTION 5a i
In Java, erroneous behaviour often results in an Exception being generated. An Exception allows a programmer an opportunity to handle errors gracefully and possibly take corrective measures.

Performing a division by zero in Java causes an exception when dealing with integer division. However, for floating point numbers, the special value “Inf” is returned and no exception is raised. Write a checked exception class that will be raised when a floating point division by zero is about to occur?

### ANSWER
```Java
public class DivideByZeroException extends Exception {
    public DivideByZeroException() {
        super("Division by zero");
    }
}
```

(0/3)

## QUESTION 5a ii
5aii Write a method that divides one floating point number by another and returns the result. In the event that the denominator is zero, an exception should be generated?

### ANSWER
```Java
public static float divide(float x, float y) {
    if(y == 0) {
        throw new ArithmeticException("Divide by zero");
    }
    return x/y;
}
```

(3/4) - static method?

## QUESTION 5a iii
Write a code example to demonstrate how you would use the method from 5aii in a Java application?

### ANSWER
```Java
public static void main(String[] args) {
    try {
        System.out.println(divide(10, 0));
    } catch(ArithmeticException e) {
        System.out.println("Divide by zero");
    }
}
```

(3/3)

## QUESTION 5b
5b A set object only allows unique objects to be stored. Design a generic Set class for storing objects. Include appropriate methods to add items, to find if a particular object is already in the set and to find the number of objects stored?

### ANSWER
```Java
public class Set<T> {
    private T[] objects;
    public Set() {
        objects = new T[0];
    }
    public void add(T object) {
        if (objects.contains(object)) {
            return;
        }
        T[] newObjects = new T[objects.length + 1];
        for (int i = 0; i < objects.length; i++) {
            newObjects[i] = objects[i];
        }
        newObjects[objects.length] = object;
        objects = newObjects;
    }
    public boolean contains(T object) {
        return objects.contains(object);
    }
    public int size() {
        return objects.length;
    }
}
```

(6/6)

## QUESTION 5c
5c We wish to use the Set class to store Employee objects from question 4. Demonstrate how we would achieve this?

### ANSWER
```Java
Just repeated the Employee Class
```

(0/2)

## QUESTION 5d
5d Modify your Set class so that it can only store Employee objects?

### ANSWER
```Java
public class Set<T> {
    private T[] objects;
    public Set() {
        objects = new T[0];
    }
    public void add(T object) {
        if (objects.contains(object)) {
            return;
        }
        T[] newObjects = new T[objects.length + 1];
        for (int i = 0; i < objects.length; i++) {
            newObjects[i] = objects[i];
        }
        newObjects[objects.length] = object;
        objects = newObjects;
    }
    public boolean contains(T object) {
        return objects.contains(object);
    }
    public int size() {
        return objects.length;
    }
}
```

(0/2)
