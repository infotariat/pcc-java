# Objects First with BlueJ
## Chapter 3, Part 1

### Concepts
* Object interaction
* Creating cooperating objects

### Abstraction and modularization
* *Abstraction* is the ability to ignore details of parts to focus attention on a higher level of a problem.
* *Modularization* is the process of dividing a whole into well-defined parts, which can be built and examined separately, and which interact in well-defined ways.

### Modularizing the **clock** display
* One four-digit display?
* Or two two-digit displays?

### Implementation - **NumberDisplay**
```java
public class NumberDisplay
{
    private int limit;
    private int value;

    // Constructor and methods omitted.
}
```

### Implementation - **ClockDisplay**
```java
public class ClockDisplay
{
    private NumberDisplay hours;
    private NumberDisplay minutes;

    // Constructor and methods omitted.
}
```

### Diagrams (see slides)
* Class diagram
* Object diagram

### Objects using objects
* **House** project:
    * **Picture** uses **Circle**, **Square**, and **Triangle**.
* **Greeting** uses **String**.

```java
public class Project {
    private Sample plantSample;
    private Scientist owner;
    // ...
}
```

### Exercise
* In your **greetings** project, create a new class called **Event**.
* Create two fields in **Event** of type **Greeting** named **guest1** and **guest2**
* In the constructor, create two objects with **new**, for example:
```java
guest1 = new Greeting("Jane");
```
* Draw a picture of an **Event** object at run time.

### Data types in Java
* Every data type in Java is either an *object type* or a *primitive type*.
* There are 8 primitive types in the Java language.
* Every other type is an object type, defined in a class.
* Object type:
```java
SomeObject obj;
```
* Primitive type:
```java
int i;
```

### Primitive types vs. Object types
* See slides for diagrams, and how storage differs between the two types.
```java
Customer customer = new Customer();
int totalPoints = 100;
boolean active = true;
It it = new It();
```

### What will be the output?
* What will be the value of **b**?
```java
int a;
int b;
a = 15;
b = a;
a = a + 1;
System.out.println(b);
```
* What will be the value of **b** *this* time?
```java
Person a;
Person b;
a = new Person("Everett");
b = a;
a.setName("Don");
System.out.println(b.getName());
```

### Primitive vs. Object types
* See slides for diagrams demonstrating storage

### Quiz: what is the output?
```java
int x;
int y;
x = 32;
y = x;
x = x + 1;
System.out.println(y);
```
Another example:
```java
Person p1;
Person p2;
p1 = new Person("Molly");
p2 = p1;
p1.setName("Sachi");
System.out.println(p2.getName());
```

### Primitive types
* Integer types
    * **byte**
    * **short**
    * **int**
    * **long**
* Real number types
    * **float**
    * **double**
* Other types
    * **char**
    * **boolean**

### Primitive type variable declarations and initializations
```java
int total;
int num = 55;
int product = num * 10;
long numSeconds;
long bigNum = 10000000000L; // 10 billion
long id = 752348957398025L;

double interest;
double piApproximation = 3.14159;
double average = sum / 100.0;

boolean again;
boolean done = false;
```

### Primitive type exercises
* Declare (and initialize if asked) the following *local variables* in the method **public void calc()**
    1. An **int** named **number**
    2. A **long** named **milesDriven**
    3. A **double** named **epsilon** set to **0.00001**
    4. A **boolean** named **active** set to **true**
    5. An **int** named **x** set to **0**.
* Declare (and initialize if asked) the followinf fields in the class **HighSchool**
    1. A **boolean** named **first**
    2. A **double** named **gpa**
    3. An **int** named **numTracks** set to **10**

### The modulo operator
Consider this source code:
```java
public void increment()
{
    value = (value + 1) % limit; // What is the "%" sign all about?
}
```
* The *division* operator (**/**), when applied to **int** operands, returns the *result* of an *integer division*.
* The *modulo* operator (**%**) returns the *remainder* of an integer division.
* So, generally:
    * 17 / 5 gives result 3, remainder 2
* In Java:
    * 17 / 5 == 3
    * 17 % 5 == 2

### Integer arithmetic examples
* 10 % 3 = 1
* 11 / 5 = 2
* 12 % 6 = 0
* 3 / 8 = 0
* 3 % 8 = 3

### Modulo operator
* For integer **n >= 0**, what are all possible results of:
    * n % 5

### Source code: **NumberDisplay**
```java
public void increment()
{
    value = (value + 1) % limit;
}

public String getDisplayValue()
{
    if (value < 10) {
        return "0" + value;
    } else {
        return "" + value;
    }
}
```

### Exercise
* Create a class called **MathHelper** with an int field named **number**
* Write a constructor that takes a parameter and initializes **number**
* Write a method **getNumAsString** that returns **number** as a String
* Write a method called **square** that returns the square of a number
* Write a method **positive** that returns **true** if **number** is positive.
* Challenge: if you finish early, add the following to your **MathHelper** class:
    * A method called **reciprocal** that returns the reciprocal of **number** as a double
    * A method called **even** that returns **true** if **number** is even
    * A method called **multipleOf** that takes a parameter and returns **true** if **number** is a multiple of the parameter.
    * Rewrite **even** to use **multipleOf**

## Chapter 3, Part 2

### Objects creating objects
```java
public class ClockDisplay
{
    private NumberDisplay hours;
    private NumberDisplay minutes;
    private String DisplayString;

    public ClockDisplay()
    {
        hours = new NumberDisplay(24);
        minutes = new NumberDisplay(60);
        // ...
    }
}
```
* In the class **ClockDisplay**:
    * ``` hours = new NumberDisplay(24);```
        * Here **24** is an *actual* parameter
* In the class **NumberDisplay**:
    * ``` public NumberDisplay(int rolloverlimit) {}```
        * Here **rolloverlimit** is a *formal* parameter

### Creating objects - examples
* Use the **new** operator to create objects
```java
Square wall = new Square();
Project proj1 = new Project();
Car myCar = new Car("Toyota", 0);
```

### Creating objects - exercise
* Write a statement that creates
    * A **Square** object
    * A **Car** object with make "Ford" and 12000 miles
    * A **Qwerty** object (constructor takes no parameters)

### Calling a method on a different object
* aka *external method call*
* When no return value:
```
object.methodName(parameter-list);
```
* Java example:
```java
minutes.increment();
```

### Calling a method on the same object
* aka *internal method call*
* When no return value:
```
methodName(parameter-list)
```
* Java example:
```java
updateDisplay();
```
* No object name required
* Optional: use **this** as object:
```java
this.updateDisplay();
```

### Method calling
```java
public void timeTick()
{
    // external method calls
    minutes.increment();
    if (minutes.getValue() == 0) {
        // it just rolled over!
        hours.increment();
    }
    // internal method call
    updateDisplay();
}
```

### **null**
* **null** is a special value in Java
* An object variable that is **null** is not pointing to any object
* You can test for, and assign, **null**:
```java
hours = null;
if (hours != null) {
    // ...
}
```

### Field default values
* **Object** fields: **null**
* **Int** fields: **0**
* **Double** fields: **0.0**
* **Boolean fields: **false**

### this with fields
* When a parameter has the same name as a field, it overshadows the field.
* Use **this.fieldName** to refer to the field.
```java
public Dog {
    private String breed;
    public Dog(String breed) {
        this.breed = breed;
    }
    // The "breed" in "this.breed" is a field
    // The "breed" on the right side of the "=" is a parameter
}
```
* Use this technique in *setters*, too!

### Logical operators
* Source code: NumberDisplay
```java
public void setValue(int replacementValue)
{
    if ((replacementValue >= 0) &&
        (replacementValue < limit)) {
            value = replacementValue;
        }
}
```
* \&\& i.e. "and", *both* conditions true
* || i.e. "or", *either* condition true
* ! i.e. "not", condition *not true*
* Examples
    * ``` (age >= 18) && validID```
    * ``` (num < 1) || (num > 100)```
    * ``` !done ```
    * ``` (cat != null) && !cat.isPersian()```

### Logical operators exercise
* Write a boolean expression for each condition:
    * **Int** variable **temp** is greater than 70 and less than 80
    * **MathHelper** variable **m** is not positive (use the **positive** method)
    * **Double** variable **amount** is greater than zero or **boolean** variable **override** is true.
