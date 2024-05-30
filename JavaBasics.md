## What is Java?

Java is a object oriented programming language developed by sun microsystems in the year 1991, It was built on the idea of platform independent which means java programs can run anywhere or any OS which has Java virtual machine (JDK) installed in it.

## Here's the breakdown of how java works:

- Write once run anywhere (WORA) : When a Java code is executed it is first converted into byte code. This byte code is compatible with every device which has a JVM installed in it.

- Compilation : When ever a java code is executed the .java extension file is converted into .class file (bytecode file).

- Java Virtual machine (JVM) : JVM converts this bytecode into machine code.

- Object oriented : Java is a object oriented language which means each and every block of code is written using classes and objects.

## Hello World in Java

```Java
	public class HelloWorld {
    public static void main(String[] args) {
        System.out.println("Hello, World!");
    }
}
```

- Here is the block of code in which a class is declared by the name HelloWorld. 
- Inside which a main method is declared, each and every program in Java should have a main method in it. Which is the entry point of the program.
- main method has an argument called as args which is a array of string
- System.out.println("Hello World") prints hello world on the console.

## Comments

```Java
// Single Line Comment

/*
	Multiline comments
*/
```
## Variables and Data types

- Variables are containers in which certain data is stored within a program.
- It mainly comprises of datatype, name and value.

```Java
int a;
a = 10
	OR
int a = 10;
```

### Literals
- In any programming language Literals are fixed value in the program.
- Literals can be declared using primitive data types and "string".
- We can also modify a literal variable

```Java
int a = 10;
float b = 3.142
String c = "Hello World!"
```

### Data types
- Data types are the keywords which are used to specify what type of data is being stored in the variable.
- There are 8 data types which are pre-defined in java which are also called as primitive data types.
	   1. boolean
	   2. byte
	   3. short
	   4. int
	   5. long
	   6. double
	   7. float 
	   8. char

1. Boolean :  Boolean is a data type which is associated with only two values which is either true or false
```Java
	boolean a = true
	boolean b = false
```

3. byte :  Byte is a data type which is used to store numerical values within a given range of -128 to 127. Its default value is zero.
 ```Java
	 byte a = 100 
 ```
 
 3. short :  Short is a data type which is also used to store numerical values within the range of  -2^7 to 2^7-1, If the values lie between this range then short data type is used.
```Java
	short a = 30000
```

4. int : int is a data type which is also used to store numerical values within the range from -2^31 to 2^31-1
```Java
	int a = 458555
```

5. long : Long is also a numerical data type which is used to store values in the range of -2^63 to 2^63-1
```Java
	long a = 45645618945
```

6. double : double is also a numerical data type which is used to store values in decimal format of double precision which means up to 15 decimal digits.
```java
	double a = 0.048554784121;
	double default = 0.0
```

7. float : float is also a numerical data type which is used to store values in decimal format of single precision which means up to 6-7 decimal digits.
```Java
	float a = 123.2f
```
  - Here the prefix f or F should be appended onto the number while declaring.

8. char : char is a data type which is used to store single character inside a single quote.
```Java
	char a = 'A';
	char b = 'S'
```

### Strings
Apart from the 8 primitive types Java also supports a String data type. Here String is a Object of the String class.
```java
	String a = "San";
	String myString = new String("Hello World");
```

## Java basic input and output.

### Output in java

 - Java basically provides three ways to display output on the standard output
```java
	System.out.println(); // Cursor moves to the next line
	System.out.print(); // Cursor doesnt moves to next line
	System.out.printf(); // Provides formatting specifiers like C or C++
```

### Input in Java

- Java provides to take input using standard output (Screen) using Scanner class.
```java
	import java.util.Scanner;
	public class InputInJava {
		public static void main(String[] args){
			Scanner input = new Scanner();
			int a = input.nextInt(); // int
			float b = input.nextFloat(); // float
			double c = input.nextDouble(); // double
			String d = input.next(); // String
			input.close();
		}
	}
```

## Conditionals in Java

- In programming when a certain block of code has to be executed only if a certain condition is satisfied.

### Conditional Statements

```java
	if(condition){
		// block of code
	}
	
	if(condition){
		// block of code
	}else{
		// block of code
	}

	if(condition){
		// block of code
	}else if(condition){
		// block of code
	}else {
		// block of code
	}
```

### Ternary Operator

- Ternary operators are the syntactical sugar for if-else condition
```Java
	condition ? expression1 : expression2
	int marks = 40;
	String result = (marks >= 35) ? "pass" : "fail";
```

## for-each loop 

- for-each loop in java is used to iterate over array or collection.

```java
class Main {
  public static void main(String[] args) {
    int[] numbers = {3, 9, 5, -5};
    for (int number: numbers) {
      System.out.println(number);
    }
  }
}
```

## Break and Continue

- While working with loops always their arises a situation when a loop has to be terminated under certain condition, In this situation we make use of break or continue statements.
- Break statements stops the entire loop and return to the next statement to execute.
- Continue only skips that particular iteration where it is used.

## Arrays in Java

- Arrays are linear data structure which stores the data in sequential order in an continuous memory locations. 
- Arrays are always used with index.
- Index of array starts with 0

### Declaration of an array

```java
	datatype[] array-name;
	int[] a;

	int[] marks = new int[10];
```

```Java
 // Looping over an array.

	public class LoopArray {
		public static void main(String[] args){
			int[] a = new int[5];
			int[] b = {10,20,30};

			for(int ele : b){
				System.out.println(ele);
			}
		}
	}
```

### Copying an array

- In java There are several ways to copy an array

1. Using assignment operators.

```Java
	public static void main(String[] args){
		int[] a = {10,20,30,40,50};
		int[] b = a;
	}
```
- Here the technique which is used to copy the array is shallow copy.
- Any change made to the parent array will directly affect the child array as well.

2. Looping over a array

```Java
	public static void main(String[] args){
		int[] a = {10,20,30,40,50};
		int[] b = new int[5];

		for(int i = 0; i < a.length; i++){
			b[i] = a[i];
		}
		// This will copy the elements of source array to destination array.
	}
```

3. arrayCopy( ) method.

- arrayCopy( ) method is the best approach than the other two discussed earlier.
- It is present in the System class as a inbuilt method.
- SYNTAX : arrayCopy( object src,  int index, object dest, int index, int number_of_elements  )

```Java
	public static void main(String[] args){
		int[] a = {10,20,30,40,50};
		int[] b = new int[5];
		System.arrayCopy(a,0,b,0,5);
	}
```


## Methods or Functions

- Methods or Functions is a certain block of code which performs certain operations. But this operations are only called when it is called., also known as function call.
- This helps in re-useability of code.
```Java
	// Components of a method
	Access-Modifier return-type method-name (paraneters list .....)
	{
		//Method Body
	}

	static int averageofTwoNumbers(int a, int b){
		return (a+b)/2;
	}
```

### Math class methods

- Math class is a utility class which provides various built-in mathematical methods to perform various operations.
- Math class is a static class which means the methods associated with it can be accessed using class name itself.

```Java
	public class MathMethodsExample {
    public static void main(String[] args) {
        // Basic arithmetic operations
        int sum = Math.addExact(5, 3);
        int difference = Math.subtractExact(10, 4);
        int product = Math.multiplyExact(7, 2);
        int incrementedValue = Math.incrementExact(5);
        int decrementedValue = Math.decrementExact(10);
        int negatedValue = Math.negateExact(8);

        // Exponential and logarithmic functions
        double expValue = Math.exp(2.0);
        double logValue = Math.log(10.0);
        double powerValue = Math.pow(3.0, 4.0);
        double sqrtValue = Math.sqrt(25.0);

        // Trigonometric functions
        double sinValue = Math.sin(Math.PI / 2);
        double cosValue = Math.cos(Math.PI);
        double tanValue = Math.tan(Math.PI / 4);
        double asinValue = Math.asin(0.5);
        double acosValue = Math.acos(0.5);
        double atanValue = Math.atan(1.0);

        // Rounding and absolute value
        double ceilValue = Math.ceil(3.14);
        double floorValue = Math.floor(3.14);
        long roundValue = Math.round(3.14);
        int absValue = Math.abs(-5);

    }
}
```

## String class in Java

- In Java string is declared using a object created using String class. It provides various methods associated with it such as concatenation, searching etc.
- Declaration of string
```Java
	String name = "Santosh" // Declaration using string literal
	String lastname = new String("Sohani")
```
- Strings are mainly associated with two functionalities : 
	- Immutable Nature of String
	- String pool

### Immutable nature of string

- Strings are immutable in nature, which means once the string object is created it cannot be modified further.
- Operations which looks like manipulation of strings, create a new string object itself.

### String pool

- String pool is a concept in java where all the string literals are stored, When a new string is created, it is first searched in string pool if it is present, its reference is stored to that literal or else a new literal is created and added to the string pool.

### String methods.

```Java
public class StringMethodsExample {
    public static void main(String[] args) {
        // String creation and modification
        String str1 = "Hello";
        String str2 = "World";
        
        // Concatenation
        String concatenatedStr = str1.concat(" ").concat(str2);
        
        // Substring
        String substring = concatenatedStr.substring(6, 11);
        
        // Replace
        String replacedStr = concatenatedStr.replace('o', 'x');
        
        // Conversion to lowercase
        String lowercaseStr = concatenatedStr.toLowerCase();
        
        // Conversion to uppercase
        String uppercaseStr = concatenatedStr.toUpperCase();
        
        // Trimming
        String trimmedStr = "   Trim Me   ".trim();
        
        // Comparison and searching
        boolean isEqual = str1.equals(str2);
        boolean contains = concatenatedStr.contains("World");
        boolean startsWith = concatenatedStr.startsWith("Hello");
        boolean endsWith = concatenatedStr.endsWith("World");
        int indexOf = concatenatedStr.indexOf("World");
        
        // Splitting
        String[] parts = concatenatedStr.split(" ");
        
        // Joining
        String joinedStr = String.join("-", parts);
        
    }
}
```

