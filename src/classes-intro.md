# Classes
## What are classes?
Classes are a way for you to create your own "objects." 
Classes are exceptional (from their predecessors) because they can have both *state* (class variables) and *behavior* (methods). 
You can have state and methods separately of course, for example: structs let
you have state and functions have behavior, but classes enable you to couple
both state and behavior together, and enable other OOP concepts, such as polymorphism.

Alright, so lets look at a class:
```kotlin
class DoesNothing() { // Note: class name is in upper camel case
}
```
This class, as the name describes, does nothing. 

So let's make a class with some state:
```kotlin
class State(val x: Double, val y: Double) { 
}
```

Here we have a class that takes in two doubles and stores them. 
If you omit the `val` before either variable, the variables will only be used in the `constructor` (we'll get to constructors later).
This code actually already defines a constructor, but the constructor has (essentially) no behavior. 
This concept is sometimes called Dependency Injection (DI).

Let's look at what it'll look like if you wanted to use this class in your code:
```kotlin
fun main() {
	val newClass = State(1.0, 2.0)
	println(newClass.x) // prints 1.0
}
```

Ok, neat, but how do we add behavior that interacts with the state?
Let's try another example of a class with behavior and state:
```kotlin
class State(val x: Double, val y: Double) {
	fun printX() {
		println(x);
	}
}
```

And the corresponding code in main:
```kotlin
fun main() {
	val newClass = State(1.0, 2.0)
	newClass.printX()
}
```

## Constructors
This last concept is very important, but we will only touch on it briefly.
Let's say you wanted to add 1 to every number initially plugged into the class.
This is a good opportunity to demonstrate a simple example of a constructor:
```kotlin
class State(val x: Double, val y: Double) {
	init {
		x++
		y++
	}

	fun printX() {
		println(x);
	}
}
```
The constructor (behavior) here is in the "init" method.
It runs (as expected) when the class is first initialized.
This specific example simply adds 1 to both x and y.
You'd use the code the same as before in your `main` function (or elsewhere).

## Ok but why
> "Managing complexity is the most important technical topic in software development. 
> In my view, it's so important that Software's Primary Technical Imperative
> has to be managing complexity. 
> Complexity is not a new feature of software development."
> -Steve McConnell

In Kotlin/Java, classes are *required*. 
There are no structs (but there are data classes in Kotlin) so all state needs
to stored be in a class.
Arguments for whether state should be coupled with behavior in this way are more nuanced, but we will do it regardless on the team, so it's worth learning.

## Further Steps
To learn more check out the `data classes` chapter and the chapter on inheritance/polymorphism.
