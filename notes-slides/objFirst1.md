# Objects First with BlueJ
---
## Chapter 1
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
