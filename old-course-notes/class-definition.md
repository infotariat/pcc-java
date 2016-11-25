# The structure of a Java class definition
A Java program consists of one or more *class definitions*. Every class
definition has the same basic structure. After reading this document you
should be able to identify the components of any Java class definition.

##### Class wrapper
The class wrapper consists of the *class header* and the *class body*.

##### Class header
Three things are specified by the class header:
* the access modifier **public**
* the keyword **class**
* the name of the class (**Course**, below)

```java
public class Course // class header
{ // <-- begin class body
    // class fields
    private String instructor;
    private String room;
    private String timeAndDay;
    private List<Student> students;
    private int capacity;

    public LabClass(int maxNumberOfStudents)
    {
        instructor = "unknown";
        room = "unknown";
        timeAndDay = "unknown";
        students = new ArrayList<Student>();
        capacity = maxNumberOfStudents;
    }

    public int numberOfStudents()
    {
        return students.size();
    }
    // --> end class body
}
```
##### Class body
The class *body* above consists of everything between the first bracket
and the last bracket.

##### Class fields
The class *fields* are always listed immediately after the first bracket.
A field consists of:
* An access modifier (**private** or **public**)
* A data type
* The name of the field

##### Class methods
Immediately after the fields, the methods are listed.
A method consists of:
* The method header
* The body of the method

##### Method header
The method header consists of:
* The access modifier (**public** or **private**)
* The return type or the keyword **void**
* The method name
* A pair of parentheses
* Input *parameters*

```java
public void setUp(int maxNumberOfStudents) // method header
{
    // method body
    instructor = "unknown";
    room = "unknown";
    timeAndDay = "unknown";
    students = new ArrayList<Student>();
    capacity = maxNumberOfStudents;
}
```

##### Method body
The method body consists of everything between the beginning and ending brackets.
