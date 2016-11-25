# Naming rules and conventions

### Rules
The Java naming rules **must** be followed or the compiler will flag the statement with an
error message.

When you create names for variables, constants, methods, classes, etc, the legal
characters for Java names are:
* Uppercase letters
* lowercase letters
* digits (0-9)
* underscore

In your names you cannot use:
* reserved words (keywords)
* spaces
* special characters (%, &, *, etc.)
* cannot *begin* with a digit

These names would be legal:
* age
* Employee
* planet567

These names would *not* be legal:
* 567planet (can't start with a digit)
* Employee salary (has a blank space)
* age% (can't have a special character)
* int (is a reserved word)

### Conventions
The Java naming rules must be followed. But there are also conventions used in naming
things in Java. You should follow them to be consistent with other programmers.

Class names should begin with an uppercase letter.

```java
public class Employee {
    // class code
}
```
Variables should begin with a lowercase letter and then capitalize each word.

```
age
planetDiameter
rateOfPay
```
Method names should begin with a lowercase letter and then capitalize each word.
```
displaySalary
monthlySalary
```
Constants should be all uppercase.
```
PI
TAXRATE
```
