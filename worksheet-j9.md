## Worksheet J9
# Niyati Shah

# 1. What is the difference between a design pattern and a java library?


# 2. Using the Singleton pattern, write code/pseudocode that ensures that only one database connection object is ever instantiated.


# 3. Assume there is an Animal abstract parent class that has the following constructor: public Animal(String name, int weight. Using the Factory pattern, write code/pseudocode that sets up a factory for two child classes of Animal: Bird and Mammal. Each of these has a constructor with the same arguments as those of the parent class.


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



# 5. What is the benefit of the Bridge design pattern? Why use one?
