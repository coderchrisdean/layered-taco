# Validating Passwords with Regex

In this tutorial, we will learn how to use Regex to check if passwords are strong enough.  We'll go through the different parts of a Regex, like anchors, quantifiers, character classes, and look-ahead and look-behind, and show you how to use them to create a Regex pattern that makes sure passwords have at least a certain number of characters, a mix of uppercase and lowercase letters, numbers, and special characters. Also, we'll make sure that the password doesn't contain any two or more consecutive digits in ascending or descending order by using two look-behind (negative look-ahead) assertions.

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
- [OR Operator](#or-operator)
- [Character Classes](#character-classes)
- [Bracket Expressions](#bracket-expressions)
- [Greedy and Lazy Match](#greedy-and-lazy-match)
- [Boundaries](#boundaries)
- [Back-references](#back-references)
- [Look-ahead and Look-behind](#look-ahead-and-look-behind)
- [Author](#author)

## Regex Components

Since regex is considered a literal, the pattern is wrapped in slashes (/). 
### Anchors 

Anchors are employed to find patterns at the start or end of a string. Caret (^) and Dollar Sign ($) are both considered anchors. We can use the caret (^) anchor in our password validation Regex to match the start of the string.

### Quantifiers

Quantifiers determine the number of times a character or group is matched in a Regex. In the password validation Regex, we use the {8,} quantifier to match a minimum of 8 characters.


### OR Operator

In "Password Validator," we use the OR operator (|) to match either a digit or a letter. This operator is used in our regex as follows: 

`/^(?!.*(\d{2,}`

OR (|) -> `|`

`([0-9]).*?\2))(?=.*[A-Z])(?=.*[a-z])(?=.*\d)(?=.*[@$!%*?&])[A-Za-z\d@$!%*?&]{8,}$/`

The OR operator is specifically used in the negative lookahead to enforce the rule that the password cannot contain consecutive digits. The lookahead checks if there are two or more digits in a row, which would violate the rule.

### Character Classes

In the Password Validator Regex, we utilize character classes to match a specific set of characters. To ensure a strong password, we include four positive look-aheads, that match at least one uppercase letter, one lowercase letter, one digit, and one special character followed by one negative look-ahead that ensures that the password does not contain any two or more consecutive digits in ascending or descending order. The positive look-aheads are as follows:

```
(?=.*[A-Z])
(?=.*[a-z])
(?=.*\d)
(?=.*[@$!%*?&])
```

The negative look-ahead is as follows:

```
(?!(.*\d){2,}|.*([0-9]).*?\2)
```
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

### Greedy and Lazy Match

There are no greedy or lazy matches in "Password Validator".

### Boundaries

There are no boundaries in "Password Validator".

### Back-references

### Look-ahead and Look-behind

The first positive lookahead `(?=.*[A-Z])` matches at least one uppercase letter.
The second positive lookahead `(?=.*[a-z])` matches at least one lowercase letter.
The third positive lookahead `(?=.*\d)` matches at least one digit.
The fourth positive lookahead `(?=.*[@$!%*?&])` matches at least one special character, which can be any of the following: `@`, `$`, `!`, `%`, `*`, `?`, `&`.

The negative look-ahead `(?!(.*\d){2,}|.*([0-9]).*?\2)` ensures that the password does not contain consecutive digits.
The look-aheads and look-behind ensure that the password meets the complexity requirements while also preventing certain patterns in the password.

## Author

This tutorial was written by Christopher Dean.  You can find more of his work on [GitHub](https://github.com/coderchrisdean), or reach out to coderchrisdean@gmail.com.
