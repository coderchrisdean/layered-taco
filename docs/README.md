# 🔒 Password Validator

This project is a Regular Expression (regex) pattern that can be used to validate the strength and complexity of passwords.  The password validator ensures that the password meets certain criteria, such as length, character requirements, and pattern restrictions.

## 🗂️ Table of Contents

- [Getting Started](#getting-started)
- [How It Works](#how-it-works)
- [Usage](#usage)
- [Author](#author)
- [License](#license)
- [Links](#links)

## 🚀 Getting Started

To use this password validator, copy the following regex pattern and paste it into your code:

```
/^(?!.*(\d{2,}|([0-9]).*?\2))(?=.*[A-Z])(?=.*[a-z])(?=.*\d)(?=.*[@$!%*?&])[A-Za-z\d@$!%*?&]{8,}$/
```

You can call this regex pattern "Password Validator."


## 🔍 How It Works

This Password Validator regex enforces the following certain criteria:

- Anchors `^`, `$` which are used to match patters at the beginning or end of a string.
- Quantifiers `{8,}` which are used to match a minimum of 8 characters.
- OR Operator `|` which is used to match either a digit or a letter.
- Character Classes `[A-Z]`, `[a-z]`, `[0-9]`, `[@$!%*?&]` which are used to match a specific set of characters.
- Bracket Expressions `[A-Za-z\d@$!%*?&]` which are used to match a specific set of characters.
- Look-ahead and Look-behind `(?=.*[A-Z])`, `(?=.*[a-z])`, `(?=.*\d)`, `(?=.*[@$!%*?&])` which are used to match a specific set of characters.

The regex pattern validates the following type of password:

- The password must be at least 8 characters long.
- The password must contain at least one uppercase letter.
- The password must contain at least one lowercase letter.
- The password must contain at least one digit.
- The password must contain at least one special character.
- The password cannot contain two or more consecutive digits in ascending or descending order.

## 🛠️ Usage

Just copy and paste the pattern from "Getting Started" into your code.

## 🧑‍💻 Author

This project was created by Christopher Dean - [GitHub](https://github.com/coderchrisdean/)

## 📝 License

None

## 🔗 Links

### GitHub Repository:
 - https://github.com/coderchrisdean/layered-taco/

 ### GitHub Gist:
  - https://gist.github.com/coderchrisdean/fe4819cd07bb563e7d8fd2ca2c2f14f9

