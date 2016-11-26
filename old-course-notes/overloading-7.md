## Method overloading
##### Number 7 in old course notes
#### Objectives
* Overload a method
* Overloading constructors
* **this** reference

#### Overloading methods
##### How to define overloaded methods
You can define more than one method with the same name. This is called *method overloading*.
Both class and instance methods can be overloaded.

Overloading does pose a problem: when you invoke a method, you use its name. So if two
methods have the same name, how does Java know which one it should use? This problem
is solved by making each overloaded method have its own *signature*.

##### A method signature is determined by:
* The number of arguments passed to it
* The types of the arguments

Here is a method named **multiply**. It accepts two arguments, both **double**. The portion
within the parentheses is the signature:
```java
public static double multiply(double x, double y)
{
    return (x * y);
}
```
Here is another method, also named **multiply**, but its signature is different:
```Java
public static double multiply(double x, double y, double z)
{
    return (x * y * z);
}
```
Java can tell these two methods apart by their signatures. They are different, in this case,
because the number of arguments is different (two vs. three).

Methods with different types on the arguments also have different signatures. Consider this
example, where both methods have two arguments, but the types are different:
```java
public static long multiply(long x, double y)
{
    return (x * y);
}

public static long multiply(int x, long y)
{
    return (x * y);
}
```
#### How to use overloaded methods
Use an overloaded method just like you would any other method. Java will determine which
overload to use based on the signature of the method. Using the above example, with the
two **multiply** methods, Java will choose the second **multiply** method because
**multiply** is invoked with **int** and **long** arguments:
```java
public static void main(String[] args)
{
    int a = 5;
    long b = 55;
    long result = 0;

    result = multiply(a, b);
}
```
In this example, Java chooses the first **multiply** method:
```java
public static void main(String[] args)
{
    double a = 5;
    long b = 55;
    long result = 0;

    result = multiply(a, b);
}
```
The next example would cause an error, because there is no overloaded method that matches
the call:
```java
public static void main(String[] args)
{
    double a = 5;
    double b = 55;
    long result = 0;

    result = multiply(b, a); // two doubles, causes error
}
```
This next example also causes an error, because there is no matching method:
```java
public static void main(String[] args)
{
    double a = 5;
    double b = 55;
    int x = 66;
    long result = 0;

    result = multiple(x, b, a);
}
```
