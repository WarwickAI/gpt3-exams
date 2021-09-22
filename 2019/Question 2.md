# Question 2 (8/20)
## QUESTION 2a
2a Consider the following method written to determine whether its String parameter is a palindrome, that is it is identical when read left-to-right and right-to-left:

```Java
boolean isPalindrome(String s) {
    int i = 0;
    j = s.length - 1;
    while (i != j && s.charAt(i) = s.charAt(j)) {
        i++;    j--;    }
        return (i == j);    }
```
Unfortunately the code does not compile. Identify and fix three syntax errors that prevent the code from compiling?

### ANSWER
```
The scope of variable i is not specified.
The scope of variable j is not specified.
The scope of variable s is not specified.
```

(0/6) - Codex isn't great at identifying syntax errors in code, likely because there weren't many examples in the 2017 paper

## QUESTION 2b
2b After fixing the syntax of the code from 2a, if you run it you will see that there is a logical error, in that it does not run correctly or results in a runtime error. Identify the error and provide a fix for it?

### ANSWER
```Java
boolean isPalindrome(String s) {
    int i = 0;
    int j = s.length - 1;
    while (i != j && s.charAt(i) == s.charAt(j)) {
        i++;    j--;    }
        return (i == j);    }?
		
The return value is not specified.
The return value should be a boolean.
```

(0/6) - Interestingly Codex did add "int j = ..." and replaced "=" with "==" in the while loop, so it can identify some syntax errors if prompted correctly

## QUESTION 2c
2c Write an alternative, recursive method to check for palindromes?

### ANSWER
```Java
boolean isPalindrome(String s) {
    if (s.length() <= 1) {
        return true;
    } else {
        return s.charAt(0) == s.charAt(s.length() - 1) && isPalindrome(s.substring(1, s.length() - 1));
    }
}
```

(8/8) - lgtm
