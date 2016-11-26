## Selection

#### Objectives
* Use if..else structures
* Use a switch statement
* Understand nesting of structures
* Use AND, OR, NOT operators
* Use conditional operators

#### Contents
* Selection
* Relational and Logical Operators
* Additional Reading

#### Selection
##### A Java program can make a selection between alternate paths by using
    * An **if..else** structure
    * A **switch** statement

#### if..else structure
Use the **if..else** structure to choose between two or more paths. The part in the **( )**
is called a *condition*. The condition is either true or false (i.e. *Boolean*). For example,
suppose you need to determine a rate for school tuition based on whether a person lives
in-state or out-of-state. A simple **if..else** statement could be used.
```java
String status;
status = "Instate";

if (status.equals("Instate")) {
    tuition = 1000;
} else {
    tuition = 250;
}
```
The condition here is ```status.equals("Instate")```, seen between the parentheses.

Here are some other examples:
```java
int age;
age = 55;
double rate;

if (age >= 60)
    rate = .55;
else
    rate = .77;
```

```java
int x = 2;

// if with no else
if (x < 3)
    System.out.println("true");
```

As a matter of safety, always use **{ }** to enclose statements in an **if..else**.
```java
int x = 5;

if (x < 3)
{
    System.out.println("true statement 1");
    System.out.println("true statement 2");
}
else
{
    System.out.println("false");
}
```
#### Nesting
You can nest **if..else** structures; that is, put them inside one another. The code below shows the **if..else** using ```if (y < z)``` nested inside the **if..else** using ```if (x < y)```.
```java
// nested if else statements
y = 5;
z = 6;
if(x < y)
{
    if (y < z)
    {
        System.out.println("true");
    }
    else
    {
        System.out.println("false");
    }
}
else
{
    System.out.println("true");
}
```
#### Multiple conditions using logical operators
You can have more than one condition by joining them with a logical operator.
##### These are the two logical operators:
* **&&** (AND)
* **||** (OR)

#### && (AND operator)
```java
x = 4;
y = 5;
z = 6;

if (x < y && y < z) {
    // actions go here
}
```
All conditions must be true when linked with **&&** for the entire condition to be true.

#### switch statement
The **switch** statement is used for many conditions. For example,
when you have to test for each state or different countries, or
many ages.

You *must* test an integer or character value.

Be sure to use the **break** keyword in each case.

Be sure to use the **default** keyword to catch other cases.


Code examples:
```java
int value;

switch(value)
{
    case 1:
        System.out.println("The value is one.");
        break;
    case 3:
        System.out.println("The value is three");
        break;
    case 6:
        System.out.println("The value is six");
        break;
    default:
        System.out.println("The value is I don't know");
}
```
```java
char letter;

switch (letter)
{
    case 'a':
        // etc
}
```

#### Relational and logical operators

##### The relational operators are:
* **==**, the *equals* operator
* **!=**, the *not equals* operator
* **>**, the *greater than* operator
* **<**, the *less than* operator
* **>=**, the *greater than or equal to* operator
* **<=**, the *less than or equal to* operator

These are used to compare two expressions and give a true or
false result.
