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

| Struct      | Class (Object) |
| :---        |    :--------:  |
| value type | reference type | 
| organized memory |  full object oriented functionality<br> (methods, data, virtual functions, <br>inheritance, etc) |

- When you copy a struct, you end up with two unique copies of the data

- When you copy a class, you end up with two references to one instance of the data

- **Struct** is faster than Class because: To store class, Apple first finds memory in Heap, then maintain the extra field to RETAIN count. Also, store reference of Heap into Stack. So when it comes to access part, it has to process stack and heap

</details>

<details>
<summary>
What is Class?
</summary>

A **class** is an object and how it works. i.e., a class is like a blueprint of an object
</details>

<details>
<summary>
What is Object?
</summary>
An object is an instance of a class
</details>

<details>
<summary>
What is interface?
</summary>

- Like a class, an interface defines methods

- Unlike a class, an interface never implements methods;

- classes that implement the interface implement the methods defined by the interface
</details>

<details>
<summary>
What are Functions?
</summary>
self contained chunks of code that perform specific tasks 
</details>

<details>
<summary>
What is Enum or Enumerations?
</summary>

- **Enumerations** define a finite number of states, and can bundle associated values with each individual state

- you can use them to model the state of your app and its internal processes
</details>


<details>
<summary>
Explain Guard statement
</summary>
a statement that is essentially a redirection or early exit of a statement or function to prevent crashing and incorrect data
</details>


<details>
<summary>
How to pass data between view controllers?
</summary>
There are 3 ways to pass data between view controllers.

- **Segue**, in prepareForSegue method (Forward) - visual connectors between view controllers in storyboards

- **Delegate** (Backward) - design pattern that allows one object to send messages to another object when a specific event happens.

- **Setting variable directly** (Forward) - getting/settings variables within classes 

</details>

<details>
<summary>
How to pass a variable as a reference?
</summary>
there are two types of variables: reference and value types. 

- by passing value type, the variable will create a copy of its data

- by passing reference type variable will just point to the original data in the memory

Arguments are passed by assignment. The rationale behind this is twofold:

- the parameter passed in is actually a reference to an object (but the reference is passed by value)

- some data types are mutable, but others aren't
</details>


# Swift Fundamentals

<details>
<summary>
What are the main advantages of Swift?
</summary>

- **Optional Types**, which make applications crash-resistant

- **Built-in error handling**

- **Closures**: self-contained blocks of functionality that can be passed around and used in your code

- **Much faster compared to other languages**

- **Type-safe language**

- **Supports pattern matching**
</details>

<details>
<summary>
Explain lazy in Swift?
</summary>

An initial value of the **lazy** stored properties is calculated only when the property is called for the first time
</details>

<details>
<summary>
 Explain generics in Swift?
</summary>

**Generics** create code that does not get specific about underlying data types

Provides for optimization of code by allowing us to know what type it is going to contain
</details>

<details>
<summary>
Explain defer?
</summary>

**defer** keyword which provides a block of code that will be executed in the case when execution is leaving the current scope
</details>

<details>
<summary>
Explain Compilation Conditions aka Conditional Compilation Blocks
</summary>
A conditional compilation block allows code to be conditionally compiled depending on the value of one or more compilation conditions.

Every conditional compilation block begins with the **#if** compilation directive and ends with the **#endif** compilation directive.

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
NSError is information about an error condition including a domain, a domain-specific error code, and application-specific information (i.e. user info dictionary).

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
Enums are not objects, so we don’t specify strong or weak
</details>

<details>
<summary>
What is @synthesize in Objective-C?
</summary>
Synthesize generates getter and setter methods for your property.
</details>


<details>
<summary>
What is the difference strong, weaks, read only and copy?
</summary>
strong, weak, assign property attributes define how memory for that property will be managed.

**Strong** means that the reference count will be increased and the reference to it will be maintained through the life of the object

**Weak** ( non-strong reference ), means that we are pointing to an object but not increasing its reference count. It’s often used when creating a parent child relationship. The parent has a strong reference to the child but the child only has a weak reference to the parent.

**Read-only**, we can set the property initially but then it can’t be changed.

**Copy** means that we’re copying the value of the object when it’s created. Also prevents its value from changing.

</details>

<details>
<summary>
What’s Code Coverage?
</summary>
Code coverage is a metric that helps us to measure the value of our unit tests.
</details>

<details>
<summary>
What’s Completion Handler?
</summary>
A completion handler is a closure (“a self-contained block of functionality that can be passed around and used in your code”). It gets passed to a function as an argument and then called when that function is done.

The completion handler takes a chunk of code with 3 arguments: **(NSData?, NSURLResponse?, NSError?)**

They're super convenient when making an API call, and we need to do something when that task is done, like updating the UI to show the data from the API call.
</details>


<details>
<summary>
What is Responder Chain?
</summary>

A **ResponderChain** is a hierarchy of objects that have the opportunity to respond to events received
</details>


<details>
<summary>
What is Regular expressions?
</summary>

**Regular expressions** are special string patterns that describe how to search through a string
</details>


<details>
<summary>
What is Operator Overloading?
</summary>

**Operator overloading** allows us to change how existing operators behave with types that both already exist. 

**Operators** are those symbols like `+`, `*`, and `/`
</details>

<details>
<summary>
Please explain Swift’s pattern matching techniques
</summary>

- **Tuple patterns** are used to match values of corresponding tuple types

- **Type-casting patterns** allow you to cast or match types

- **Wildcard patterns** match and ignore any kind and type of value

- **Optional patterns** are used to match optional values

- **Enumeration case patterns** match cases of existing enumeration types

- **Expression patterns** allow you to compare a given value against a given expression

</details>


<details>
<summary>
What is Downcasting?
</summary>
When we’re casting an object to another type in Objective-C, it’s pretty simple since there’s only one way to do it. In Swift, though, there are two ways to cast — one that’s safe and one that’s not.

- **as** used for upcasting and type casting to bridged type

- **as?** used for safe casting, return nil if failed

- **as!** used to force casting, crash if failed. should only be used when we know the downcast will succeed
</details>


<details>
<summary>
Explain the difference between SDK and Framework
</summary>

**SDK** is a set of software development tools. This set is used for the creation of applications. 

**Framework** is basically a platform which is used for developing software applications. It provides the necessary foundation on which the programs can be developed for a specific platform. 

SDK and Framework complement each other, and SDKs are available for frameworks.
</details>

<details>
<summary>
What is the difference between property and instance variable?
</summary>

**Property** is a more abstract concept. 

**Instance** variable is literally just a storage slot, as a slot in a struct. 

Normally other objects are never supposed to access them directly. Usually, a property will return or set an instance variable, but it could use data from several or none at all.
</details>

<details>
<summary>
What are the most important application delegate methods a developer should handle?
</summary>
The seven most important application delegate methods a developer should handle are:

- **application:willFinishLaunchingWithOptions**
    Method called when the launch process is initiated. This is the first opportunity to execute any code within the app.

- **application:didFinishLaunchingWithOptions**
    Method called when the launch process is nearly complete. Since this method is called is before any of the app’s windows are displayed, it is the last opportunity to prepare the interface and make any final adjustments.

- **applicationDidBecomeActive**
    Once the application has become active, the application delegate will receive a callback notification message via the method applicationDidBecomeActive.
    
    This method is also called each time the app returns to an active state from a previous switch to inactive from a resulting phone call or SMS.

- **applicationWillResignActive**
    There are several conditions that will spawn the **applicationWillResignActive** method. 
    
    Each time a temporary event, such as a phone call, happens this method gets called. It is also important to note that “quitting” an iOS app does not terminate the processes, but rather moves the app to the background.

- **applicationDidEnterBackground**
    This method is called when an iOS app is running, but no longer in the foreground. 
    
    In other words, the user interface is not currently being displayed. 
    
    The app has approximately five seconds to perform tasks and return. If the method does not return within five seconds, the application is terminated.

- **applicationWillEnterForeground**
    This method is called as an app is preparing to move from the background to the foreground. 
    
    The app, however, is not moved into an active state without the **applicationDidBecomeActive** method being called. This method gives a developer the opportunity to re-establish the settings of the previous running state before the app becomes active.

- **applicationWillTerminate**
    This method notifies your application delegate when a termination event has been triggered. 
    
    Hitting the home button no longer quits the application. 
    
    Force quitting the iOS app, or shutting down the device triggers the **applicationWillTerminate** method. This is an opportunity to save the application configuration, settings, and user preferences.

### Two more delegate functions come with iOS13

- **configurationForConnecting**
    It returns the configuration data for UIKit to use when creating a new scene.

- **didDiscardSceneSessions**
    This method is called as an app’s user closed one or more scenes via the app switcher.
</details>

<details>
<summary>
Why are completion handlers marked with @escaping?
</summary>
Because they are executed some point after the enclosing function has been executed.
</details>


# UI + Interface

<details>
<summary>
Explain View Controller Lifecycle events order?
</summary>
There are a few different lifecycle events:

- **loadView**

    Creates the view that the controller manages. It’s only called when the view controller is created and only when done programatically. It is responsible for making the view property exist in the first place.

- **viewDidLoad**

    Called after the controller’s view is loaded into memory. It’s only called when the view is created.

- **viewWillAppear**

    It’s called whenever the view is presented on the screen. In this step the view has bounds defined but the orientation is not applied.

- **viewWillLayoutSubviews**

    Called to notify the view controller that its view is about to layout its subviews. This method is called every time the frame changes

- **viewDidLayoutSubviews**

    Called to notify the view controller that its view has just laid out its subviews. Make additional changes here after the view lays out its subviews.

- **viewDidAppear**

    Notifies the view controller that its view was added to a view hierarchy.

- **viewWillDisappear**

    Before the transition to the next view controller happens and the origin view controller gets removed from screen, this method gets called.

- **viewDidDisappear**

    After a view controller gets removed from the screen, this method gets called. You usually override this method to stop tasks that are should not run while a view controller is not on screen.

- **viewWillTransition(to:with:)**

    When the interface orientation changes, UIKit calls this method on the window’s root view controller before the size changes are about to be made. The root view controller then notifies its child view controllers, propagating the message throughout the view controller hierarchy.
</details>

<details>
<summary>
How could you set up Live Rendering?
</summary>
The attribute @IBDesignable lets Interface Builder perform live updates on a particular view. 

**IBDesignable** requires Init frame to be defined as well in UIView class.

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

There are few common ways to specify the layout of elements in a UIView:

- Using **InterfaceBuilder**, you can add a **XIB** file to your project, layout elements within it, then load the XIB in your application code (either automatically, based on naming conventions, or manually)

- Also, using InterfaceBuilder you can create a storyboard for your application

- Use **NSLayoutConstraints** to have elements in a view arranged by Auto Layout

- Create **CGRects** describing the exact coordinates for each element and pass them to UIView

</details>

<details>
<summary>
What is UIStackView?
</summary>

**UIStackView** provides a way to layout a series of views horizontally or vertically. 

We can define how the contained views adjust themselves to the available space.
</details>

<details>
<summary>
How to Prioritize Usability in Design ?
</summary>
Broke down its design process to prioritize usability in 4 steps:

- Think like the user, then design the UX.

- Remember that users are people, not demographics.

- When promoting an app, consider all the situations in which it could be useful.

- Keep working on the utility of the app even after launch.
</details>

<details>
<summary>
What’s the difference between the frame and the bounds?
</summary>

The **bounds** of a UIView is the rectangle, expressed as a location (x,y) and size (width, height) relative to its own coordinate system (0,0). 

The **frame** of a UIView is the rectangle, expressed as a location (x,y) and size (width, height) relative to the superview or parent view it is contained within.

### This means a few things:

- If you create a view at X:0, Y:0, width:100, height:100, its frame and bounds are the same.

- If you move that view to X:100, its frame will reflect that change but its bounds will not. Remember, the bounds is relative to the view’s own space, and internally to the view nothing has changed.

- If you transform the view, e.g. rotating it or scaling it up, the frame will change to reflect that, but the bounds still won’t – as far as the view is concerned internally, it hasn’t changed.

Generally it’s better to modify bounds plus center and transform, and let UIKit calculate the frame for you.
</details>

<details>
<summary>
What is the bounding box?
</summary>
The bounding box is a term used in geometry; it refers to the smallest measure (area or volume) within which a given set of points.
</details>


# Concurrency & Parallelism

<details>
<summary>
What is a race condition?
</summary>

</details>

<details>
<summary>
What are two ways to achieve concurrency in iOS?
</summary>
Dispatch queues, Operation queues, handling threads manually.
</details>

<details>
<summary>
Which is the application thread from where UIKit classes should be used?
</summary>
The main thread.
</details>

<details>
<summary>
Explain Grand Central Dispatch (GCD)
</summary>

</details>

<details>
<summary>
Explain how queues are managed by GCD.
</summary>

</details>

<details>
<summary>
Describe the levels of priority for queues.
</summary>

- **.userInteractive** - interacting with users
    high

- **.userInitiated** - initiated/started by user 
    default

- **.utility**
    low

- **.background**
    background

</details>

<details>
<summary>
Explain NSOperation — NSOperationQueue — NSBlockOperation
</summary>

</details>

<details>
<summary>
What is Concurrency and Parallelism?
</summary>

- **Concurrency**: the ability to decompose a program, algorithm, or problem into smaller components or units that can be executed out-of-order, or in partial order, without affecting the final outcome. ie. **Concurrency** is the act of dividing up work.

- **Parallelism**: Parallel programming utilizes a shift from procedural tasks, which run sequentially, to tasks that run at the same time.

### Short of it:

- **Concurrency** is about dealing with lots of things at once.

- **Parallelism** is about doing lots of things at once

</details>

<details>
<summary>
Why do we use synchronized?
</summary>
Synchronized guarantees that only one thread can be executing that code in the block at any given time.
</details>

<details>
<summary>
What is the difference between Synchronous & Asynchronous task?
</summary>
Synchronous: waits until the task have completed 

Asynchronous: completes a task in the background and can notify you when complete
</details>

<details>
<summary>
Specify types of concurrency challenges: 
</summary>

- **Deadlocks**

- **Priority Inversion**

- **Race Conditions**

- **Critical Section**

- **Locking(mutexes, rendez vous, semaphores)**
    A **mutex** is like a token that passes from one thread to another, allowing one thread at a time to proceed.

    **rendez vous**: Threads that get to the rendezvous point wait until all the threads have reached the rendezvous point, and then they continue.     

</details>

<details>
<summary>
What are ways of executing work with GCD 
</summary>

- **Readers-Writers Problem**

- **DispatchWorkItem**

- **DispatchGroups**

- **Concurrent Loops**

- **Delayed Task Execution**

</details>


<details>
<summary>
What is Dynamic Dispatch?
</summary>
Dynamic Dispatch is the process of selecting which implementation of a polymorphic operation that’s a method or a function to call at run time. 

i.e When a class to override methods and properties declared in its superclasses
</details>

<details>
<summary>
Define a semaphore
</summary>
A data structure that is useful for solving a variety of synchronization problems
</details>

<details>
<summary>
What is the difference between a serial and a concurrent queue?
</summary>

- **Serial queues** (aka private dispatch queues) execute one task at a time in the order in which they are added to the queue

- **Concurrent queues** (also known as a type of global dispatch queue) execute one or more tasks concurrently, but tasks are still started in the order in which they were added to the queue
</details>

<details>
<summary>
How does the class DispatchSemaphore work
</summary>
An object that controls access to a resource across multiple execution contexts through use of a traditional counting semaphore.

Increment a semaphore count by calling **signal()**

Decrement a semaphore count by calling **wait()** or one of its variants that specifies a timeout.

#### Two components:

- **A threads queue** - used by the semaphore to keep track of waiting threads in FIFO order (The first thread entered to the queue will be the first to get access to the shared resource once it is available).

- **A counter value** - used by the semaphore to decide if a thread should get access to a shared resource or not. The counter value changes when we call signal() or wait() functions.

</details>

<details>
<summary>
Explain how Operations can be managed and when is the best situation to use Operations.
</summary>

Managed in a blockOperation, blockOperations are then used in

```class OperationQueue : NSObject``` 

**blockOperations** are a bridge between GCD and Operations 

- best used for developer control and code reusability 

</details>

<details>
<summary>
What are JSON/PLIST limits?
</summary>

</details>

<details>
<summary>
What are the states of an iOS App?
</summary>

- **Non-running** — The app is not running.

- **Inactive** — The app is running in the foreground, but not receiving events. An iOS app can be placed into an inactive state, for example, when a call or SMS message is received.

- **Active** — The app is running in the foreground, and receiving events.

- **Background** — The app is running in the background, and executing code.

- **Suspended** — The app is in the background, but no code is being executed.
</details>

# Design Patterns

<details>
<summary>
Why are design pattern important?
</summary>
Design patterns are reusable solutions to common problems in software design. They’re templates designed to help you write code that’s easy to understand and reuse. 

Most common Cocoa design patterns:
- **Creational**: Singleton.

- **Structural**: Decorator, Adapter, Facade.

- **Behavioral**: Observer, and, Memento
</details>


<details>
<summary>
What is Singleton Pattern ?
</summary>

</details>


<details>
<summary>
What is Facade Design Pattern?
</summary>

</details>

<details>
<summary>
What is Decorator Design Pattern?
</summary>

</details>

<details>
<summary>
What is Adapter Pattern?
</summary>

</details>

<details>
<summary>
What is Observer Pattern?
</summary>

</details>


<details>
<summary>
What is Memento Pattern?
</summary>

</details>

# Architecture

<details>
<summary>
Explain MVC
</summary>

</details>

<details>
<summary>
Explain MVVM
</summary>

</details>