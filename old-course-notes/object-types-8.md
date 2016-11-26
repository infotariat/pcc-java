## Object types
##### Number 8 in series of old course notes

#### Object types in Java
Suppose you have a class named **Dog** defined like this:
```java
public class Dog
{
    public Dog()
    {
        // code etc...
    }
}
```
To create a new object from a class, the general formula is:

``` classname objectname = new classname();```

Or, in this example, since you want to create an object from class **Dog**:

``` Dog d = new Dog();```

This will create a new object from class **Dog** in memory.

##### In fact, two different things are created in memory:
* An object reference
* The actual object

``` Dog d``` creates the object reference.

``` new Dog();``` creates the actual object. It is the **new** keyword that actually causes
the object to be created in memory.

The two parts are related in that the object reference contains the memory address of the
object. Other languages (C, C++) call this a *pointer*, but Java does not use that term.

You can create the object reference at an earlier time and later create the actual object,
like this:
```java
Dog d;
d = new Dog();
```

By the way, *primitive* types, such as **int**, **long**, **float**, **double**, etc., are
not created this way. Primitive types simply exist in memory as variables. They do not have
an object reference since they are not objects.

Recap: any time you create an object it exists in two components: object reference, and object.
