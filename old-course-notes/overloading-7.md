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
Note that all of these examples use static methods, but instance methods can also be
overloaded in the same way.

#### Overloading constructors
##### How to define overloaded constructors
You can define more than one constructor with the same name. If there is more than one
constructor in a class, Java uses the signature to decide which one to use.

Here is a class with two constructors, each with different signatures:
```java
public class Employee
{
    private String lastName;
    private String firstName;
    private int age;

    public Employee(String l, String f, int a)
    {
        lastName = l;
        firstName = f;
        age = a;
    }

    public Employee(String l, String f)
    {
        lastName = l;
        firstName = f;
    }
}
```
##### How to use overloaded constructors
Use overloaded constructors just as you would any other constructors. Java will use the
signature to figure out which one to use. In the following example:
* For the **emp** object, Java uses the second constructor in the **Employee** class.
* For the **emp2** object, the first constructor is used.
```java
public static void main(String[] args)
{
    Employee emp = new Employee("Jones", "Ed");
    Employee emp2 = new Employee("Nguyen", "Cathy", 29);
}
```

It is an error if you try to create an object that lacks a matching constructor,
as we see below:
```java
public static void main(String[] args)
{
    Employee emp = new Employee("Jones"); // no matching constructor, ERROR
}
```

#### this reference
The **this** reference points to the object being used. It is not normally needed,
but when using accessor and mutator methods, it can be used.

Consider this example: it is the **Employee** class with accessor and mutator methods
for the **lastName** variable. Notice the **setLastName** method. It is sent a **String**
which we call **s**. **s** is assigned to the **lastName** variable. Java can understand this.
```java
public class Employee
{
    private String lastName;
    private String firstName;
    private int age;

    // mutator method for lastName variable
    public void setLastName(String s)
    {
        lastName = s;
    }

    // accessor method for lastName variable
    public String getLastName()
    {
        return lastName;
    }
}
```

But what if we named the variable **lastName** instead of **s**, as in the following
example?
```java
public class Employee
{
    private String lastName;
    private String firstName;
    private int age;

    // mutator method for lastName variable
    public void setLastName(String lastName)
    {
        lastName = lastName; // UH OH!
    }

    // accessor method for lastName variable
    public String getLastName()
    {
        return lastName;
    }
}
```
Now Java will be confused when presented with the assignment statement ```lastName = lastName;```

To eliminate the confusion, you could use **this** reference:
``` this.lastName = lastName;```

Now the complete example would look like this:
```java
public class Employee
{
    private String lastName;
    private String firstName;
    private int age;

    // mutator method for lastName variable
    public void setLastName(String lastName)
    {
        this.lastName = lastName; // UH OH!
    }

    // accessor method for lastName variable
    public String getLastName()
    {
        return lastName;
    }
}
```
The **this** reference means "the current object." So **this.lastName** means the **lastName**
variable of the current object. 
