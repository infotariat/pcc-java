# Objects First BlueJ: Personal Notes
## Chapter 3

### Main concepts
* Abstraction
* Modularization
* Object creation
* Object diagrams
* Method calls
* Debuggers

### Java constructs discussed in this chapter
* class types
* logic operators (**&&**, **||**)
* string concatenation
* modulo operator (**%**)
* object construction (**new**)
* method calls (dot notation)
* **this**

### 3.1 The clock example
This chapter discusses object interaction. Our project will be a display for a digital clock.

The display will show hours and minutes, separated by a colon. We start with a 24-hour clock. The display will go from "00:00" to "23:59". Later we think about the 12-hour implementation.

### 3.2 Abstraction and modularization
We want to break problems down into smaller components that can be turned into separate classes. *Abstraction* is the tool we use to deal with complexity. Once the problems within the smaller components are dealt with those components then become "building blocks" and we don't have to think about their details. We refer to this technique as *divide and conquer*.

**Concepts**
* **abstraction**: the ability to ignore details of parts, to focus attention on a higher level of a problem.
* **modularization**: the process of dividing a whole into well-defined parts  that can be built and examined separately and that interact in well-defined ways.

Abstraction and modularization complement each other.

### 3.3 Abstraction in software
In object-oriented programming the components and subcomponents we're talking about are *objects*. Taking a car as an example, we would start not by thinking of one overall car but by constructing separate objects for the different parts of a car and then building the *car object* from these smaller objects.

### 3.4 Modularization in the clock example
How should we view the display? We can think of it as one single display showing the whole time (i.e. all four digits of display), or we can think of it as two two-digit displays. We're going with the latter. So the main object we're modeling is a two-digit display.

The plan is to create a class for a two-digit display and then give it an accessor method (to get its value) and two mutator methods (one to set its value and the other to increment it). We will create two objects of this class to build the full display.

### 3.5 Implementing the clock display
We start with a number display. It needs to store two values: the limit (before rolling over to "00"), and the current value. These will be integer fields.
```java
public class NumberDisplay
{
    private int limit;
    private int value;

    // constructor and methods omitted.
}
```
Now that we have this basic structure in mind we can just assume we can build it, and we can focus on the clock display. We're going to use objects of the **NumberDisplay** class as fields for the **ClockDisplay** class.
```java
public class ClockDisplay
{
    private NumberDisplay hours;
    private NumberDisplay minutes;

    // Constructor and methods omitted.
}
```
**Concept**
* **classes define types**: A class name can be used as the type for a variable. Variables that have a class as their type can store objects of that class.

### Class diagrams versus object diagrams


**Concepts**
* **class diagram**: shows the classes of an application and the relationships between them. It gives information about the source code and presents the static view of a program.
* **object diagram** shows the objects and their relationships at one moment in time during the execution of an application. It gives information about objects at runtime and presents the dynamic view of a program.
* **object references**: Variables of *object types* store references to objects.

### 3.7 Primitive types and object types
Primitive types are your basic types like **int**, **boolean**, etc. Object types are either provided by Java's library (like the **String** class) or provided when we write them ourselves. Primitive types have no methods.

Primitive values are stored directly in the variable. Objects are not stored in a variable - instead, a reference to the object is stored. We draw these references as arrows in our diagrams.

### 3.8 The ClockDisplay source code
Let's start with the implementation of **NumberDisplay**. The class has two fields, one constructor, and four methods:
* **getValue**
* **setValue**
* **getDisplayValue**
* **increment**

The constructor receives the roll-over limit as a parameter. That way we can use the same class for minutes and hours (because the parameter handles the job of setting the limit, to 24 or 60 or whatever else one might want). The constructor stores that roll-over limit in a field and sets the current value to 0.
```java
/**
 * The NumberDisplay class represents a digital number
 * display that can hold values from zero to a given limit.
 * The limit can be specified when creating the display. The
 * values range from zero (inclusive) to limit-1. If used, for
 * example, for the seconds on a digital clock, the limit
 * would be 60, resulting in display values from 0 to 59.
 * When incremented, the display automatically rolls over to
 * zero when reaching the limit.
 * @author Michael Kolling and David J. Barnes
 * @version 2011.07.31
 */
 public class NumberDisplay
 {
     private int limit;
     private int value;

     /**
      * Constructor for objects of class NumberDisplay
      */
     public NumberDisplay(int rollOverLimit)
     {
         limit = rollOverLimit;
         value = 0;
     }

     /*
      * Return the current value.
      */
     public int getValue()
     {
         return value;
     }

     /**
      * Set the value of the display to the new specified
      * value. If the new value is less than zero or over the
      * limit, do nothing.
      */
     public void setValues(int replacementValue)
     {
         if((replacementValue >= 0) &&
                (replacementValue < limit)) {
                    value = replacementValue;
                }
     }

     /**
      * Return the display value (that is, the current value
      * as a two-digit String. If the value is less than ten,
      * it will be padded with a leading zero).
      */
     public String getDisplayValue()
     {
         if(value < 10) {
             return "0" + value;
         } else {
             return "" + value;
         }
     }

     /**
      * Increment the display value by one, rolling over to zero if
      * the limit is reached.
      */
     public void increment()
     {
         value = (value + 1) % limit;
     }
 }
```

### String concatenation


### The modulo operator

### 3.8.4 Class ClockDisplay
This class creates two number displays to create a full time display.
```java
/**
 * The ClockDisplay class implements a digital clock display
 * for a European-style 24-hour clock. The closk shows hours
 * and minutes.
 * The range of the clock is 00:00 (midnight) to 23:59 (one
 * minute before midnight).
 * The clock display receives "ticks" (via the timeTick
 * method) every minute and reacts by incrementing the
 * display. This is done in the usual clock fashion: the hour
 * increments when the minutes roll over to zero.
 * @author Michael Kolling and David J. Barnes
 * @version 2011.07.31
 */
 public class ClockDisplay
 {
     private NumberDisplay hours;
     private NumberDisplay minutes;
     private String displayString; // simulates the actual display

     /**
      * Constructor for ClockDisplay objects. This constructor
      * creates a new clock set at 00:00.
      */
     public ClockDisplay()
      {
          hours = new NumberDisplay(24);
          minutes = new NumberDisplay(60);
          updateDisplay();
      }
      /**
       * Constructor for ClockDisplay objects. This constructor
       * creates a new clock set at the time specified by the
       * parameters.
       */
      public ClockDisplay(int hour, int minute)
      {
          hours = new NumberDisplay(24);
          minutes = new NumberDisplay(60);
          setTime(hour, minute);
      }
      /**
       * This method should only get called once every minute - it
       * makes the clock display go one minute forward.
       */
       public void timeTick()
       {
           minutes.increment();
           if (minutes.getValue() == 0) { // it just rolled over!
               hours.increment();
           }
           updateDisplay();
       }
       /**
        * Set the time of the display to the specified hour and
        * minute.
        */
        public void setTime(int hour, int minute)
        {
            hours.setValue(hour);
            minutes.setValue(minute);
            updateDisplay();
        }
        /**
         * Return the current time of this display in the format
         * HH:MM
         */
         public String getTime()
         {
             return displayString;
         }
         /**
          * Update the internal string that represents the
          * display.
          */
         private void updateDisplay()
         {
             displayString = hours.getDisplayValue() + ":" +
                             minutes.getDisplayValue();
         }
}
```
