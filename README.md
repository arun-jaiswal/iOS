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


