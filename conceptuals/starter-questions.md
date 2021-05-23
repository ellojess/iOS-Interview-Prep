<!-- TABLE OF CONTENTS -->
<details open="open">
  <summary>Table of Contents</summary>
  <ol>
    <li><a href="#General-CS">General CS</a></li>
    <li><a href="#Swift-Fundamentals">Swift Fundamentals</a></li>
    <li><a href="#UI-&-Interface">UI & Interface</a></li>
    <li><a href="#Concurrency-&-Parallelism">Concurrency & Parallelism</a></li>
    <li><a href="#Design-Patterns">Design Patterns</a></li>
    <li><a href="#Architecture">Architecture</a></li>
  </ol>
</details>

# General CS

<details>
<summary>
When and why do we use an object as opposed to a struct?
</summary>
A: 
</details>

<details>
<summary>
What is Class?
</summary>
A: 
</details>

<details>
<summary>
What is Object?
</summary>
A: 
</details>

<details>
<summary>
What is interface?
</summary>
A: 
</details>

<details>
<summary>
What are Functions?
</summary>
A: 
</details>

<details>
<summary>
What is Enum or Enumerations?
</summary>
A: 
</details>


<details>
<summary>
Explain Guard statement
</summary>
A: 
</details>


<details>
<summary>
How to pass data between view controllers?
</summary>
A: 
</details>

<details>
<summary>
How to pass a variable as a reference?
</summary>
A: 
</details>


# Swift Fundamentals

<details>
<summary>
What is the Swift main advantage?
</summary>
A: 
</details>

<details>
<summary>
Explain lazy in Swift?
</summary>
A: 
</details>

<details>
<summary>
 Explain generics in Swift?
</summary>
A: 
</details>

<details>
<summary>
Explain defer?
</summary>
A: 
</details>

<details>
<summary>
Explain Compilation Conditions aka Conditional Compilation Blocks
</summary>
A: 

### Sample Code

```Swift
#if compiler(>=5)
print("Compiled with the Swift 5 compiler or later")
#endif
#if swift(>=4.2)
print("Compiled in Swift 4.2 mode or later")
#endif
#if compiler(>=5) && swift(<5)
print("Compiled with the Swift 5 compiler or later in a Swift mode earlier than 5")
#endif
// Prints "Compiled with the Swift 5 compiler or later"
// Prints "Compiled in Swift 4.2 mode or later"
// Prints "Compiled with the Swift 5 compiler or later in a Swift mode earlier than 5"
```
</details>

<details>
<summary>
What is made up of NSError object?
</summary>
A: 

### Sample Code

```Swift
init(domain: String, code: Int, userInfo: [String : Any]?)
// Returns an NSError object initialized for a given domain and code with a given userInfo dictionary.
```
</details>



<details>
<summary>
Why don’t we use strong for enum property
</summary>
A: 
</details>

<details>
<summary>
What is @synthesize in Objective-C?
</summary>
A: 
</details>


<details>
<summary>
What is the difference strong, weaks, read only and copy?
</summary>
A: 
</details>

<details>
<summary>
What’s Code Coverage?
</summary>
A: 
</details>

<details>
<summary>
What’s Completion Handler?
</summary>
A: 
</details>


<details>
<summary>
What is Responder Chain?
</summary>
A: 
</details>


<details>
<summary>
What is Regular expressions?
</summary>
A: 
</details>


<details>
<summary>
What is Operator Overloading?
</summary>
A: 
</details>


<details>
<summary>
What is Responder Chain?
</summary>
A: 
</details>



<details>
<summary>
Please explain Swift’s pattern matching techniques
</summary>
A: 
</details>


<details>
<summary>
What is Downcasting?
</summary>
A: 
</details>


<details>
<summary>
Explain the difference between SDK and Framework
</summary>
A: 
</details>

<details>
<summary>
What are the most important application delegate methods a developer should handle?
</summary>
A: 
</details>

<details>
<summary>
Why are completion handlers marked with @escaping?
</summary>
A: 
</details>


# UI + Interface

<details>
<summary>
Explain View Controller Lifecycle events order?
</summary>
A: 
</details>

<details>
<summary>
How could you set up Live Rendering?
</summary>
A: 

### Sample Code

```Swift 
@IBDesignable 
class MyCustomView: UIView {
   let textLabel = UILabel()

   required init(coder aDecoder: NSCoder) {
         super.init(coder: aDecoder)!
         setupView()
   }
   override init(frame: CGRect) {
          super.init(frame: frame)
          setupView()
   }
```
</details>

<details>
<summary>
What are the different ways to specify the layout of elements in UIView?
</summary>
A: 
</details>

<details>
<summary>
What is UIStackView?
</summary>
A: 
</details>

<details>
<summary>
How to Prioritize Usability in Design ?
</summary>
A: 
</details>

<details>
<summary>
What’s the difference between the frame and the bounds?
</summary>
A: 
</details>

<details>
<summary>
What is the bounding box?
</summary>
A: 
</details>


# Concurrency & Parallelism

<details>
<summary>
What is a race condition?
</summary>
A: 
</details>

<details>
<summary>
What are two ways to achieve concurrency in iOS?
</summary>
A: 
</details>

<details>
<summary>
Which is the application thread from where UIKit classes should be used?
</summary>
A: 
</details>

<details>
<summary>
Explain Grand Central Dispatch (GCD)
</summary>
A: 
</details>

<details>
<summary>
Explain how queues are managed by GCD.
</summary>
A: 
</details>

<details>
<summary>
Describe the levels of priority for queues.
</summary>
A: 
</details>

<details>
<summary>
Explain NSOperation — NSOperationQueue — NSBlockOperation
</summary>
A: 
</details>

<details>
<summary>
What is Concurrency and Parallelism?
</summary>
A: 
</details>

<details>
<summary>
Why do we use synchronized?
</summary>
A: 
</details>

<details>
<summary>
What is the difference between Synchronous & Asynchronous task?
</summary>
A: 
</details>

<details>
<summary>
Specify types of concurrency challenges: 
</summary>
A: 
</details>

<details>
<summary>
What are ways of executing work with GCD 
</summary>
A: 
</details>


<details>
<summary>
What is Dynamic Dispatch?
</summary>
A: 
</details>

<details>
<summary>
Define a semaphore
</summary>
A: 
</details>

<details>
<summary>
What is the difference between a serial and a concurrent queue?
</summary>
A: 
</details>

<details>
<summary>
How does the class DispatchSemaphore work
</summary>
A: 
</details>

<details>
<summary>
Explain how Operations can be managed and when is the best situation to use Operations.
</summary>
A: 
</details>


<details>
<summary>
What are JSON/PLIST limits?
</summary>
A: 
</details>

<details>
<summary>
What are the states of an iOS App?
</summary>
A: 
</details>

# Design Patterns

<details>
<summary>
Why are design pattern important?
</summary>
A: 
</details>


<details>
<summary>
What is Singleton Pattern ?
</summary>
A: 
</details>


<details>
<summary>
What is Facade Design Pattern?
</summary>
A: 
</details>

<details>
<summary>
What is Decorator Design Pattern?
</summary>
A: 
</details>

<details>
<summary>
What is Adapter Pattern?
</summary>
A: 
</details>

<details>
<summary>
What is Observer Pattern?
</summary>
A: 
</details>


<details>
<summary>
What is Memento Pattern?
</summary>
A: 
</details>

# Architecture

<details>
<summary>
Explain MVC
</summary>
A: 
</details>

<details>
<summary>
Explain MVVM
</summary>
A: 
</details>