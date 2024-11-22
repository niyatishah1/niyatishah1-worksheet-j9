# Worksheet J9
## Niyati Shah

# 1. What is the difference between a design pattern and a java library?
A design pattern is a conceptual template or blueprint that developers use on how to implement some functionality, while a java library is downloaded code for existing functionality.

# 2. Using the Singleton pattern, write code/pseudocode that ensures that only one database connection object is ever instantiated.
```java
public class DBSSingleton {
	//this is a private member variable so that the file can only be accessed through the getInstance() method.
	private static DBSSingleton file;
	private static Connection connection;

	//private constuctor forces the class to be instatiated via getInstance method.
	private DBSSingleton() {
		//private constructor
		//set up the object here
		connection = new Connection("username", "12345", "120.5.4.4");
	}

	//method to get an instance of this class.
	public static DBSSingleton getInstance() {
		//if this singleton instance is null, then constuct new instance.
		//otherwise return the existing instance
		if(connection == null) {
			connection = new DBSSingleton();
		}
		return file;
	}
}
```

# 3. Assume there is an Animal abstract parent class that has the following constructor: public Animal(String name, int weight. Using the Factory pattern, write code/pseudocode that sets up a factory for two child classes of Animal: Bird and Mammal. Each of these has a constructor with the same arguments as those of the parent class.
```java
public class AnimalFactory {
	public static Animal getAnimal(String option, String name, int weight) {
	   switch(option) {
	      case "mammal":
		return new mammal(name, weight);
	      case "bird":
		return new bird(name, weight);
	   }
	   return null;
	}
}		
```

# 4. Imagine we have some code for an aquarium that works nicely to schedule feeding the fish in all the tanks, and cleaning the tanks:
```java
public class Aquarium {
	public void feedAll(ArrayList<Fish> tanks, int numFishInTank) {...}
	public void cleanAll(ArrayList<Fish> tanks)
}
```
**This code works well with the following Fish class:**
```java
public class Fish{
	public void feed(String food, int weight) {...}
	public void clean(String cleaningProduct) {...}
}
```
**We also, one day, inherit an animal hospital, where each patient is solo in a cage. We want to be able to use the code above to feed and clean the cages of all the animals, but our hospital has the following API for the mammals they serve:**
```java
public class Mammal{
	public void feed(String food, int weight, String medication) {...}
	public void clean() {...}
}
```
**Use the Adapter pattern to allow us to use the Mammal class with the Aquarium class above. Each animal is housed alone in its cage during its visit. All mammals are given the same medication, namely, "antibiotics".**
```java
public class MammalAdapter extends Fish {
	private Mammal mammal;
	public statis void feed(String food, int weight) {
		return mammal.feed(food, weight, "antibiotics");
	}
	public static void clean(String cleaningProduct) {
		return mammal.clean();
	}
}
```

# 5. What is the benefit of the Bridge design pattern? Why use one?
It allows for code reuse, has good OOP principles and has maintainable use.
