## Methods
##### Number 6 in the series of old instructor notes

#### Objectives
* Create a method with arguments
* Create a method with return value
* Use method arguments
* Use the return keyword
* Use the static keyword
* Write and invoke static methods

#### Anatomy of a method
A *method* is aseries of statements (a section of code) that does a certain
job. Methods follow a certain format.

##### A method must have these three parts:
* Header
* Starting and ending curly braces
* Body

Here is a simple method:
```java
public static void main(String[] args) // header
{                                      // start brace
    System.out.println("Hello.");      // body
    System.out.println("Welcome to Java.");
}                                      // end brace
```
##### The method header contains:
* The name of the method
* The return type
* An access modifier
* Any arguments (optional)

```java
public static void main(String[] args)
{
    // code goes here
}
```

#### Arguments
The header contains any arguments. An argument is a value that is sent into
the method. Arguments are optional. Arguments are enclosed in parentheses.
Parentheses are required, even if there are no arguments:
```java
public static void main(String[] args) {
    // etc...
}

private int display() {
    // etc...
}
```
More than one argument can be sent to a method. Separate argument by a comma:
```java
public void add(int x, int y) {
    // etc...
}
```
#### How to design a method
When designing a method, think of it as a box where one or more pieces of data
enter (*inputs*) and one piece of data exits (*output*). Inside the box, the method transforms the input into the output.

##### Steps in designing a method
* Explain what the method should do, in simple terms.
* Determine the output and its data type, and give it a name.
* Determine the inputs, how many will be needed, and their data types, and give them names.
* Determine the *algorithm*, or *recipe*, that changes the input(s) into the output, and give the method a name.
* Implement the method in Java.

##### Simple example: adding two numbers
* step one:
```
This method should add two numbers and give the result.
```
* step two:
```
The output should be a double. I'll name it sum.
```
* step three:
```
The method needs to accept two numbers to add.
They should both be doubles.
Their names will be x and y.
```
* step four:
```
The method should be called add.
The algorithm is:
    Get the numbers.
    Add the numbers.
    Return the result.
```
* step five:
```java
public double add(double x, double y)
{
    double answer;
    answer = x + y;
    return answer;
}
```
An easier implementation:
```java
public double add(double x, double y)
{
    return x + y;
}
```

#### Static methods
Review: a *method* is a programming unit that performs a specific
task.
##### There are two categories of methods:
* *static* (also called class methods)
* *instance* (also called object methods)

#### The difference between a static method and an instance method
A *static method* does not need an object in order to be invoked (called). Static methods are
also called *class methods*. This section only discusses static methods; instance methods
are covered later in the course.

#### How to declare a static method
Methods always have to be declared inside a class. To declare a method as static, simply
use the **static** keyword in the method definition:
```java
public class Employee
{
    public static int getAge()
    {
        // code goes here
    }
}
```
#### How to invoke a static method from another method
A static method is invoked by specifying its name preceded by the class it is defined
in. Notice in the code below how the *classname.methodname* is used to invoke a static
method. Methods always have to be invoked from another method:
```java
public static void main(String[] args) {
    Employee.getAge(); // invoking the method
}
```
#### How to pass arguments to a method
Static methods can be written to accept any number of *arguments* (or no arguments). An
argument is simply a value passed to a method. For instance, if you had a method that could
add two numbers, the two numbers you actually want to add would be passed to the method
as arguments. The arguments passed to the method must specify a data type and a name. You
can pass any types and number of arguments, and you can pass arguments of different types:
```java
public static double addTwo(double x, double y)
{
    return x + y;
}
```
#### How to return a value from a method
In the example above, notice that the method returns the result of the addition. A method
can only return one value. This is called a *return value*. It is done by using the **return**
keyword: ```return x + y;```

#### How to create a method that does not return a value
A method does not have to return a value. In this case, use the **void** keyword:
```java
public static void aMethod()
{
    // code goes here
}
```

#### How to invoke methods
When you invoke a method, you must match the number and types of arguments it expects. For
example, in the **addTwo** method above, it expects two **double** values. That is what
you must send to the method. It is always an error if you do not do this.
```java
public class Test
{

    public static void main(String[] args)
    {
        double a = 5;
        double b = 66;
        double result;

        result = addTwo(a, b);
    }

    public static double addTwo(double x, double y)
    {
        return x + y;
    }
}
```
#### How to capture the return value of a method
For a method that returns a value, the calling method needs to capture it. Again, we use
the **addTwo** method as an example. Notice in the code for **Test** how the variable
**result** is used to capture the return value from **addTwo**.
