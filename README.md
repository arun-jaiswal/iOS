#### what is SOLID in oops programming
#### how to hide/transparent navigation controller
#### oops concepts
#### what is GCD
#### different between unowned weak property
#### stored property and computed property
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
