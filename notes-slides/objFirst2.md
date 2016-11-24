# Objects First with BlueJ
---
## Chapter 2, Part 1
### Main concepts to be covered (Part A)
* fields
* constructors
* methods
* parameters
* assignment statements

### Ticket machines - an external view
* Exploring the behavior of a typical ticket machine
* Using **naive-ticket-machine** project
    * Machines supply tickets of fixed price.
    * How is that price determined?
    * How is money entered into a machine?
    * How does a machine keep track of the money that is entered?

### Ticket machines - an internal view
* Interacting with an object gives us clues about its behavior
* Looking inside allows us to determine how that behavior is provided or implemented

### Basic class structure
```java
public class TicketMachine
{
    // Inner part omitted
}

public class ClassName
{
    // Fields
    // Constructors
    // Methods
}
```

### Keywords with a special meaning in Java
* **public**
* **class**
* **private**
* **int**
* These are also known as *reserved words*

### Fields
* Fields store value in an object.
* They are also known as *instance variables*.
* Fields define the state of an object.
* Use **Inspect** to view the state.
* Some values change often.
* Some change rarely, or not at all.

```java
public class TicketMachine
{
    private int price;
    private int balance;
    private int total;
}
```

### Constructors
* Constructors initialize an object.
* They have the same name as their class.
* They have a close association with fields.
* They store initial values into fields.
* External parameter values for initializing fields.

```java
public TicketMachine(int cost)
{
    price = cost;
    balance = 0;
    total = 0;
}
```

### Methods
* Methods implement the behavior of objects.
* Methods have a consistent structure comprised of a *header* and a *body*.

```java
public int getPrice()
{
    return price;
}
```

### Variables
* Instance variables, aka *fields*
* Class variables, i.e. *static fields*
* Parameters
* Local variables

### Choosing variable names
* Lots of freedom of choice in creating names, but use wisely.
* Choose expressive names to make code easier to understand:
    * **price**
    * **firstName**
    * **numGuests**
* Avoid single letter, cryptic names
    * **w**
    * **t5**
    * **next**

### Scope and lifetime of variables
* Scope - the section of source code from which the variable can be accessed.
* Lifetime - how long the variable continues to exist before it is destroyed.
    * Fields - exist for the life of the object
    * Parameters - exist only during method execution

### Assignment
* Values are stored into fields (and other variables) via assignment statements:
    * *variable = expression;*
    * **price = cost;**
* A variable stores a single value, so any previous value is lost.

### Main concepts to be covered (Part B)
* More on methods
    * Accessor methods
    * Mutator methods
    * Return statements
* Printing
* String concatenation

### Types of methods
* Methods implement the behavior of objects
* *Accessor methods* provide information about an object.
* *Mutator methods* alter the state of an object.
* Other sorts of methods accomplish a variety of tasks.

### Method structure
* The header provides the method's *signature*:
    * **public int getPrice()**
* The header tells us:
    * The name of the method
    * What parameters it takes
    * Whether it returns a result
    * Its visibility to objects of other classes
* The body encloses the method's statements.

### Accessor methods
* A method that simply returns the value of a field is a *getter*.
* An accessor method always has a return type that is not **void**.
* An accessor method returns a value *(result)* of the type given in the header.
* The method will contain a **return** statement to return the value.
* Remember: returning is *not* printing!

### Mutator methods
* Have a similar method structure: *header* and *body*.
* Used to *mutate* (i.e., change) an object's state.
* Achieved through changing the value of one or more fields.
    * Typically contain assignment statements.
    * Often receive parameters.

```java
public void insertMoney(int amount)
{
    balance = balance + amount;
}
```

### **set** mutator methods
* Fields often have dedicated **set** mutator methods, known as *setters*.
* These have a simple, distinctive form:
    * **void** return type
    * method name related to the field name
    * single parameter, with the same type as the type of the field
    * a single assignment statement

### A typical **set** method
```java
public void setDiscount(int amount)
{
    discount = amount;
}
```

### Protective mutators
* A **set** method does not have to assign the parameter to the field.
* The parameter may be checked for validity and rejected if inappropriate.
* Mutators thereby protect fields.
* Mutators support *encapsulation*.

### Printing from methods
```java
public void printTicket()
{
    // Simulate the printing of a ticket
    System.out.println("###################");
    System.out.println("# The BlueJ Line ");
    System.out.println("# Ticket");
    System.out.println("# " + price + " cents.");
    System.out.println("###################");
    System.out.println();

    // Update the total collected with the balance.
    total = total + balance;
    // Clear the balance.
    balance = 0;
}
```

### Method Summary
* Methods implement all object behavior.
* A method has a name and a return type.
    * The return type may be **void**.
    * A non-**void** return type means the method will return a value to its caller.
* A method might take parameters.
    * Parameters bring values in from outside for the method to use.

### Exercise
* Create a class called **Greetings**.
* Add a **String** field called **name**.
* Add a constructor that takes a parameter **newName** and uses it to initialize **name**.
* Add a method called **hello** that takes no parameters and prints "Hello, **name**!", substituting the name.
* Add a method called **goodbye** that prints "Bye, **name**!"

## Chapter 2, Part 2

### Main concepts to be covered
* Conditional statements
* Local variables
* Calling methods

### Reflecting on the ticket machines
* Their behavior is inadequate in several ways:
    * No checks on the amounts entered
    * No refunds
    * No checks for a sensible initialization
* How can we do better?
    * We need more sophisticated behavior.

### Making choices in everyday life
* If I have enough money, I go for a meal
* Otherwise I stay home and watch a movie.

```
if (I have enough money left) {
    go for meal;
} else {
    stay home and watch movie;
}
```

### Making choices in Java
```
if (perform some test) {
    Do these statements if test returned true
} else {
    do this, i.e. if test returned false
}
```

### Making a choice in the ticket machine
```java
public void insertMoney(int amount)
{
    if (amount > 0) {
        balance = balance + amount;
    } else {
        System.out.println(
            "Use a positive amount: " +
            amount
        );
    }
}
```

### Exercise
* In the **Greeting** class:
    * Add a method called **checkAge** that takes an **int** parameter **age** and prints either
        * Eligible to vote
    * or
        * Too young to vote
    * Assume that 18 is the voting age.
* Extra: if too young to vote, print the number of years remaining until eligible.
* Extra: If age entered is negative, print an error

### Variables: a recap
* Fields are one sort of variable:
    * They store values through the life of an object.
    * They are accessible throughout the class.
* Parameters are another sort of variable:
    * They receive values from outside the method.
    * They help a method complete its task.
    * Each call to the method receives a fresh set of values.
    * Parameter values are short lived.

### Local variables
* Methods can define their own, *local* variables:
    * Short-lived, like parameters.
    * The method sets their values - unlike parameters, they do not receive external values.
    * Used for "temporary" calculation and storage.
    * They exist only as long as the method is being executed (*Lifetime*).
    * They are only accessible from within the method (*Scope*).
* A local variable:

```java
public int refundBalance()
{
    int amountToRefund;
    amountToRefund = balance;
    balance = 0;
    return amountToRefund;
}
```
Notice the lack of a visibility modifier in the line
```int amountToRefund;```
which declares the *local* variable.

### Exercise
* In your **Greeting** class, modify the **hello** method as follows:
    * Create a local variable of type **String** called **greetingString**
    * Set **greetingSTring** equal to the string you want to print, such as "Hello, **name**!"
    * Change the print statement to print the variable **greetingString**
* Extra: do the same with **goodbye**

### Review: classes
* Classes contain:
    * Fields - store values that determine an object's *state*.
    * Constructors - initialize objects, particularly their fields.
    * Methods - implement the behavior of objects.

### Review: variables
* Types of variables include:
    * Fields - store an object's state, persist for the lifetime of the object.
    * Parameters - used to receive values into a constructor or method.
    * Local variables - used for short-lived temporary storage.

### Calling methods
* To call a method on the same object:
    * If the method returns a value:
```java
ReturnType var = methodName(params);
```
    * If the method does not return a value:
```java
methodName(params);
```
* To call a method on a different object:
    * If the method returns a value:
```java
ReturnType var = object.methodName(params);
```
    * If the method does not return a value:
```java
object.methodName(params);
```

### Exercise
* In your **Greeting** class, modify the **checkAge** method as follows:
    * Call the **hello** method to print a greeting, *then* print the voting message.
* Extra: call **goodbye** after printing the voting message.
