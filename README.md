# OO Design Final Project
**Holt Skinner 🤓 & Kyle Whitney ♿️**

*CS 4330 Spring 2017*

>  An analysis of Java and Swift based on Object-Oriented Design Principles.

Java
<img src="JavaLogo.png" alt="Java" width="50">

Swift
<img src="SwiftLogo.png" alt="Swift" width="50">

> Computer Science is about as close to magic you can get, if you're smart enough.  
> ~ Dale Musser

## Language Purpose & Origins 📚
🤓

### Java

#### Early History
The Java programming language (not to be confused with *JavaScript*) was first released in 1995 by Sun Microsystems. The project was started in 1990 as a response to C and C++. Programmers were becoming frustrated by the tedious tasks required by the language, such as memory management and incompatability between operating systems. The goal was to create a virtual machine and language that was similar to C, but much simpler to program in. Jasmes Gosling was chosen as the lead architect for the team of only 13 people, soon known as *The Green Team.* [^1] The name *Java* was chosen after the Indonesian island Java, and the slang term for coffee. ☕️ [^2]

#### Philosophy
There were 5 primary goals in mind when creating Java.
1. It should use the object-oriented programming methodology.
2. It should allow the same program to be executed on multiple operating systems.
3. It should contain built-in support for using computer networks.
4. It should be designed to execute code from remote sources securely.
5. It should be easy to use by selecting what was considered the good parts of other object-oriented languages.
   [^3]

> A Simple "Hello World" program in Java.

```java
System.out.println("Hello World!");
```

### Swift

#### Early History
The Swift programming language (not to be confused with [*Taylor Swift*](https://en.wikipedia.org/wiki/Taylor_Swift)) began development in July 2010 under the direction of Chris Lattner at Apple. Swift was designed as a replacement for Objective-C, to be used as the primary language for iOS and macOS development. Swift took language ideas "from Objective-C, Rust, Haskell, Ruby, Python, C#, CLU, and far too many others to list." [^4] Although not officially stated, it is quite apparent that many ideas were borrowed from Java as well. Swift was unveiled by Craig Federighi at WWDC 2014; it was described as "Objective-C without the baggage of C."

[![Apple WWDC 2014 - Swift Introduction](https://img.youtube.com/vi/MO7Ta0DvEWA/0.jpg)](https://youtu.be/MO7Ta0DvEWA)

#### Philosophy
Similar to Java, Swift's primarily goal was to greatly simplify the software engineering process. Some of the minor adjustments include:
- No semicolons required `;`
- No header files to manage
- Type inference
- Functions are first class citizens.
- Null pointer exceptions are not possible via the use of optionals (see below)
- C-style enumeration `for (int i = 0; i < size; i++)` is not allowed. [^5]

> A Simple "Hello World" program in Swift.
> Notice how this program is 14 characters fewer than the Java example.

```swift
print("Hello World!")
```

## Unique Features 🦄
🤓

### Java

Many of the "unique" features of Java have been encorporated into other languages as the field has progressed. The initial selling point was that Java code is platform independant due to the existance of the Java Virtual Machine (JVM). Code could be written and compiled for the JVM, and the compiled byte codes could be used on any machine with the JVM installed. In addition, other languages such as Clojure, Groovy ☮️ and Scala were written to run on the JVM.

### Swift

The most notable unique feature of Swift is the notion of an "Optional" denoted by `?` An optional prevents the common programming error of a "Null Pointer Exception" by "wrapping up" values that can potentially hold a nil reference. These optional values must be "unwrapped" using the `if let` construct. This is conceptually similar to the idea of dereferencing a pointer in `C/C++`.

> An example of Optionals [^6]

```swift
// A Swift Dictionary
let ages = ["Mohsen": 17, "Amy": 40, "Graham": 5]

// Defining a constant, possibleAge, of type Int Optional
let possibleAge: Int? = ages["Daryl"]

// Unwrapping the Optional
if let age = possibleAge {
    // This line will only run if age != nil
    print("An age of \(age) was found.")
}

```

> Another Example of Optionals [^7]

```swift
var optionalString: String? = "Hello"

print(optionalString == nil)
 
var optionalName: String? = "John Appleseed"

var greeting = "Hello!"

if let name = optionalName {
    greeting = "Hello, \(name)"
}
```

Many of the other features of Swift are modeled after popular programming languages. [10 features Apple 'stole' for Swift](http://www.infoworld.com/article/2606431/application-development/155797-10-prominent-features-stolen-by-Apple-s-Swift-and-where-they-came-fro.html)

## Reflection ⚗️
🤓

[Background Information](http://stackoverflow.com/questions/37628/what-is-reflection-and-why-is-it-useful)

### Java
Reflection in Java is provided via the reflect library. It allows the ability to dynamically inspect the abilities of a class at runtime.

> Greatly simplified Reflection example (Credit to Dale Musser)

```java
import java.lang.reflect

Class dogClass = Dog.class;
```

### Swift

As of Swift 3, reflection is not natively supported. 😔 The Mirror Class in the Swift Standard Library provides some of the functionality. [^8] Other libraries have been created to imitate this functionality, and some "hacks" can be made to work with Objective-C backwards compatability.
[StackOverflow](http://stackoverflow.com/questions/24060667/does-swift-support-reflection)

## Memory Management 🗑
🤓

### Java

[Garbage Collection Description](https://www.dynatrace.com/resources/ebooks/javabook/how-garbage-collection-works/)

Java's method of managing unused memory is called "Garbage Collection." The basic idea is the Garbage Collector keeps track of the amount of references for each object. When the last reference to an object is unreferenced, the garbage collector frees the memory. 

Objects can be unreferenced by :

1. Setting the object to null.

```java
Dog dog = new Dog(); // 🐶
dog = null;
```

2. Assigning a reference to another object.

```java
Cat cat1 = new Cat(); // 😺
Cat cat2 = new Cat();

cat1 = cat2;
// The object referrenced by cat1 can be garbage collected.
```
3. Creating an annonymous object.

```java
new Tiger(); // 🐯
```

The `finalize()` method on the Object class is called before the object is garbage collected. [^9]

### Swift

Automatic Reference Counting

On a high level, Swift's method of memory management keeps a count of the different references to an object. When the count hits 0, the memory is deallocated.

[^10]

## Comparison of Values and References 👾
🤓

### Java

`==` compares if two variables referecne the same object. `.equals()` compares the value inside an object.

```java
String string1 = "Holt"
String string2 = string1;
String string3 = "Holt"

if (string1 == string2) {
    // This if will run.
}

if (string1 == string3) {
    // This if will not run.
}

if (string1.equals(string3)) {
    // This if will run.
}
```

### Swift

`==` compares value types. (`Int`, `Array`, `String`, etc).
`===` compares reference types. `class`

Value types copy data upon assignment; reference types create a shared instance.

```swift
var a: Int = 5
var b: = a
a = 55

print("\(a), \(b)")             // prints "55, 5"

class C { var data: Int = -1 }
var x = C()
var y = x						// x is copied to y
x.data = 42						// changes the instance referred to by x (and y)
println("\(x.data), \(y.data)")	// prints "42, 42"

```
[^11]

## Null/nil References ⛔️
🤓

A null pointer (or reference) is a special value indicating that the pointer doesn't refer to an object. [^12]

### Java

Null ponters are referred to by `null` and can be assigned to any object type.

### Swift

Null pointers use the `nil` keyword and can only be assigned to Optional Types.

```swift
var x: Int = nil // This is invalid
var y: Int? = nil // This is valid
```

## Singleton :shipit:
🤓

### Java

The Java Standard for Singletons has been based around (Crazy) Bob Lee's paradigm of a Lazy-Loaded, Thread-safe Singleton.

```java
public class Something {
    private Something() {}

    private static class LazyHolder {
        static final Something INSTANCE = new Something();
    }

    public static Something getInstance() {
        return LazyHolder.INSTANCE;
    }
}
```

[Initialization-on-demand holder idiom] (https://en.wikipedia.org/wiki/Initialization-on-demand_holder_idiom)

[Crazy Bob Lee] (http://blog.crazybob.org/2007/01/lazy-loading-singletons.html)

### Swift

To make lazy instantiation easier for developers, Swift has the `lazy` keyword. Singletons are also incredibly simple to instanciate.

```swift
class TheOneAndOnlyKraken {
    static lazy let sharedInstance = TheOneAndOnlyKraken()
    private init() {} //This prevents others from using the default '()' initializer for this class.
}
```

[Right Way to Write a Singleton](https://krakendev.io/blog/the-right-way-to-write-a-singleton)

## [Procedural Programming] (https://en.wikipedia.org/wiki/Procedural_programming) 🔑
🤓

[OO Verus Procedural](https://softwareengineering.stackexchange.com/a/61216)

Java was written from the ground up to be a fully Object-Oriented Language. It is possible to write procedural code by putting everything in the `main` class, but it is not what Java was intended to do. Also, it is not *true* proceduaral programming, because Java requires everything to be inside a class. 😒

Swift natively supports Object-Oriented AND proceduaral programming paradigms. Classes & Protocols are intended to be optional (pun intended), not required. [^14]

![Why Not Both](https://img.memesuper.com/200de1d4ef6baaccc1cb515779c2faf6_-meme-why-not-both-meme-why-not-both_419-261.jpeg)

[More information on design patterns in Swift] (https://github.com/ochococo/Design-Patterns-In-Swift)

## Functional Programming
♿️

## Threads 🕸
🤓

A thread of execution is the smallest sequence of programmed instructions that can be scheduled. Multi-threaded applications allow for multiple instructions to be scheduled independently. (With some reservations) [^15]

### Java

In Java, threads can be created in one of two ways:

1. Implementing the Runnable interface `java.lang.Runnable`

In this strategy, the `run()` method in the interface must be defined inside the class. This method contains the code that will be run concurrently.

2. Extending the Thread class `java.lang.Thread`

This strategy is similar, however the default `run()` method must be overriden with a user-defined method. Extending is much more limiting than Implementing because Java only allows single-inheritance.

To start a thread of execution, the `start()` method is called on the thread object, which invokes `run()`.

Unfortunately, User Interface Frameworks are not thread-safe. If a programmer wants to use threads with a UI, thread code must NOT directly manipulate the UI objects. Java's solution is to place all thread code that must manipulatre the UI in the `Platform.runLater()` method. This code will run later, as in when the thread is complete.

### Swift

To simplify the process, programmer Josh Smith took advantage of Swift's ability to define custom operators and created a custom thread operator `~>`.
[Swift Custom Thread Operator](https://ijoshsmith.com/2014/07/05/custom-threading-operator-in-swift/)
# Sources

[^1]: https://en.wikibooks.org/wiki/Java_Programming/History

[^2]: http://www.javaworld.com/article/2077265/core-java/so-why-did-they-decide-to-call-it-java-.html

[^3]: http://www.freejavaguide.com/history.html

[^4]: http://nondot.org/sabre/

[^5]: https://en.wikipedia.org/wiki/Swift_(programming_language)

[^6]: https://www.youtube.com/watch?v=AzesJrOcFDU

[^7]: https://itunes.apple.com/us/book/the-swift-programming-language-swift-3-1/id881256329?mt=11

[^8]: https://developer.apple.com/reference/swift/mirror

[^9]: https://www.javatpoint.com/Garbage-Collection

[^10]: https://developer.apple.com/library/content/documentation/Swift/Conceptual/Swift_Programming_Language/AutomaticReferenceCounting.html

[^11]: https://developer.apple.com/swift/blog/?id=10

[^12]: https://en.wikipedia.org/wiki/Null_pointer

[^14]: https://developer.apple.com/library/content/documentation/Swift/Conceptual/Swift_Programming_Language/

[^15]: https://en.wikipedia.org/wiki/Thread_(computing)

[Java Documentation](https://docs.oracle.com/javase/8/)

[Swift Documentation](https://developer.apple.com/library/content/documentation/Swift/Conceptual/Swift_Programming_Language/index.html#//apple_ref/doc/uid/TP40014097-CH3-ID0)
