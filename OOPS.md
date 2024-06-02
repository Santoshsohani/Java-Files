---

---


Java is object oriented programming language which means, complex problems are divided into various objects.
- Object has mainly two entities associated with it.
	- State
	- Behavior

## Class 

- Class in java is a blueprint for an object, class contains all the necessary features and attributes required.
- Before creating a object, one should create a class, From that particular class an instance is created called as Object.
- Example : Blueprint of a house can be termed as class, which contains all the necessary dimensions, floor planning etc. From that blueprint a object can be created i.e. House
- using a single class multiple objects can be created.

```Java
	class className{
		//fields
		// behaviour
	}
```

- Here the fields are state or variables which store data.
- behavior are the functionality of a particular class.

```Java
	class Bicycle {
	
		// fields
		public int wheel = 2;
		public int seat = 1;
		public int breaks = 2;
		
		// behaviour
		public void braking() {
			System.out.println("Brakes Applied");
		}
	}
```

- using this Bicycle class multiple objects can be created.

## Objects 

- Objects are also called as instance of a class, For example consider the example of  Bicycle then its objects like Touring Cycle  can be called as its instance.

```Java
	ClassName ObjectName = new ClassName();

	Bicycle touringCycyle = new Bicycle();
```


## Method Overloading

Suppose you are at a coffee shop and you can ask barista for a coffee in different number of ways:
- can i get a coffee
- can i get a coffee with milk
- can i get a coffee with milk and sugar

Here the operation which is being performed is getting a coffee, but the parameters which is being passed is different. This concept is called as Method overloading.

```
Method Overloading : It is a feature in java where different methods inside the same class may have same name but the methods should differ in number of paramters or different types of parameters or both. Then this concept is termed as Method overloading.
```

```Java
	// Example for method overloading in Java
	public class Calculator{
		public add(int a, int b){
			return a+b;
		}
		public add(double a, double b, double c){
			return a+b+c;
		}
	}
```

```

NOTE : Method overloading is not associated with return type of the methods, which means the methods can have same return type or different.
```

## Constructors

Suppose you have purchased a new phone, when you first turn on the device it asks for certain attributes like setting up your account, Wi-Fi and other such settings. This initial data provided is given using constructor method.

Properties : 
1. Setup the initial values for the object created as per requirement.
2. Name same as the class name
3. No return type
4. Can have or may not have parameters.

```
	Default : non parameterized constructor
```

```Java
	public class Car {
    // Fields (attributes)
    String color;
    String model;
    int year;

    // Constructor
    public Car(String color, String model, int year) {
        this.color = color;
        this.model = model;
        this.year = year;
    }

    // Method to display car details
    void displayDetails() {
        System.out.println("Car: " + color + " " + model + " (" + year + ")");
    }
}

public class Main {
    public static void main(String[] args) {
        // Creating a new Car object using the constructor
        Car myCar = new Car("Red", "Toyota", 2022);

        // Displaying car details
        myCar.displayDetails();
    }
}
```

## Static Keyword

Static keyword in Java helps us to identify that a particular member belongs to a class itself rather than its instance.  
- Static Keyword are used for 4 reasons :  
  - static variables  
  - static methods  
  - static block  
  - static inner classes

### Static Variables

- Variables which are declared as static is only associated with its class and not its instance, which means an object created from a class cannot access the class static members.  
- These variables are only accessed using the class name.  
- When using inside the same class, it can be used directly using variable name.

```Java  
   class Car{  
    static int a = 45;  
  }  
  public class Execution{  
    public static void main(String[] args){  
      System.out.println(Car.a) // 45  
    }  
  }

```

### Static Methods

- Static methods are also the methods which belongs to particular class and not its instance which means its methods cannot be accessed using its instance, But with the class name only.  
- Example of static Method can be given using Math class, where all the methods of class Math are static and can be only be accessed using Math class name.  
```Java  
  class Car{  
    static int numberOfCars = 4;  
    public static displayNumberOfCars() {  
      System.out.println(numberOfCars);  
    }  
  }  
  public class Execution{  
    public static void main(String[] args){  
      Car.displayNumberOfCars() // 45  
    }  
  }  
```

### Static Block

- Static blocks are used to initialize static variables.  
```Java  
  static{  
    // intilize static variables  
  }  
```  
- These static blocks gets called once the class is loaded into the memory, before creation of any object.  
```java  
class Main {

   // static variables  
   static int a = 23;  
   static int b;  
   static int max;

   // static blocks  
   static {  
       System.out.println("First Static block.");  
       b = a * 4;  
   }  
   static {  
       System.out.println("Second Static block.");  
       max = 30;  
   }

   // static method  
   static void display() {

       System.out.println("a = " + a);  
       System.out.println("b = " + b);  
       System.out.println("max = " + max);  
   }

   public static void main(String args[]) {  
       // calling the static method  
       display();  
   }  
}  
```

```Java  
  First Static block.  
  Second Static block.  
  a = 23  
  b = 92  
  max = 30  
```

## Packages

- Packages in java are entities which helps us to group related classes, interfaces into a single group.  
- Think packages as a folder where multiple files or sub-folder are grouped together.  
- Package is created at the first line of source code  
```java  
  package com.example.myapp;  
  public class MyApp{  
    // Class fields and behaviours  
  }  
```  
- Here the class MyApp is grouped into package com.example.myapp  
- Now if the class MyApp present in the package com.example.myapp to be used inside another class, Then we should use import keyword for the same.  
```java

  import com.example.myapp.Myapp;

  public class PackageUsegae{  
    public static void main(String[] args){  
      Myapp app = new Myapp();  
    }  
  }  
```

## Access Modifiers

- Access modifiers are used to set the accessibility of a variable, method, class, constructor etc.  
- Access modifiers are of 4 types :  
  - default : Declarations are visible only within the same package.  
  - private  
  - public   
  - protected

### Default

```java  
  package com.defaultclass.app;  
  class DefaultClass{  
    int a = 10;  
    void displayNumber(){  
      System.out.println(a);  
    }  
  }   
```  
- As the class and its members are default, Then the class DefaultClass, variable a and method displayNumber can be accessed by all entities present in the package com.defaultclass.app

### Private

- when variables, methods are given the access modifier as private then it is only accessible within the particular class.

```Java  
class Data {  
    // private variable  
    private String name;  
}

public class Main {  
    public static void main(String[] main){

        // create an object of Data  
        Data d = new Data();

        // access private variable and field from another class  
        d.name = "Programiz";  
        // Throws an error  
    }  
}  
```

- But what to do when you want to access these private variables , Now we can use getters() and setters() methods for the same.

```Java  
class Data {  
    private String name;

    // getter method  
    public String getName() {  
        return this.name;  
    }  
    // setter method  
    public void setName(String name) {  
        this.name= name;  
    }  
}  
public class Main {  
    public static void main(String[] main){  
        Data d = new Data();

        // access the private variable using the getter and setter  
        d.setName("Programiz");  
        System.out.println(d.getName());  
    }  
}  
```

### Protected

- When classes, methods or fields are declared as private then its fields and behavior's are  accessed within the same package and also within the same sub-class.  
```Java  
class Animal {  
    // protected method  
    protected void display() {  
        System.out.println("I am an animal");  
    }  
}

class Dog extends Animal {  
    public static void main(String[] args) {

        // create an object of Dog class  
        Dog dog = new Dog();  
         // access protected method  
        dog.display();  
    }  
}  
```

### Public

- When access modifiers are termed as public its members can be accessed by any package or any class.  
- No restriction what so ever.

### Tabulated Features of all access modifiers.

| Feature                                            | `private` | `default` (package-private) | `protected` | `public` |
| -------------------------------------------------- | --------- | --------------------------- | ----------- | -------- |
| **Accessible within the same class**               | Yes       | Yes                         | Yes         | Yes      |
| **Accessible within the same package**             | No        | Yes                         | Yes         | Yes      |
| **Accessible by subclasses in the same package**   | No        | Yes                         | Yes         | Yes      |
| **Accessible by subclasses in different packages** | No        | No                          | Yes         | Yes      |
| **Accessible by any class in different packages**  | No        | No                          | No          | Yes      |
| **Encapsulation**                                  | Highest   | Moderate                    | Moderate    | Lowest   |
|                                                    |           |                             |             |          |

## This Keyword
- This keyword in java refers to the current object, inside a instance method or inside a constructor.
- There are various use cases of this keyword
	- Ambiguous nature of variable names.
	- With getters and setters
	 - Constructor overloading.

### 1. Ambiguous nature of variable name

- We cannot declare multiple variables with same name inside a same scope, for example
```Java
class MyClass {
	int a;
	MyClass(int a){
	 a = a // Results in values as 0
	}
}
```
- In the above example the compiler gets confused because of the ambiguity, hence the value a=0
```Java
class MyClass {
	int a;
	MyClass(int a){
	 this.a = a 
	}
}
``` 
- This gets the desired output because the this keyword inside the constructor points to the current object and assign's the desired value to the instance variable.

### 2. getters and setters

- As we know this keyword refers to the current object when called inside a instance method or constructor, hence this keyword has all the instance variables as well, hence it is used in getters and setters.
```Java
class MyClass {
	static int a;
	private int getters(){
		return this.a;
	}
	private void setters(int a){
		this.a = a
	}
}
```

### 3. In Constructor Overloading
- Here we can use this keyword to call a constructor inside a another constructor of the same class.
```java
class Complex {

    private int a, b;

    // constructor with 2 parameters
    private Complex( int i, int j ){
        this.a = i;
        this.b = j;
    }

    // constructor with single parameter
    private Complex(int i){
        // invokes the constructor with 2 parameters
        this(i, i); 
    }

    // constructor with no parameter
    private Complex(){
        // invokes the constructor with single parameter
        this(0);
    }

    @Override
    public String toString(){
        return this.a + " + " + this.b + "i";
    }

    public static void main( String[] args ) {
  
        // creating object of Complex class
        // calls the constructor with 2 parameters
        Complex c1 = new Complex(2, 3); 
    
        // calls the constructor with a single parameter
        Complex c2 = new Complex(3);

        // calls the constructor with no parameters
        Complex c3 = new Complex();

        // print objects
        System.out.println(c1);
        System.out.println(c2);
        System.out.println(c3);
    }
}
```


## Inheritance in Java

- Inheritance refers to the feature in java where another sub-class is created from a main class or also called as super class.
- The sub class which is created inherits the properties and behavior from the super class. This phenomena is called as inheritance.
- Here we use a keyword called as extends for inheritance.

```Java
class Vehicle{
	int topSpeed;
	Vehicle(int topSpeed){
		this.topSpeed = topSpeed;	
	}
}

class Car extend Vehicle{
	public void gears(){
		System.out.println("Car has 5 gears");
	}
}
```

- Inheritance is seen when there arises a "is a" relation.
- Car is a Vehicle
- Orange is a Fruit.

- The main use case of inheritance is code reusability, here the methods of super class can directly be accessed by the sub-class.

### Types of Inheritance

![[Types of Inheritance.png]]

## Method Overriding in Java

- In the case of inheritance we know a sub-class is created from a existing super-class, And the sub class inherits the properties and methods from the super class, But now the question arises what if the super class and sub class have the methods with the same name. This is when method overriding comes into picture, the method in superclass gets overridden by the method present in sub-class. The method present in sub-class gets called.
- Rules for method overriding :
  1. The Name, return type and parameters list has to be same in both super class and sub class.
  2. Method overriding cannot be applied if the access modifier for the method is either of static or final.

```Java
class Animal {
   public void displayInfo() {
      System.out.println("I am an animal.");
   }
}

class Dog extends Animal {
   @Override
   public void displayInfo() {
      System.out.println("I am a dog.");
   }
}

class Main {
   public static void main(String[] args) {
      Dog d1 = new Dog();
      d1.displayInfo();
   }
}
```


## Final Keyword in Java

- When a particular entity has to declared as constant we use a keyword called as final.
- final keyword can be applied to a variable, method or a class.
- The rules for final keyword
	- If a variable is declared as final its value cannot be manipulated again.
	- if a method is declared as final it cannot be overridden.
	- if a class is declared as final it cannot be extended.

### 1. Java final keyword

```Java
class Main {
  public static void main(String[] args) {

    // create a final variable
    final int AGE = 32;

    // try to change the final variable
    AGE = 45;
    System.out.println("Age: " + AGE);
  }
}
```

```
cannot assign a value to final variable AGE
    AGE = 45;
    ^
```

### 2. Java final method

```Java
class FinalDemo {
    // create a final method
    public final void display() {
      System.out.println("This is a final method.");
    }
}

class Main extends FinalDemo {
  // try to override final method
  public final void display() {
    System.out.println("The final method is overridden.");
  }

  public static void main(String[] args) {
    Main obj = new Main();
    obj.display();
  }
}
```

```
 display() in Main cannot override display() in FinalDemo
  public final void display() {
  
  overridden method is final
```

### 3. Java final class

```Java
// create a final class
final class FinalClass {
  public void display() {
    System.out.println("This is a final method.");
  }
}

// try to extend the final class
class Main extends FinalClass {
  public  void display() {
    System.out.println("The final method is overridden.");
  }

  public static void main(String[] args) {
    Main obj = new Main();
    obj.display();
  }
}
```

```
cannot inherit from final FinalClass
class Main extends FinalClass {
```

## Instanceof operator in Java

- Instanceof operator in java is used to check whether a object is instance of a class or not.
```
	objectName instanceof className
```
- During inheritance the instance of operator returns true for both the parent class and child class.

## Super keyword in java

- Super keyword in java is associated with inheritance, it is used within the sub-class to access the entities of super class, The entities are variables, methods and constructor.
- There are three main use cases of super keyword
	- Access the overridden methods of super class.
	- Access the Variables of super class within the subclass having same name.
	- call constructor of super class in sub class.

### 1. Access the overridden methods of super class
```java
class Animal{
	void makeNoise(){
		System.out.println("Animal Makes noise");
	}
}

class Dog extends Animal{
	void makeNoise(){
		System.out.println("Dog barks");
	}
	super.makeNoise();
}

public static void main(String[] args){
	Dog dog1 = new Dog();
	
}

// Output
// Dog barks
// Animal makes noise
```

### 2.  Access the variables of superclass having the same name.

```Java
class Animal{
	public String type = "mammal";
	void makeNoise(){
		System.out.println("Animal Makes noise");
	}
}

class Dog extends Animal{
    
    Dog(){
        System.out.println(super.type);
    }
    
	void makeNoise(){
		System.out.println(super.type);
	}
	
}

public class Main{
	public static void main(String[] args){
	Dog dog1 = new Dog();
	dog1.makeNoise();
}
}
```


### Call the constructor of the super class.

```Java
class Animal{

	Animal(){
		System.out.println("This is a animal");
	}

	void makeNoise(){
		System.out.println("Animal Makes noise");
	}
}

class Dog extends Animal{

	Dog(){
		super();
	}

	void makeNoise(){
		System.out.println("Dog barks");	
	}
}

public class Main{
	public static void main(String[] args){
	Dog dog1 = new Dog();	
	dog1.makeNoise();
	}
}
```

## Abstract method and Abstract class in java

- Abstract methods are those methods in java, which cannot be instantiated.
- No objects can be created using an abstract class.
- abstract keyword is used to declare a abstract class and abstract method.
- abstract class can contain both abstract methods and regular methods
- if a class contains abstract method, then class should be declared as abstract as well.
- abstract method doesn't have its body. 
- Abstract class can be inherited, objects can be created from the sub-class.

