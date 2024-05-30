Java is object oriented programming language which means, complex problems are divided into various objects.
- Object has mainly two entities associated with it.
	- State
	- Behavior

## Class 

- Class in java is a blueprint for an object, class contains all the necessary features and attributes required.
- Before creating a object, one should create a class, From that particular class an instance is created called as Object.
- Example : Blueprint of a house can be termed as class, which contains all the necessary dimensions, floor planning etc. From that blueprint a object can be created i.e House
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

