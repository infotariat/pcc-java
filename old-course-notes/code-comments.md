# Code comments

**Comments** are lines you add to the source code to document the program. Java ignores comment lines when it compiles the source code.
You can add comments to a Java program in three ways:
* single line
* multi-line
* javadoc

Single line comments begin with ```//```
Here is an example:
```java
// This is the Hello World Java program.
public class Test
{
    public static void main(String[] args) {
        System.out.println("Hello World");
    }
}
```
You can add multi-line comments like this:
```java
/* This is the Hello World
    Program */
public class Test
{
    public static void main(String[] args) {
        System.out.println("Helllo World");
    }
}
```
The last way to add comments is a special way for use with a program called **javadoc**. These are not discussed here.
```java
/** this is a javadoc comment. It starts with a slash and two
asterisks. */
```
Programs should **always** have comments that include the author, date, name of the program, and a description of the program.
```java
/*
    Program Name: Hello World
    Description: This program is the first Java program. It displays Hello World.
    Author: Terry Foty
    Date: May 25, 2003
*/
public class Test
{
    public static void main(String[] args) {
        System.out.println("Hello World");
    }
}
```
