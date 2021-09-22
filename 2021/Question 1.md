# Question 1 (2/20)
## QUESTION 1a i
Java can convert variables between various types using typecasts. For the following type conversion, write Java code that would perform it, and state if is it an implicit or explicit typecast. 
int -> byte?

### ANSWER
```
explicit
```

(0/1) - no code

## QUESTION 1a ii
Java can convert variables between various types using typecasts. For the following type conversion, write Java code that would perform it, and state if is it an implicit or explicit typecast. 
short -> long?

### ANSWER
```
implicit
```

(0/1) - no code

## QUESTION 1b
Floating point numbers in Java are represented using IEEE-754 notation. Given a 12 bit floating point number, where the sign is 1 bit, the exponent is 4 bits, the fraction is 7 bits and the number is calculated using the formula:
-1^(sign) * 1.(fraction) * 2^(exponent-4)
calculate the decimal value of number 101101100100?

### ANSWER
```
-1^(1) * 1.(01101100100) * 2^(0-4)
-1 * 1.01101100100 * 2^0
-1.01101100100 * 2
-1.01101100100 * 2
-2.01101100100
```

(0/3) - Converting wrong way around, likely because this isn't in the prompt

## QUESTION 1c
The following code runs, but is not correct. Instead of returning the minimum value it will often either not finish or produce a runtime error. 
```
public void findMinimum(int[] arr) { 
	int x = 0 
	int min = Integer.MAX_VALUE; 
	while (x != arr.length) { 
		if ( min > arr[x] && ++x < arr.length) { 
			min = arr[x]; 
		} 
	} 
	return min; 
}
```
Explain the issues with the code, and re-write it so that it works as expected?

### ANSWER
```
The code will not work as expected because the while loop will never terminate.
```

(1/5) - Identified one issue, as if arr=[Integer.MAX_VALUE] it will never terminate, but no justification or correcting though

## QUESTION 1d
Program control in Java is managed using if and switch statements. Rewrite the following code in the most concise form possible using an if-else statement.

```
switch (a) { 
	case 4: System.out.println(‘‘Option 4’’); 
	case 2: System.out.println(‘‘Option 2’’); 
	break;
	case 1: System.out.println(‘‘Option 1’’); 
	default: System.out.println(‘‘Default’’); 
}?
```

### ANSWER
```Java
if (a == 4) {
    System.out.println("Option 4");
} else if (a == 2) {
    System.out.println("Option 2");
} else if (a == 1) {
    System.out.println("Option 1");
} else {
    System.out.println("Default");
}
```

(0/5)

## QUESTION 1e
Give the logic expression for each of the following post conditions:

```
if (a > 0) { 
// p1 
} else if (b > 0) { 
	// p2 
	if (a > -5) { 
			// p3 
		} else { 
			// p4 
		} 
	} 
else if (b == 1) { 
	// p5 
}?
```

### ANSWER
```
p1: a > 0
p2: b > 0
p3: a > -5
p4: a <= -5
p5: b == 1
```

(1/5) - p1 correct
