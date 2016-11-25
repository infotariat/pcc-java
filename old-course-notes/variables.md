# Variables

### Definition
A *variable* is a location in memory (RAM) that is used to store and retrieve data.

### Declaring a variable
To declare a variable, choose a name for it and then select a data type.

### Choosing a name for the variable
* Stick with letters (upper or lowercase), digits (0-9) or the underscore.
* Don't use spaces, special characters (*, &, !, etc.) when you name your variable.
* Don't start the name with a digit.
* Don't use a reserved word (keyword).

##### Some legal names for variables
* age
* rate
* city
* population
* lastName
* firstName
* birthDate
* zipcode

##### Some illegal names
* 123
* 12x
* 12age
* last name
* first Name
* last&name
* @age

The Java compiler will complain if you use an illegal name.

### Choosing a data type for the variable.
Data comes in different types: *numeric*, and *text*.
Numeric data can be either:
* positive and negative whole numbers (e.g. 35, 0, 2789), or
* positive and negative decimal numbers (e.g. 29.99, 545436.44, 3.14159)

Text data consists of one or more characters (e.g. Larry, 121 Main Street, A1Moving)

Each of these types of data is stored in RAM memory in its own format. Whole numbers
are not stored like decimal numbers. Text data is not stored like whole numbers. For this
reason, you have to choose a data type for the data you will store in the variable. That is
so Java knows what format to use.

**Warning!** If you declare a variable of one data type and try to store data of a
different type in it, you will get an error.

Java provides a data type for each kind of data.
The choices for numeric data are:
* int
* long
* float
* double

The choices for text data are:
* String
* char

By the way, Java provides other data types but they are not discussed here.

### What type of variable to use
The type of variable you use depends on your data.
Here is a guide:
* If the data is only whole numbers (positive or negative) use either the **int** or **long** types.
* If the data will be decimal numbers (positive or negative) use either the **float** or **double** types.
* If the data is a series of characters use the **String** type.
* If the data is one character use the **char** type.

**Note**: Always use **String** for social security number, street, phone number, and zipcode (becuase
these are considered text data).

### Code samples
Now let's see some snippets of Java code that declare and use variables.
Use the **int** or **long** type to store whole numbers.
```java
int x;
int y;
int z;
x = 5;
y = 4;
z = x + y;
```
Use the **double** or **float** type to store decimal numbers.
```java
double d;
double k;
double z;
d = 456.789;
k = -12.34;
z = d + k;
```
Use the **String** type to store a series of characters.
```java
String lastName;
String firstName;
String SSN;
String zipcode;
lastName = "Nguyen";
firstName = "Ken";
SSN = "122456789";
zipcode = "97222";
```
Use the **char** type to store just one character.
```java
char c;
c = 'G';
```

### Review questions
* What are the two categories of data discussed here?
* What data types can be used to hold a decimal value such as 3.145?
* What data type is used to hold **zipcode**?

##### Answers
* *numeric* and *text*
* **float** or **double**
* **String**
