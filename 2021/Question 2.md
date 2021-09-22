# Question 2 (15/20)

## Question 2a
2a Using iterative statements, write code to calculate the result of the following formula:

(\sum_{x=30}^{70}{x^2 + 2}) / 5?

### ANSWER
```Java
int result = 0;
for (int i = 30; i <= 70; i++) {
    result += i * i + 2;
}
result /= 5;
```

(5/5) - Formatting in latex helps

## Question 2b
2b Write a method that, when given an integer value, returns whether the value is a prime number or not?

### ANSWER
```Java
public boolean isPrime(int n) {
    if (n < 2) {
        return false;
    }
    for (int i = 2; i < n; i++) {
        if (n % i == 0) {
            return false;
        }
    }
    return true;
}
```

(5/5)

## Question 2c
2c Using your previous answer to 2b, write code that returns an array filled with the first 30 prime numbers?

### ANSWER
```Java
public int[] getPrimes(int n) {
    int[] primes = new int[n];
    int i = 0;
    int j = 0;
    while (i < n) {
        if (isPrime(j)) {
            primes[i] = j;
            i++;
        }
        j++;
    }
    return primes;
}
```

(4/6) - n prime numbers instead of 30

## Question 2d
2d Rewrite the following for loop as a while loop:

```
int total = 0; 
for (int i = 0; i < 100; i+=2) { 
	total = total + (i * Math.random() * Math.random()); 
	if (total > 75) { break; } 
}?
```

### ANSWER
```Java
int total = 0; 
int i = 0; 
while (i < 100) { 
	total = total + (i * Math.random() * Math.random()); 
	if (total > 75) { break; } 
	i += 2; 
}
```

(3/3)

## Question 2e
2e Can the loop in 2d be written recursively? Justify your answer?

### ANSWER
```
No, because the loop in 2d is not tail recursive.
```

(0/1)
