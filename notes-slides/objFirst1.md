# Objects First with BlueJ
---
## Chapter 1
### Main concepts to be covered (part A)
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