# Question 1 (12/20)
### 1a
Explain what is meant by casting in Java and show examples where it is safe and when it is unsafe to use casting?

```
Casting is a way to convert a variable from one type to another. Casting is safe when the variable is converted to a type that is more specific than the original type. Casting is unsafe when the variable is converted to a type that is less specific than the original type. For example, casting a float to an int is unsafe because an int can hold any value that a float can hold. However, casting an int to a float is safe because a float can hold a larger range of values than an int can.
```

(1/4) - Too vague

### 1b
Explain the difference between 2, 2.0, '2', and "2.0"?

```
2 is an integer, 2.0 is a floating point number, '2' is a string, and "2.0" is a string.
```

(4/4)

### 1c
Describe the syntax of the switch statement, and explain its use through a small example which shows different possible outcomes?

```
The switch statement is a multiway branch statement that compares a value with a variable. The switch statement is used to select from a number of alternatives.
switch(x) {
    case 1:
    x = 2;
    break;
}
```

(1/4) - Didn't explain the syntax, only showed one possible outcome from the switch statement.

### 1d i
Rewrite the following loop into a while loop:
int s = 0;

```
for (int i = 1; i <= 10; i++) s = s + i;?
```

```Java
int s = 0;
int i = 1;
while (i <= 10) {
    s = s + i;
    i++;
}
```

(4/4)

### 1d ii
Rewrite the following loop into a while loop:

```
int n = 1;
double x = 0;
double s;
do {
	s = 1.0 / (n*n) ;
	x = x + s ;
	n++ ;
} while (s > 0.01);?
```

```Java
int n = 1;
double x = 0;
double s;
while (s > 0.01) {
	s = 1.0 / (n*n) ;
	x = x + s ;
	n++ ;
}

```

(2/4) Almost correct, but since the original was do {x} while {y}, x is evaluated before checking y which isn't the case in the answer.
