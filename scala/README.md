# What is Scala, and what are its key features?

Scala is a modern, statically typed, multi-paradigm programming language that combines elements of both functional and object-oriented programming. It was designed to improve upon the shortcomings of Java and other programming languages, providing a concise and expressive syntax while maintaining compatibility with the Java Virtual Machine (JVM).


# Explain the difference between Scala and Java?

Scala and Java are both programming languages that run on the Java Virtual Machine (JVM), which means they share some similarities, such as interoperability and access to the Java ecosystem. However, there are significant differences between Scala and Java in terms of language features, programming paradigms, and coding style. Here's a breakdown of some key differences:

**Paradigm**:
* Java: Java is primarily an object-oriented programming (OOP) language with support for imperative and procedural programming. It encourages the use of classes and objects for organizing code.

* Scala: Scala is a multi-paradigm language that combines both functional and object-oriented programming. It places a strong emphasis on functional programming constructs like immutability, higher-order functions, and pattern matching.

**Null Safety**:

* Java: Java has a null reference (null) that can lead to null pointer exceptions at runtime, a common source of bugs.

* Scala: Scala addresses null safety by introducing the Option type for handling potentially absent values. This reduces the likelihood of null-related errors.

**Functional Programming**:

* Java: While Java has added functional programming features in recent versions (e.g., streams), it is not as deeply rooted in functional programming paradigms as Scala.

* Scala: Scala is designed with functional programming in mind and provides robust support for functional constructs, making it easier to write functional code.

**Pattern Matching**:

* Java: Java doesn't have native support for pattern matching.

* Scala: Scala has powerful pattern matching capabilities, making it easier to destructure data and perform complex pattern-based operations.


# What is the primary use case for Scala?

Scala is a versatile programming language with a wide range of use cases. Its design, which combines functional and object-oriented programming paradigms, makes it suitable for various application domains. Here are some primary use cases for Scala:
Web Development, Big Data Processing, Concurrent and Distributed Systems, Scientific and Numerical Computing, DSL (Domain-Specific Language) Creation, Microservices, Machine Learning and Data Science


# What are the advantages of using Scala over other programming languages?


Scala offers several advantages over other programming languages, making it an attractive choice for many developers and organizations. Here are some of the key advantages of using Scala:
Concise and Expressive Syntax, Strong Type System with Type Inference, Functional and Object-Oriented, Immutability, Pattern Matching, Interoperability with Java, Concurrency and Parallelism, Functional Collections, Case Classes, Domain-Specific Language (DSL) Creation, Tooling


# What is immutability in Scala, and why is it important?


Immutability in Scala refers to the property of objects or variables whose state cannot be changed after they are created. This means that once an immutable object is instantiated, its data remains fixed throughout its lifetime.

Immutability is important in Scala for several key reasons:
Predictable Code, Thread Safety, Debugging Simplicity, Functional Programming Paradigm, Safe Parallelism


# Explain the concept of pattern matching in Scala. Provide an example.


pattern matching is a powerful feature that allows us to match and destructure data based on patterns. It's often used for control flow, data extraction, and working with data structures in a concise and expressive way. Think of it as a more versatile and powerful version of the switch statement in some other languages.

```scala
sealed trait Shape // A sealed trait represents a closed set of subclasses
case class Circle(radius: Double) extends Shape
case class Square(sideLength: Double) extends Shape
case class Triangle(base: Double, height: Double) extends Shape

def calculateArea(shape: Shape): Double = shape match {
  case Circle(radius) => math.Pi * math.pow(radius, 2)
  case Square(sideLength) => math.pow(sideLength, 2)
  case Triangle(base, height) => 0.5 * base * height
}

val circle = Circle(5.0)
val square = Square(4.0)
val triangle = Triangle(3.0, 6.0)

val circleArea = calculateArea(circle)
val squareArea = calculateArea(square)
val triangleArea = calculateArea(triangle)

println(s"Circle area: $circleArea")
println(s"Square area: $squareArea")
println(s"Triangle area: $triangleArea")

```

# What is the difference between a val and a var in Scala?


In Scala, val and var are used to declare variables, but they have different characteristics related to mutability.

`val` stands for "value" and is used to declare an immutable variable. Once you assign a value to a val, you cannot change it.

`var` stands for "variable" and is used to declare a mutable variable. You can assign a value to a var, and you can later change that value


# What are higher-order functions in Scala? Can you provide an example?


In Scala, **higher-order functions** are functions that can take other functions as arguments or return functions as results. They treat functions as first-class citizens, allowing for more expressive and modular code. Higher-order functions are a key concept in functional programming and are widely used in Scala.


```scala
// Higher-order function
def transformList(numbers: List[Int], func: Int => Int): List[Int] = {
  numbers.map(func)
}

// Example usage
val numbers = List(1, 2, 3, 4, 5)

// Define a function to double a number
def doubleNumber(x: Int): Int = x * 2

// Use the higher-order function to double each element in the list
val doubledNumbers = transformList(numbers, doubleNumber)

println(doubledNumbers) // Output: List(2, 4, 6, 8, 10)

```

# What is the Option type in Scala, and how is it used for handling null or absent values?


In Scala, the **Option** type is a powerful tool for dealing with null or absent values in a type-safe and expressive way. It's designed to help prevent null pointer exceptions, which are common in languages like Java.

An Option can have one of two values:

- Some(value): Represents a non-null or present value, where value is the actual value.
- None: Represents the absence of a value, similar to null in other languages.


```scala
// Creating an Option with a value
val someValue: Option[String] = Some("Hello, Scala!")

// Creating an Option with no value (None)
val noValue: Option[String] = None

```

Using **Option** helps make code more robust because it forces you to explicitly handle the case of missing values. This reduces the likelihood of null pointer exceptions and encourages a more functional and safe programming style.

Additionally, you can use `getOrElse` to provide a default value in case of None, or other methods like map, flatMap, and filter to work with the value inside the Option in a functional way.


# Explain the concept of type inference in Scala. How does it work?


Type **inference** is a fundamental feature in Scala that allows the compiler to automatically deduce and assign data types to variables, expressions, and functions without requiring explicit type annotations in most cases.


```scala
val name = "John" // Compiler infers that 'name' is of type String
val age = 30      // Compiler infers that 'age' is of type Int

def add(x: Int, y: Int) = x + y // Compiler infers the return type as Int

def head[A](list: List[A]): A = list.head // Compiler infers the type parameter A

val total: Double = 42.5 // Explicit type annotation

```

# What is a case class in Scala, and when would you use it?


In Scala, a **case class** is a special type of class that is primarily designed for immutable data modeling. It comes with several built-in features and conventions that make it well-suited for certain use cases

```scala
case class Point(x: Double, y: Double)

def calculateArea(shape: Shape): Double = shape match {
  case Circle(radius) => math.Pi * math.pow(radius, 2)
  case Rectangle(width, height) => width * height
  // ...
}

```

# What are traits in Scala, and how do they differ from classes and interfaces in other languages?

In Scala, **traits** are a fundamental language feature that provide a way to encapsulate method and field definitions, which can then be mixed into classes. Traits are similar to interfaces in other languages, but they offer more flexibility and functionality. Here's a breakdown of traits and their differences from classes and interfaces:

Traits in Scala:

- Definition: A trait is similar to an abstract class but cannot be instantiated on its own. It defines a set of abstract and concrete methods and can also include fields.

- Multiple Inheritance: One of the key differences is that Scala allows a class to mix in multiple traits. This enables a form of multiple inheritance where a class can inherit behavior from multiple sources.

- Constructor Parameters: Traits can have constructor parameters, which can be used to pass data to the trait when it's mixed into a class.

- Concrete Methods: Traits can provide concrete (non-abstract) methods, allowing them to encapsulate reusable behavior that can be shared across classes.

- Stackable Traits: Traits can be stacked together in a specific order to build complex behaviors by composing multiple traits in a class.

- Usage: Traits are often used for defining shared behaviors, mixins, or building blocks for classes. They promote code reuse and modular design.



# Differences from Classes and Interfaces:

- Instantiation: Traits cannot be instantiated directly, whereas classes can. Interfaces in many languages also cannot be instantiated.

- Fields: Traits can contain fields (both abstract and concrete), while interfaces typically do not allow fields (only method signatures).

- Multiple Inheritance: Traits support multiple inheritance, allowing a class to inherit from multiple traits simultaneously. This is in contrast to some languages like Java, which do not support multiple inheritance of classes.

- Constructor Parameters: Traits can accept constructor parameters, which can be passed when the trait is mixed into a class. This provides flexibility for parameterized behavior.

- Concrete Methods: Traits can include concrete methods with implementations, which can be inherited by classes that mix in the trait. Interfaces typically only define method signatures without implementations.

- Order of Mixins: The order in which traits are mixed into a class can affect the behavior of the class. This feature, known as the "linearization order," allows for flexible composition of behaviors.


# What is the difference between an abstract class and a trait in Scala?


**abstract** classes are used for defining common base classes in class hierarchies, while traits are used for defining reusable behaviors that can be mixed into multiple classes, allowing for greater flexibility and code reuse, especially when dealing with multiple inheritance scenarios. The choice between an abstract class and a trait depends on the specific requirements of your design and whether you need single or multiple inheritance.

**Inheritance**
- Traits support multiple inheritance, which means a class can mix in multiple traits simultaneously. This provides greater flexibility in composing behavior from multiple sources.

- A class can inherit from only one abstract class, which enforces single inheritance.


# What is the purpose of the match keyword in Scala? Provide an example of its usage.


In Scala, the **match** keyword is used for pattern matching, which is a powerful and versatile feature. It allows you to perform pattern-based conditional statements and value extraction.

```scala
def classifyDay(day: String): String = day.toLowerCase match {
  case "saturday" | "sunday" => "Weekend"
  case "monday" | "tuesday" | "wednesday" | "thursday" | "friday" => "Weekday"
  case _ => "Unknown"
}

val dayOfWeek = "Saturday"
val classification = classifyDay(dayOfWeek)

println(s"$dayOfWeek is a $classification")

```

- We use the pipe | symbol to match multiple values in a single pattern (e.g., "saturday" or "sunday").
- The underscore _ is a wildcard that matches any value not covered by the previous patterns.


# Explain the concept of implicit conversions and implicit parameters in Scala.

Implicit conversions and implicit parameters are two advanced features in Scala that provide flexibility and enable you to write more concise and expressive code.

### implicit conversions:

You can define an implicit conversion function that takes an argument of one type and returns another type. For example, you might define a conversion from Int to Double like this:


```scala
implicit def intToDouble(i: Int): Double = i.toDouble
```

Usage: When you attempt to use a value of the source type where the target type is expected, the compiler will automatically insert the implicit conversion to bridge the gap. For example:


```scala
val intNumber: Int = 42
val doubleNumber: Double = intNumber // Implicit conversion is applied here
```

Implicit conversions are often used for scenarios like enhancing the functionality of existing types, enabling method chaining, or adapting types for compatibility with libraries and APIs.


### Implicit Parameters:


Implicit parameters allow you to declare parameters in a function or method as "implicit." When a parameter is marked as implicit, the Scala compiler searches for values of that type within the current scope and automatically fills in the argument when the function is called.

Here's how implicit parameters work:

Declaring Implicit Parameters: You can declare a parameter as implicit in a function or method definition. For example:

```scala
def greet(name: String)(implicit greeting: String): String = s"$greeting, $name!"
```

Implicit Values: Implicit values are values marked with the implicit keyword that are in scope. These values are candidates to be automatically passed as implicit parameters when needed.

Usage: When calling a function with implicit parameters, you don't need to explicitly provide values for those parameters. The compiler will look for suitable implicit values and insert them automatically. For example:

```scala
implicit val defaultGreeting: String = "Hello"

val greetingMessage = greet("Alice")

```


implicit parameters are commonly used for dependency injection, configuring behavior, or passing context-specific values without cluttering function signatures.


# What is the Akka framework in Scala, and how does it relate to concurrent and distributed programming?
```
xx
```

# What is functional programming, and how does Scala support functional programming paradigms?

Functional programming is a programming paradigm that treats computation as the evaluation of mathematical functions and avoids changing-state and mutable data. It emphasizes immutability, pure functions, and declarative code. Scala is a language that fully supports functional programming paradigms while also being an object-oriented language. Here's a breakdown of functional programming and how Scala supports it:

Functional Programming Principles:

1 - Immutable Data: In functional programming, data is typically immutable. Once a data structure is created, it cannot be changed. Any modifications result in new data structures being created.

2 - Pure Functions: Functions in functional programming are pure, meaning they have no side effects and always return the same output for the same input. They do not modify external state or rely on mutable data.

3 - First-Class and Higher-Order Functions: Functions in functional programming are first-class citizens, which means they can be treated as values, passed as arguments to other functions, and returned as results. Higher-order functions are functions that take other functions as arguments or return them.

4 - Function Composition: Functional programming encourages composing smaller functions to build more complex ones. This promotes code reuse and modular design.

5 - Avoidance of Mutable State: Mutable state is minimized or avoided entirely. Data is transformed through a series of pure functions.

6 - Declarative Style: Functional programming often uses a declarative style where you describe what you want to achieve, rather than specifying how to achieve it. This leads to more concise and expressive code.


# Explain tail recursion in Scala. Why is it important, and how does it differ from regular recursion?

**Tail** recursion is a specific form of recursion in which a function makes its recursive call as its very last action before returning a result. In other words, the recursive call is in the "tail" position of the function. This is in contrast to regular recursion, where the recursive call may lead to additional computations or operations after the recursion returns.

Key Characteristics of Tail Recursion:

1- Last Operation: In a tail-recursive function, the recursive call is the last operation performed within the function before it returns a result.

2- Efficiency: Tail recursion is important because it allows for efficient memory usage. In languages and environments that support tail call optimization (TCO), like Scala, the recursive call can be optimized in a way that avoids adding a new frame to the call stack for each recursive call. Instead, the same stack frame can be reused, effectively making the recursion use constant stack space.

3- Termination: Tail-recursive functions are typically easier to reason about in terms of termination conditions, as the result is calculated during the recursive descent, and there's no need to track intermediate results or states after the recursive call.


Here's an example of a tail-recursive function in Scala to calculate the factorial of a number:

```scala
def factorial(n: Int): Int = {
  @scala.annotation.tailrec
  def factorialHelper(n: Int, accumulator: Int): Int = {
    if (n <= 1) accumulator
    else factorialHelper(n - 1, n * accumulator)
  }

  factorialHelper(n, 1)
}

```

```scala
def factorial(n: Int): Int = {
  if (n <= 1) 1
  else n * factorial(n - 1)
}

```


# What is the "Future" class in Scala, and how is it used for asynchronous programming?

In Scala, the Future class is a fundamental component of the concurrency and asynchronous programming model. It's used to represent a computation that may not have completed yet but will produce a result or potentially an error in the future. Future is part of the Scala standard library and is widely used in modern Scala applications for handling asynchronous operations.

```scala
import scala.concurrent.Future
import scala.concurrent.ExecutionContext.Implicits.global

val futureResult: Future[Int] = Future {
  // Some time-consuming computation
  42
}

val modifiedFuture: Future[String] = futureResult.map(result => s"Result is: $result")

```

# Discuss the concept of "for comprehensions" in Scala and how they relate to monads.

**For comprehensions** in Scala are a powerful feature for working with monads and handling sequences of operations in a clear and concise way. They are often used with monads to simplify code that involves sequential operations, such as working with `Option``, `Future``, or other monadic types. Let's dive into this concept and its relationship with monads.

A **for comprehension** is a construct that allows you to sequence a series of operations on monadic types using a syntax that resembles imperative programming. It's also known as a 'for-yield' expression. Here's the basic structure of a **for comprehension**:


```scala

for {
  binding1 <- monad1
  binding2 <- monad2
  // ... more bindings
} yield result

```

```scala
val maybeName: Option[String] = Some("Alice")
val maybeAge: Option[Int] = Some(30)

val result: Option[String] = for {
  name <- maybeName
  age <- maybeAge
} yield s"$name is $age years old"

// Equivalent to:
// val result: Option[String] = maybeName.flatMap(name => maybeAge.map(age => s"$name is $age years old"))


```

# What is the difference between a Set and a Map in Scala?

In Scala, both Sets and Maps are collection types, but they serve different purposes and have distinct characteristics:

### Set:

* Unordered Collection: A Set is an unordered collection of distinct elements. It does not allow duplicate values. You can think of it as a mathematical set where each element appears at most once.

* Use Cases: Sets are typically used when you need to store a collection of elements and you want to ensure that each element is unique. Common use cases include checking membership (whether an element is in the set) and eliminating duplicates from a list of values.

* Access and Modification: You can add or remove elements from a Set, but the order of elements is not guaranteed. Sets provide efficient operations for adding and checking for membership.

* Declaration: You can declare a Set in Scala using the Set keyword, followed by a type parameter (for a specific element type) or without one (for a general Set):

```scala
val integerSet: Set[Int] = Set(1, 2, 3)
```

### Map:

* Key-Value Pairs: A Map is a collection of key-value pairs, where each key is associated with a value. Keys in a Map must be unique, but values can be duplicated.

* Use Cases: Maps are used when you need to associate values with keys and look up values based on their keys. Common use cases include building dictionaries, caches, and data representations that require fast lookups.

* Access and Modification: You can add, update, or remove key-value pairs in a Map. Maps provide efficient lookups by key.

* Declaration: You can declare a Map in Scala using the Map keyword, specifying the types of keys and values:


```scala
var colorMap: Map[String, String] = Map("red" -> "#FF0000", "green" -> "#00FF00", "blue" -> "#0000FF")

// Adding a new key-value pair
colorMap += ("yellow" -> "#FFFF00")

// Alternatively, using updated method
colorMap = colorMap.updated("purple", "#800080")

// Print the updated Map
println(colorMap)


// Removing a key-value pair
colorMap -= "yellow"

```


# Explain the concept of currying in Scala. Provide an example.

Currying is a functional programming technique in Scala that allows you to transform a function that takes multiple arguments into a series of functions, each taking a single argument. This can make your code more modular and flexible.

Here's how currying works and an example:

Currying Concept:

* Currying involves transforming a function that takes multiple arguments into a chain of functions, each taking one argument at a time.

* The original function takes all its arguments at once, while the curried version allows you to partially apply arguments and build up the computation step by step.

Example:

Let's say we have a function that calculates the total cost of items in a shopping cart based on the unit price and quantity of each item:

```scala

def calculateTotalCost(unitPrice: Double, quantity: Int): Double = unitPrice * quantity
```

In its current form, you need to provide both unitPrice and quantity at the same time. However, using currying, we can transform this function into a curried version:

```scala
def calculateTotalCostCurried(unitPrice: Double)(quantity: Int): Double = unitPrice * quantity
```
Now, this function is curried. You can use it in two ways:

- Provide all arguments at once:

```scala
val totalCost1 = calculateTotalCostCurried(10.0)(5) // Computes 10.0 * 5 = 50.0
```

- Partially apply arguments:

```scala
val calculateForPrice = calculateTotalCostCurried(10.0) _ // Partially apply unitPrice
val totalCost2 = calculateForPrice(5) // Computes 10.0 * 5 = 50.0

```

# What is a companion object in Scala, and why would you use it?
In Scala, a companion object is a special object associated with a class or trait. It has the same name as the class or trait it's associated with and is defined in the same source file. Companion objects serve several important purposes:

**Factory Methods**: One of the primary use cases for companion objects is to provide factory methods for creating instances of the associated class. These factory methods can have more descriptive names than the class's constructor, making code more readable.

```scala

class Circle(radius: Double) {
  import Circle._ // Importing the companion object

  def area: Double = Circle.calculateArea(radius)
}

object Circle {
  private val Pi = 3.14159265359
  def calculateArea(radius: Double): Double = Pi * radius * radius
}
```

**Static Members**: Companion objects can contain static members (also known as "class-level" members) such as fields and methods that are shared across all instances of the class. These members can be accessed without creating an instance of the class.

```scala
// Class and companion object definition
class Person(name: String, age: Int)
object Person {
  def apply(name: String, age: Int): Person = new Person(name, age)
}

// Creating instances using the companion object's factory method
val person = Person("Alice", 30)

```

**Shared Constants and Configuration**: Companion objects are a convenient place to store constants and configuration parameters related to the class. These constants can be accessed without creating an instance of the class.

```scala

class AppConfig {
  import AppConfig._

  def printAppName(): Unit = println(s"App Name: $AppName")
}

object AppConfig {
  val AppName = "MyApp"
}
```

**Companion Object as a Module**:  In some cases, a companion object can serve as a singleton object that encapsulates functionality related to the class. It's a way to organize utility methods and stateless functions.

```scala
class StringUtils {
  import StringUtils._

  def capitalize(text: String): String = capitalizeFirstLetter(text)
}

object StringUtils {
  def capitalizeFirstLetter(text: String): String =
    if (text.isEmpty) text else text.head.toUpper + text.tail.toLowerCase
}
```

# How does Scala handle exceptions, and what is the role of the "try-catch-finally" block?
Scala, like many programming languages, provides mechanisms for handling exceptions using the "try-catch-finally" construct. However, Scala also offers a more functional approach to error handling through the use of "Try" and "Either." Let me explain both approaches:

### Traditional "try-catch-finally" Block:
Scala supports the traditional "try-catch-finally" construct, which is similar to what you find in languages like Java. Here's how it works:

**Try**: You wrap the code that might throw an exception inside a "try" block.
**Catch**: You can specify one or more "catch" blocks to handle specific types of exceptions.
**Finally**: The "finally" block is optional and is used for cleanup code that should be executed regardless of whether an exception is thrown or not.

```scala
try {
  // Code that might throw an exception
} catch {
  case ex: ExceptionType1 => // Handle ExceptionType1
  case ex: ExceptionType2 => // Handle ExceptionType2
  // ...
} finally {
  // Cleanup code (optional)
}

```

### Functional Error Handling with "Try" and "Either":

Scala provides two functional approaches to error handling: "Try" and "Either."

**Try**: The "Try" class represents the result of a computation that can either result in a successful value (Success) or a failure (Failure) due to an exception. It's a functional way to capture and work with exceptions without using "try-catch" blocks directly.

```scala
import scala.util.{Try, Success, Failure}

val result: Try[Int] = Try(10 / 0) // Creates a Failure with ArithmeticException
val valueOrDefault = result.getOrElse(0) // Gets the value or a default (0 in this case)
```

**Either**: The "Either" class represents a value that can be either a "Left" (indicating a failure with an error message) or a "Right" (indicating a success with a value). It's often used for more structured error handling.

```scala
sealed trait MyError
case class ValidationError(message: String) extends MyError

def divide(a: Int, b: Int): Either[MyError, Int] =
  if (b == 0) Left(ValidationError("Division by zero"))
  else Right(a / b)

```
In functional programming, it's common to use "Try" and "Either" to handle errors in a more expressive and composable way, avoiding the need for "try-catch" blocks and promoting functional code style.


# What is the difference between "Option" and "Either" in Scala for error handling?

"Option" and "Either" are two distinct approaches to error handling in Scala, each with its own use cases and characteristics.

## Option:

* Option is used for representing values that may be absent or present. It's primarily used for handling scenarios where an operation can return a valid result or no result (e.g., due to the absence of data or an error condition).

* Option has two concrete subtypes: Some (represents a value) and None (represents the absence of a value).

* It's commonly used for expressing computations that may or may not yield a result, such as when querying a database, reading a file, or finding an element in a collection.

* Option provides methods like map, flatMap, and getOrElse for safely transforming, chaining, and accessing values.

```scala
val maybeValue: Option[Int] = Some(42) // Value is present
val maybeEmpty: Option[Int] = None // Value is absent

val doubled = maybeValue.map(_ * 2) // Result: Some(84)
val defaultValue = maybeEmpty.getOrElse(0) // Result: 0

```
## Either: 

* Either is used for representing two possible outcomes of a computation, often associated with success and failure. It's typically used when you need to provide additional information about why an operation failed.

* Either has two subtypes: Left (represents a failure with a value) and Right (represents a success with a value).

* It's suitable for situations where you want to return an error message, an exception, or some other contextual information along with the result.
Either provides methods like map, flatMap, and getOrElse for working with its values similar to Option.

```scala

def divide(x: Int, y: Int): Either[String, Int] = {
  if (y == 0) Left("Division by zero")
  else Right(x / y)
}

val result1 = divide(10, 2) // Result: Right(5)
val result2 = divide(10, 0) // Result: Left("Division by zero")

val transformed = result1.map(_ * 2) // Result: Right(10)
val defaultResult = result2.getOrElse(-1) // Result: -1

```

# How does Scala support functional composition, and what are some common techniques for composing functions?

Scala provides several features and techniques for functional composition, which is a fundamental concept in functional programming. Functional composition involves combining multiple functions to create new functions. Here are some ways Scala supports this:

### Function Composition Operator (andThen and compose):

Scala provides two methods, andThen and compose, for composing functions.

* andThen creates a new function that first applies the left-hand function and then applies the right-hand function to its result.

* compose does the opposite; it creates a new function that first applies the right-hand function and then applies the left-hand function to its result.

```scala
val addOne: Int => Int = (x: Int) => x + 1
val multiplyByTwo: Int => Int = (x: Int) => x * 2

val addOneAndMultiplyByTwo = addOne andThen multiplyByTwo
val result = addOneAndMultiplyByTwo(3) // Result: 8 (3 + 1 = 4, 4 * 2 = 8)

```

```scala

val square: Int => Int = x => x * x

val numbers = List(1, 2, 3, 4, 5)

val squaredNumbers = numbers.map(square) // Result: List(1, 4, 9, 16, 25)

```

```scala
val maybeValue1: Option[Int] = Some(10)
val maybeValue2: Option[Int] = Some(2)

val result = for {
  a <- maybeValue1
  b <- maybeValue2
} yield a / b
```


# explain the purpose and usage of the sealed keyword in Scala?

The **sealed** keyword in Scala is used to restrict the inheritance of classes or traits within a certain scope. When a class or trait is marked as **sealed**, it can only be extended or mixed into other classes or traits within the same source file or compilation unit. This restriction has several implications and use cases:

**Limited Subclassing**: Subclassing is limited to the same source file or module where the sealed class or trait is defined. This allows the developer to have tight control over which classes can extend or mix in the sealed type.

**Pattern Matching**: The sealed keyword is often used in conjunction with pattern matching. When a match expression covers all possible subclasses or implementations of a sealed class or trait, the Scala compiler can provide warnings or errors if new subclasses are introduced in the future. This helps ensure that pattern matching is exhaustive and handles all cases.

```scala
sealed trait Shape
case class Circle(radius: Double) extends Shape
case class Rectangle(width: Double, height: Double) extends Shape

def area(shape: Shape): Double = shape match {
  case Circle(r) => math.Pi * r * r
  case Rectangle(w, h) => w * h
}

```

**API Stability**: Marking classes or traits as sealed is a way to signal to other developers that these types are considered stable parts of the API and should not be extended or mixed in arbitrarily. This can help maintain compatibility and prevent unintended consequences when evolving a codebase.

**Optimizations**: The sealed keyword can also enable certain compiler optimizations when exhaustiveness checks are performed. The compiler can make assumptions about the possible subclasses or implementations, potentially resulting in more efficient code.

In summary, the **sealed** keyword in Scala is used to control and restrict the inheritance or mixing of classes and traits within a specific scope. It provides benefits in terms of pattern matching exhaustiveness checks, API stability, and potential optimizations.