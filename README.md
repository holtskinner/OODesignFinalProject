# OO Design Final Project
**Holt Skinner 🤓 & Kyle Whitney ♿️**

*CS 4330 Spring 2017*

Java
<img src="JavaLogo.png" alt="Java" width="50">

Swift
<img src="SwiftLogo.png" alt="Swift" width="50">

> Computer Science is about as close to magic you can get, if you're smart enough. ~ Dale Musser

>  An analysis of Java and Swift based on Object-Oriented Design Principles.

## Language Purpose & Origins
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

## Unique Features
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

## Reflection
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

## Memory Management
🤓

## Comparison of Values and References
🤓

## Null/nil References
🤓

## Singleton
🤓

## Procedural Programming
🤓

## Functional Programming
♿️

## Threads
🤓

## Sources

[^1]: https://en.wikibooks.org/wiki/Java_Programming/History

[^2]: http://www.javaworld.com/article/2077265/core-java/so-why-did-they-decide-to-call-it-java-.html

[^3]: http://www.freejavaguide.com/history.html

[^4]: http://nondot.org/sabre/

[^5]: https://en.wikipedia.org/wiki/Swift_(programming_language)

[^6]: https://www.youtube.com/watch?v=AzesJrOcFDU

[^7]: https://itunes.apple.com/us/book/the-swift-programming-language-swift-3-1/id881256329?mt=11

[^8]: https://developer.apple.com/reference/swift/mirror
[Java Documentation](https://docs.oracle.com/javase/8/)

[Swift Documentation](https://developer.apple.com/library/content/documentation/Swift/Conceptual/Swift_Programming_Language/index.html#//apple_ref/doc/uid/TP40014097-CH3-ID0)
