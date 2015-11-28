
#Objective-C Classes and Objects


Objects in Objective-C are just like objects in other object-oriented programming languages: they package data with related behavior. An object is an instance of a class. Class is blueprint for object which describes the behavior and properties common to any particular type of object. 

In OS X or iOS development, we don’t need to create objects from scratch to solve every conceivable problem; instead we have a large library of existing objects available to use, provided by Cocoa and Cocoa Touch.

Basic data types(like strings and numbers) and user interface elements(like buttons and table views) are immediately usable.  On the other hand, some objects are designed for us to customize with our own code to behave in the way we want. 


  [<i class="icon-file"></i>Relation with C and C++](#relation-with-c-and-c)  
  
 [<i class="icon-file"></i>Benefits of Objective-C](#benefits-of-objective-c)  
 
 [<i class="icon-file"></i>Framework](#framework)  
 
 

##Defining Classes

In Objective-C, the class is defined in two different sections namely **@interface** and **@implementation**. In this part, we are going to talk about how to define classes in Objective-C by declaring an interface, which describes the way we intend the class and its instances to be used. This interface includes the list of messages that the class can receive, so we also need to provide the class implementation, which contains the code to be executed in response to each message.

A class definition starts with the keyword **@interface** followed by the interface(class) name; and the class body, enclosed by a pair of curly braces. In Objective-C, all classes are derived from the base class called **NSObject**. It is the superclass of all Objective-C classes. It provides basic methods like memory allocation and initialization.   

For example, we defined the *Rectangle* data type using the keyword class as follows:

```
@interface Rectangle:NSObject
{
    //Instance variables
    double length;   // length of the rectangle
    double width;  // width of the rectangle
}
@property(nonatomic, readwrite) double width; // Property

@end
```

##Properties
Properties are introduced in Objective-C to ensure that the instance variable of the class can be accessed properly outside the class. As we have seen in the above code, properties is declared by  using keyword **@property**.  This keyword is followed with *access specifiers*, which are *nonatomic* and *readwrite* in above code.  


##Allocating and initializing Objective-C Objects

##Accessing the Data Members

##Properties
