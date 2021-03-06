
#Objective-C Protocols

A protocol is a group of related properties and methods that can be implemented by *any class*, and is used to declare methods and properties that are independent of any specific class.  

In this chapter we will discuss the syntax to define a protocol, and explains how to mark a class interface as *conforming to* a protocol, which means that the class must implement the required methods.


  [<i class="icon-file"></i>Creating Protocols](#creating-protocols)  
  
  [<i class="icon-file"></i>Conforming to Protocols](#conforming-to-protocols)  
    
 

##Creating Protocols
A syntax of protocol is shown below.

```
@protocol SophiaProtocol
@required
// list of required methods and properties
@optional
// list of optional methods and properties
@end
```

Protocols can include declarations for both methods and properties. Keyword **@required** means the methods under @required must be implemented in the classes that conforms to the protocol;  Keyword **@optional** means methods under **@optional** keyword are optional to implement. Defining these characteristics in a protocol lets you apply them to any objects instead of forcing them to inherit from the same abstract superclass.

##Conforming to Protocols

Here is the syntax for a class named *SophiaClass* conforming to a protocol named *SophiaProtocol*:

```
@interface SophiaClass : NSObject <SophiaProtocol>
...
@end
```

The above code means that any instance of *SophiaClass* will respond not only to the methods declared specifically in the interface, but that *SophiaClass* also provides implementations for the required methods in *SophiaProtocol*. Since the adoption of the protocol is sufficient, we do not need to redeclare the protocol methods in the class interface.

In order to apply multiple protocols, you can specify them as a comma-separated list, like this:

```
@interface SophiaClass : NSObject <FirstProtocol, SecondProtocol, ThirdProtocol>
...
@end
```

After we make the class conform to a protocol, the class has to provide implementations of methods for each of the required protocol methods. And you can choose any optional methods to implement when they are needed. The compiler will warn you if you fail to implement any of the required methods.


