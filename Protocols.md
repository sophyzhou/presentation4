
#Objective-C Protocols

A protocol is a group of related properties and methods that can be implemented by *any class*, and is used to declare methods and properties that are independent of any specific class.  

In this chapter we will discuss the syntax to define a protocol, and explains how to mark a class interface as *conforming to* a protocol, which means that the class must implement the required methods.


  [<i class="icon-file"></i>Creating Protocols](#creating-protocols)  
  
  [<i class="icon-file"></i>Conforming to Protocols](#conforming-to-protocols)  
    
 

##Creating Protocols
A syntax of protocol is shown below.

```
@protocol MyProtocol
@required
// list of required methods and properties
@optional
// list of optional methods and properties
@end
```

Protocols can include declarations for both methods and properties. Keyword **@required** means the methods under @required must be implemented in the classes that conforms to the protocol;  Keyword **@optional** means methods under **@optional** keyword are optional to implement. Defining these characteristics in a protocol lets you apply them to any objects instead of forcing them to inherit from the same abstract superclass.

##Conforming to Protocols

Here is the syntax for class conforming to protocol:

```
@interface MyClass : NSObject <MyProtocol>
...
@end
```

The above code means that any instance of *MyClass* will respond not only to the methods declared specifically in the interface, but that *MyClass* also provides implementations for the required methods in *MyProtocol*. Since the adoption of the protocol is sufficient, we do not need to redeclare the protocol methods in the class interface.

When you want a class to apply multiple protocols, you can specify them as a comma-separated list, like this:


```
@interface MyClass : NSObject <MyProtocol, MySecondProtocol, MyThirdProtocol>
...
@end
```

After we have indicated conformance to a protocol, the class has to provide implementations of methods for each of the required protocol methods. And you can choose any optional methods to implement when they are needed.  The compiler will warn you if you fail to implement any of the required methods.


