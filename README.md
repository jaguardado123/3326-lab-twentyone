# Lab Assignment 21

In this lab you will practice working with polymorphism.

Unlike previous labs, your class has already been created for you. 

## Let's get started!

Now let's begin!

### Polymorphism

When inheriting attributes and methods from other classes it's inevitable to run into a situation where an member with the same name is inherited.

When a class has access to multiple members with the same name (identifier), this is known as **polymorphism**.

**For Example:**
```java
// Super/Parent Class
class Car {
	public String model;

	public void info() {
		System.out.print("This is a car.");
	}
	public void attributes() {
		System.out.print(model);
	}
}

// Sub/Child Class
class Truck extends Car {
	public String model; // Same name as Car attribute
	public int weight_limit;

	// Same name as Car methods.
	public void info() {
		System.out.print("This is a truck.");
	}
	public void attributes() {
		System.out.print(model);
		System.out.print(weight_limit);
	}
}
```

To learn more about polymorphism in Java visit: https://www.w3schools.com/java/java_polymorphism.asp


### Overriding

When a member from the **Super-Class** is inherited into the **Sub-Class** the **Sub-Class**' members takes precedence, this is known as **overriding**.

Overriding only occurs in the following scenarios:

* Attributes have the same identifier.
* Methods have the same identifier & parameters.

**For Example:**
```java
Truck truck1 = new Truck();
truck1.info(); // This will output "This is a truck."
```

When overriding occurs in our code it's important to reflect it using the proper annotation. 
* Use the `@Overriding` annotation above all methods that will override a method from the super-class.
* Use the `this` keyword to differentiate attributes from the sub-class.
* Use the `super` keyword to differentiate attributes from the super-class.

**For Example:**
```java
// Super/Parent Class
class Car {
	public String model;

	public void info() {
		System.out.print("This is a car.");
	}
	public void attributes() {
		System.out.print(model);
	}
}

// Sub/Child Class
class Truck extends Car {
	public String model; // Same name as Car attribute
	public int weight_limit;

	// Same name as Car methods.
	@Override
	public void info() {
		System.out.print("This is a truck.");
	}
	@Override
	public void attributes() {
		System.out.print(super.model);
		System.out.print(this.model);
		System.out.print(this.weight_limit);
	}
}
```

To learn more about overriding in Java visit: https://www.geeksforgeeks.org/overriding-in-java/

## Your Assignment

For this assignment you will be working with the following classes: `Machine`, `Bulldozer` and `Excavator`.

`Bulldozer`'s and `Excavator`'s are both `Machine`s, so have them **inherit** the `Machine` class.

Next, create constructors for `Bulldozer` and `Excavator`. Remeber, use the `this` and `super` keywords.

Lastly, **override** the `about()` method so when called upon it will output the information of the **Sub-Class**. Use the correct annotation to indicate when you are overriding a method.

**Test Your Code:**

```
./build.sh
./test.sh
```

## Submit your assignment

To submit your lab assignment click on the **Source Control** icon (3 circles with 2 lines) on your leftside navbar. Next, click on the **+** symbol next to **Changes** to stage your changes. Lastly, add a commit message (ex: "First commit") and click **Commit** then **Sync Changes**. And you're done!
