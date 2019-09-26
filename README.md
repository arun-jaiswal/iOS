#### what is SOLID in oops programming
S — Single responsibility principle
every module or class should have responsibility over a single part of the functionality provided by the software.
O — Open/closed principle
software entities (classes, modules, functions, etc.) should be open for extensions, but closed for modification.
L — Liskov substitution principle
if S is a subtype of T, then objects of type T may be replaced (or substituted) with objects of type S.
I — Interface segregation principle
no client should be forced to depend on methods it does not use.Put more simply: Do not add additional functionality to an existing interface by adding new methods.
Instead, create a new interface and let your class implement multiple interfaces if needed.
D - Dependency inversion principle

#### how to hide/transparent navigation controller

#### oops concepts
#### what is GCD/Dispatch
Dispatch, also known as Grand Central Dispatch (GCD), contains language features, runtime libraries, and system enhancements that provide systemic, comprehensive improvements to the support for concurrent code execution on multicore hardware in macOS, iOS, watchOS, and tvOS.

Grand Central Dispatch (GCD) is a low-level API for managing concurrent operations.GCD provides three main types of queues:
1. Main queue: runs on the main thread and is a serial queue.
2. Global queues: concurrent queues that are shared by the whole system. There are four such queues with different priorities : high, default, low, and background. The background priority queue has the lowest priority and is throttled in any I/O activity to minimize negative system impact.
3. Custom queues: queues that you create which can be serial or concurrent. Requests in these queues actually end up in one of the global queues.

### Closures
 self-contained functions organized as blocks and called anywhere like C and Objective C languages.
 ```swift
 let studname = { print("Welcome to Swift Closures") }
studname()//Welcome to Swift Closures


let divide = {
   (val1: Int, val2: Int) -> Int in 
   return val1 / val2 
}

let result = divide(200, 20)
print (result)//10


```
### Synchronous vs. Asynchronous
A synchronous function returns control to the caller after the task completes. You can schedule a unit of work synchronously by calling DispatchQueue.sync(execute:).
An asynchronous function returns immediately, ordering the task to start but not waiting for it to complete. Thus, an asynchronous function does not block the current thread of execution from proceeding on to the next function. You can schedule a unit of work asynchronously by calling DispatchQueue.async(execute:).

### singleton
The singleton pattern guarantees that only one instance of a class is instantiated.
It’s initialize your class instance single time only with static property and it will share your class instance globally.
```swift
class LocationManager{
    
    static let shared = LocationManager()
    
    var locationGranted: Bool?
    //Initializer access level change now
    private init(){}//now we cant not create class object directly because init is private now
    
    func requestForLocation(){
        //Code Process  
        locationGranted = true     
        print("Location granted")
    }
    
}
//Access class function in a single line
LocationManager.shared.requestForLocation() // "Location granted"
//Access variable value
print(LocationManager.shared.locationGranted ?? false) // true

```

#### different between unowned weak property
If you can guarantee that the reference will not be nil at its point of use, use unowned. If not, then you should be using weak.
#### stored property and computed property
https://apple-swift.readthedocs.io/en/latest/StoredAndComputedVariables.html

#### protocol
    Protocols can include declarations for both instance methods and class methods, as well as properties. 
    A protocol defines a blueprint of methods, properties, and other requirements that suit a particular task or piece of functionality. 
    The protocol can then be adopted by a class, structure, or enumeration to provide an actual implementation of those requirements. 
    Any type that satisfies the requirements of a protocol is said to conform to that protocol.

Protocol structure
```swift
protocol SomeProtocol {
    // protocol definition goes here
 }
 ```

Multiple protocols can be listed, and are separated by commas:
```swift
    struct SomeStructure: FirstProtocol, AnotherProtocol {
    // structure definition goes here
    }
```
If a class has a superclass, list the superclass name before any protocols it adopts, followed by a comma:
  ```swift
  class SomeClass: SomeSuperclass, FirstProtocol, AnotherProtocol {
    // class definition goes here
  }
```
Gettable and settable properties are indicated by writing { get set } after their type declaration, and gettable properties are indicated by writing { get }.
```swift
  protocol SomeProtocol {
    var mustBeSettable: Int { get set }
    var doesNotNeedToBeSettable: Int { get }
  }
  ```
  
  Always prefix type property requirements with the static keyword when you define them in a protocol. This rule pertains even though type property requirements can be prefixed with the class or static keyword when implemented by a class:
```swift
protocol AnotherProtocol {
    static var someTypeProperty: Int { get set }
}
```

### use of bacltick in `Swift
Backticks (`) are used as a name and to surround the keyword in the case if you want to give the same name as a reserved Swift keyword to a constant or a variable. But it is strongly advised to ignore the keyword unless you have no choice available

### Adapter and Memento pattern
Adapter – It lets the classes with incompatible interfaces to work together and it wraps itself around the object to expose a standard interface to interact with that object.Memento – This pattern in iOS is used as a part of state restoration.
That is this externalized state can be restored without violating any encapsulation.This pattern is especially used for the archiving in Apple.

### bounding box
The bounding box is a term used in geometry; it refers to the smallest measure (area or volume) within which a given set of points

## Properties
In Swift, properties defined with a simple let or var and are strong by default. They can be declared as weak or unowned references with weak and unowned keywords before let/var. Swift properties in types are called stored properties.
### Strong
the reference count will be increased and the reference to it will be maintained through the life of the object
### Weak
means that we are pointing to an object but not increasing its reference count. It’s often used when creating a parent child relationship. The parent has a strong reference to the child but the child only has a weak reference to the parent
Automatically changes itself to nil
### Read-only
we can set the property initially but then it can’t be changed
### Copy
means that we’re copying the value of the object when it’s created. Also prevents its value from changing

### dependency injection
pods,carthage

## declaration modifiers in Swift
1. Final
2. dynamic
### final Class 
by marking a class declaration with the final keyword, we inform the compiler that the class cannot be subclassed. This allows the compiler to make a number of optimizations to increase performance

### Dynamic dispatch
Dynamic dispatch. 
Swift allows a class to override methods and properties declared in its superclasses. This means that the program has to determine at runtime which method or property is being referred to and then perform an indirect call or indirect access. This technique, called dynamic dispatch
It simply means that the Objective-C runtime decides at runtime which implementation of a particular method or function it needs to invoke. 
For example, if a subclass overrides a method of its superclass, dynamic dispatch figures out which implementation of the method needs to be invoked, that of the subclass or that of the parent class. This is a very powerful concept
Swift uses the Swift runtime whenever possible. Swift runtime chooses other options, such as static and virtual dispatch, over dynamic dispatch whenever possible. It does this to increase performance.Static and virtual dispatch are much faster than dynamic dispatch

### difference between the frame and the bounds
The bounds of a UIView is the rectangle, expressed as a location (x,y) and size (width, height) relative to its own coordinate system (0,0). 
The frame of a UIView is the rectangle, expressed as a location (x,y) and size (width, height) relative to the superview it is contained within.

### Responder Chain
ResponderChain is a hierarchy of objects that have the opportunity to respond to events received

### Operator Overloading

### What is TVMLKit?
TVMLKit is the glue between TVML, JavaScript, and your native tvOS application

### Platform limitations of tvOS
1. no browser support of any kind, nor is there any WebKit or other web-based rendering engine you can program against
2. cannot explicitly use local storage.At product launch, the devices ship with either 32 GB or 64 GB of hard drive space, but apps are not permitted to write directly to the onboard storage.

### What is ABI

### Cocoa design patterns
**Creational:** Singleton
**Structural:** Decorator, Adapter, Facade
**Behavioral:** Observer, and, Memento
### Singleton Pattern
The Singleton design pattern ensures that only one instance exists for a given class and that there’s a global access point to that instance. It usually uses lazy loading to create the single instance when it’s needed the first time.
### Facade Design Pattern
The Facade design pattern provides a single interface to a complex subsystem. Instead of exposing the user to a set of classes and their APIs, you only expose one simple unified API.
### Decorator Design Pattern
The Decorator pattern dynamically adds behaviors and responsibilities to an object without modifying its code. It’s an alternative to subclassing where you modify a class’s behavior by wrapping it with another object.
In Objective-C there are two very common implementations of this pattern: Category and Delegation. In Swift there are also two very common implementations of this pattern: Extensions and Delegation.
### Adapter Pattern
An Adapter allows classes with incompatible interfaces to work together. It wraps itself around an object and exposes a standard interface to interact with that object.

### Observer Pattern
In the Observer pattern, one object notifies other objects of any state changes.
Cocoa implements the observer pattern in two ways: Notifications and Key-Value Observing (KVO).
### Memento Pattern

### MVC
**Models** — responsible for the domain data or a data access layer which manipulates the data, think of ‘Person’ or ‘PersonDataProvider’ classes.

**Views** — responsible for the presentation layer (GUI), for iOS environment think of everything starting with ‘UI’ prefix.

**Controller/Presenter/ViewModel** — the glue or the mediator between the Model and the View, in general responsible for altering the Model by reacting to the user’s actions performed on the View and updating the View with changes from the Model.

### MVVM
UIKit independent representation of your View and its state. The View Model invokes changes in the Model and updates itself with the updated Model, and since we have a binding between the View and the View Model, the first is updated accordingly.
Your view model will actually take in your model, and it can format the information that’s going to be displayed on your view.
There is a more known framework called RxSwift. It contains RxCocoa, which are reactive extensions for Cocoa and CocoaTouch.
### What is Concurrency 
Concurrency is dividing up the execution paths of your program so that they are possibly running at the same time. The common terminology: process, thread, multithreading, and others. Terminology;
Process, An instance of an executing app
**Thread**, Path of execution for code
**Multithreading**, Multiple threads or multiple paths of execution running at the same time.
**Concurrency**, Execute multiple tasks at the same time in a scalable manner.
**Queues**, Queues are lightweight data structures that manage objects in the order of First-in, First-out (FIFO).
Synchronous vs Asynchronous tasks
### Grand Central Dispatch (GCD)
GCD is a library that provides a low-level and object-based API to run tasks concurrently while managing threads behind the scenes. Terminology;
**Dispatch Queues**, A dispatch queue is responsible for executing a task in the first-in, first-out order.
**Serial Dispatch Queue** A serial dispatch queue runs tasks one at a time.
**Concurrent Dispatch Queue** A concurrent dispatch queue runs as many tasks as it can without waiting for the started tasks to finish.
**Main Dispatch Queue** A globally available serial queue that executes tasks on the application’s main thread.
### Readers-Writers
**Race Condition** A race condition occurs when two or more threads can access shared data and they try to change it at the same time.
**Deadlock** A deadlock occurs when two or sometimes more tasks wait for the other to finish, and neither ever does.
**Readers-Writers** problem Multiple threads reading at the same time while there should be only one thread writing.
Readers-writer lock Such a lock allows concurrent read-only access to the shared resource while write operations require exclusive access.
**Dispatch Barrier Block** Dispatch barrier blocks create a serial-style bottleneck when working with concurrent queues.

### Swift’s pattern matching techniques
Tuple patterns are used to match values of corresponding tuple types.
Type-casting patterns allow you to cast or match types.
Wildcard patterns match and ignore any kind and type of value.
Optional patterns are used to match optional values.
Enumeration case patterns match cases of existing enumeration types.
Expression patterns allow you to compare a given value against a given expression.

### closures
Functions are actually a special case of closures: blocks of code that can be called later
You can write a closure without a name by surrounding code with braces ({}). Use in to separate the arguments and return type from the body.

### One of the most important differences between structures and classes is that structures are always copied when they are passed around in your code, but classes are passed by reference.

### mutating
mutating keyword in the declaration of structure function to mark a method that modifies the structure.

```swift
struct SimpleStructure: ExampleProtocol {
    var simpleDescription: String = "A simple structure"
    mutating func adjust() {
        simpleDescription += " (adjusted)"
    }
}
```
