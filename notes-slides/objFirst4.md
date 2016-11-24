# Objects First with BlueJ

## Chapter 4, Part 1
Introduction to collections

### Chapter 4 topics
* Class libraries
* Collections, arrays
* Loops, iterators

### Class libraries aka API
* Useful classes
* We don't have to write everything from scratch
* Java class libraries are organized into *packages*
* Grouping objects is a recurring requirement
    * The **java.util** package contains collection classes
* **java.lang** included automatically in every Java program
    * String
    * Integer
    * System
* **java.util** must be imported
    * ArrayList
    * Date
    * Set

### String API exercise
* Create a String in CodePad:
```java
String s = "Hi there";
```
* Call methods on it and observe the results.
    * toUpperCase: **s.toUpperCase()**
    * toLowerCase
    * length
* Consult the API: what method tells whether a string starts with a certain prefix? Call it.

### The requirement to group objects
* Many applications involve collections of objects:
    * Personal organizers
    * Library catalogs
    * Student-record system
* The number of items to be stored varies.
    * Items added
    * Items deleted

### Without collections
```java
private String name1;
private String name2;
private String name3;
// ...
public void setUpNames()
{
    name1 = new String("Friendly");
    name2 = "Snowball"; // alternate syntax for creating a string
    name3 = "Max";
}
```
* Consult course slides for storage visualization

### Collections with **ArrayList**
* Declare a collection variable:
```java
ArrayList<String> catNames;
```
* Create a collection:
```java
catNames = new ArrayList<String>();
```

### Source code example
```java
import java.util.ArrayList;
// docstring or whatever they call it in Java
public class MusicOrganizer
{
    // Storage for an arbitrary number of file names.
    private ArrayList<String> files;

    // Perform any initialization required for the organizer
    public MusicOrganizer()
    {
        files = new ArrayList<String>();
    }
}
```

### Names exercise
* Create a class called **Names**
* Import **java.util.ArrayList**
* Add a field called **catNames** that is an **ArrayList** of **String**
* In the constructor, assign a **new ArrayList** of **String** to **catNames**
* Add a method **printNames** that prints cat names:
```java
System.out.println(catNames);
```

### Collections with **ArrayList**, continued
* Add to a collection:
```java
catNames.add("Friendly");
catNames.add("Snowball");
catNames.add("Max");
// with each addition, the ArrayList grows to contain more Strings
```
* Get the size of a collection:
```java
int numNames = catNames.size();
```
* Get an element of a collection:
```java
String firstName = catNames.get(0);
```

### Names exercise, continued
* Add a method called **setUpNames** that adds 3 names to **catNames**
* Add a line to **printNames** that prints the *number* of cat names (use the **size** method)
* Add the following method that prints the name at the specified index:
```java
public void printNameAtIndex(int index)
{
    // actions go here
}
```
* *What happens if you try to print an index that doesn't exist?*

### Challenge Names exercise
* Make **printNameAtIndex** print the name's index and then the name (e.g. "2: Max")
* Add a method called **addName** that allows the user to add names to the end of the list
    * What parameter(s) should the method take?
* Look up the **clear** method on **ArrayList** and add a method to **Names** called **clearNames** that clears the list of names.
