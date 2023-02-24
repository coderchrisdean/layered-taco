# Validating Passwords with Regex

In this tutorial, we will learn how to use Regex to check if passwords are strong enough.  We'll go through the different parts of a Regex, like anchors, quantifiers, character classes, and look-ahead and look-behind, and show you how to use them to create a Regex pattern that makes sure passwords have at least a certain number of characters, a mix of uppercase and lowercase letters, numbers, and special characters. Also, we'll make sure that the password doesn't contain any two or more consecutive digits in ascending or descending order by using two negative look-ahead assertions.

## Summary

In this tutorial, we will use the following Regex pattern to validate passwords:

```
/^(?!.*(\d{2,}|([0-9]).*?\2))(?=.*[A-Z])(?=.*[a-z])(?=.*\d)(?=.*[@$!%*?&])[A-Za-z\d@$!%*?&]{8,}$/
```

We will call this regex pattern "Password Validator".

This pattern checks that the password has at least 8 characters, at least one uppercase letter, at least one lowercase letter, at least one number, and at least one special character.  It also checks that the password doesn't contain any two or more consecutive digits in ascending or descending order.  

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Bracket Expressions](#bracket-expressions)
- [OR Operator](#or-operator)
- [Character Classes](#character-classes)
- [Look-ahead and Look-behind](#look-ahead-and-look-behind)

## Regex Components

Since regex is considered a literal, the pattern is wrapped in slashes (/). 
### Anchors 

Anchors are employed to find patterns at the start or end of a string. Caret (^) and Dollar Sign ($) are both considered anchors. We can use the caret (^) anchor in our password validation Regex to match the start of the string.

### Quantifiers

Quantifiers determine the number of times a character or group is matched in a Regex. In the password validation Regex, we use the {8,} quantifier to match a minimum of 8 characters.

### Bracket Expressions

Bracket expressions allow you to define a set of characters to match, such as any digit or letter. In "Password Validator", we use the following bracket expressions:

```
[A-Za-z\d@$!%*?&]
[0-9]
[@$!%*?&]
[A-Za-z\d@$!%*?&]
```

The first bracket expression `[A-Za-z\d@$!%*?&]` is used to match any uppercase or lowercase letter, any digit, or any of the special characters.

The second bracket expression `[0-9]` is used to match any digit.

The third bracket expression `[@$!%*?&]` is used to match any of the special characters.

The fourth bracket expression `[A-Za-z\d@$!%*?&]` is used to match any uppercase or lowercase letter, any digit, or any of the special characters.

### OR Operator

### Character Classes

### Flags

### Grouping and Capturing

### Bracket Expressions

### Greedy and Lazy Match

### Boundaries

### Back-references

### Look-ahead and Look-behind

## Author

A short section about the author with a link to the author's GitHub profile (replace with your information and a link to your profile)
