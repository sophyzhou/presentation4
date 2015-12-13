
#Objective-C Classes and Objects


Class and object are very important concepts in object-oriented programming. A class provides the blueprint for object which describes the properties and behaviors common to the object. An object is an instance of a class, which stores its properties in variables and exposes its behavior through methods. 

In OS X or iOS development, Cocoa and Cocoa Touch provide us a large libraray of existing objects available to use.In this way, we don’t need to create objects from scratch to solve every conceivable problem. Basic data types(like strings and numbers) and user interface elements(like buttons and table views) are immediately usable. On the other hand, some objects are designed for us to customize with our own code to behave in the way we want. 


  [<i class="icon-file"></i>Classes Definition](#classes-definition)  
  
 [<i class="icon-file"></i>Properties](#properties)  
 
 [<i class="icon-file"></i>Objects Allocation and Initialization](#objects-allocation-and-initialization)  
 
  [<i class="icon-file"></i>Data Members Access](#data-members-access)  
 

##Classes Definition

In Objective-C, class is defined in two different sections by using **@interface** and **@implementation**. By declaring an *interface*, we describe the way we want the class and its instances to be used. This interface includes the list of messages that the class can receive, so we also need to provide the class *implementation*, which contains the code to be executed in response to each message.  

A class definition begins with the keyword **@interface** followed by the class name and the class body, enclosed by a pair of curly braces.  
 
For example, we defined the *Rectangle* data type using the keyword @interface as follows:

```
@interface Rectangle:NSObject
{
    //Instance variables
    double length;   // length of the rectangle
    double width;  // width of the rectangle
}

// Property
@property(nonatomic, readwrite) double width; 

@end
```

In Objective-C, **NSObject** is the superclass of all Objective-C classes which provides basic methods like memory allocation and initialization.   


##Properties
Defining property is a robust way to handle object’s data. The properties are introduced in Objective-C to ensure that the instance variable of the class can be accessed properly outside the class. In other words, we need to define a property if we want a single piece of data (or a class object member) to be visible to other classes.    

First, as we have seen in the above code, properties is declared by using keyword **@property**.Then this keyword is followed with *property attribute*, which define how the property behaves. Here the property attributes are *nonatomic* and *readwrite* in above sample code. Then it is followed by the datatype of the variable. Some commonly used attributes are summarized below.

"
- **getter=**: 	Use a custom name for the getter method.
- **setter=**: 	Use a custom name for the setter method.
- **readwrite** : Give read and write access to the property.
- **readonly**:	 Prevent overwriting of the property value. 
- **nonatomic**: Make the compiler not check what other threads are executing over the value at the same time. If you are not doing some heavy thread work, using nonatomic property could speed up your code.
- **strong**:	Create an owning relationship between the property and the assigned value. This is the default for object properties.
- **weak**:	Create a non-owning relationship between the property and the assigned value. Use this to prevent retain cycles.
- **copy**:	Create a copy of the assigned value instead of referencing the existing instance.
- **retain**:  The retain attribute, instructs the setter to retain the value when it’s being assigned and release the previous value if set.   
"

referenced from: http://rypress.com/tutorials/objective-c/properties

After we define the property in the class interface, we need to also define the **property implementation** as below:

```
@implementation Rectangle

@synthesize width; 

-(id)init
{
   self = [super init];
   length = 3.0;
   return self;
}

-(double) area
{
   return length*width;
}

@end
```

##Objects Allocation and Initialization
An object is created from a class. We declare objects of a class with exactly the same sort of declaration that we declare variables of basic types. We often create instances of classes by calling **alloc**. This is a class method of NSObject, and it is available to any class in the frameworks or in our own code. We simply send a message to the class, and then we get back a new instance. Following statements declare an object of class *Rectangle*:
```
// Create rectangle1 object of type Rectangle
Rectangle *rectangle1 = [Rectangle alloc];   
```

After that, we initialize the newly created instance with a call to **init** method.
```
rectangle1 = [rectangle1 init];
```

We can combine these two messages into one line of code. 

```
Rectangle *rectangle1 = [[Rectangle alloc]init];
```



##Data Members Access

Here is an executable sample code with main method provided to check that whether we can access the data members. We declared two instances of *Rectangle* class and calculated their areas respectively by using their specific widths. 

```
#import <Foundation/Foundation.h>

@interface Rectangle:NSObject
{
    //Instance variables
    double length;   // length of the rectangle
    double width;  // width of the rectangle
}

// Property
@property(nonatomic, readwrite) double width; 

@end

@implementation Rectangle

@synthesize width; 

-(id)init
{
   self = [super init];
   length = 3.0;
   return self;
}

-(double) area
{
   return length*width;
}

@end

int main( )
{
   NSAutoreleasePool * pool = [[NSAutoreleasePool alloc] init];    
   Rectangle *rectangle1 = [[Rectangle alloc]init];    
   Rectangle *rectangle2 = [[Rectangle alloc]init];    

   double area = 0.0;     // Store the area of a Rectangle here
 
   // rectangle 1 specification
   rectangle1.width = 5.0; 

   // rectangle 2 specification
   rectangle2.width = 10.0;
  
   // area of rectangle 1
   area = [rectangle1 area];
   NSLog(@"Area of Rectangle1 : %f", area);
   // area of rectangle 2
   area = [rectangle2 area];
   NSLog(@"area of Rectangle2 : %f", area);
   [pool drain];
   return 0;
}
```

When the above code is compiled and executed, we will have the result as below: 

![Alt text](/image/classes_objects.png) 

