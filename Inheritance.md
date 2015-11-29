
#Objective-C Inheritance and 	Polymorphism


  [<i class="icon-file"></i>Inheritance Conception](#inheritance-conception)  
    
  [<i class="icon-file"></i>Method Overriding](#method-overriding)  
  
  [<i class="icon-file"></i>Inheritance Example](#inheritance-example)  
 
  [<i class="icon-file"></i>Polymorphism](#polymorphism)  

##Inheritance Conception

In the natural world, taxonomy defines groups of biological organisms on the basis of shared characteristics and giving names to those groups like species, genus, and family. These groups are hierarchical, such that groups of a given rank can be aggregated to form a super group of higher rank: multiple species may belong to one genus, and multiple genera to one family. 

As shown in the figure below, although Humans and Gorillas are differenct species, they share a lot of common similarities and they are taxonomically related since they all belong to the same Hominidae family.


![Alt text](/image/humansgorillas.png) 
Source: https://developer.apple.com/library/mac/documentation/Cocoa/Conceptual/ProgrammingWithObjectiveC/DefiningClasses/DefiningClasses.html#//apple_ref/doc/uid/TP40011210-CH3-SW1

The concept of *inheritance* brings something from a natural world perspective to programming world. In the world of object-oriented programming, objects are also categorized into hierarchical groups. The class at the top of the hierarchy is known as the **base class** or **root class** and the derived classes as **subclasses** or **child classes**. The class from which a subclass is derived is called the **parent class**. 

In the same way that humans and Gorillas inherit certain characteristics as members of the Hominidae family, the derived class inherits all of the features of the parent class and also adds some features of its own or *override* some methods in the parent class.

Objective-C only support *single inheritance* which means a subclass can only be derived from a single direct parent class. While any number of subclasses may be derived from a class.  

Classes need not only be derived from a root class. A subclass can also inherit from another subclass.


##Method Overriding




##Inheritance Example

Here is a simple example of how inheritance works in objective-C.
First of all, we define the parent class, *Shape* class. Two methods, printArea() and calculateArea() are defined.  The calculateArea() method is empty which waits to be implemented in the subclasses.  

```
#import <Foundation/Foundation.h>

@interface Shape : NSObject

{
    double area;
}

- (void)printArea;
- (void)calculateArea;
@end

@implementation Shape

- (void)printArea{
    NSLog(@"The area is %f", area);
}

- (void)calculateArea{

}

@end

```

Here we inherit our *Square* class from the parent class *Shape* . We override the printArea() method and we implement the calculateArea() method. 

```
@interface Square : Shape
{
    double length;
}

- (id)initWithSide:(double)side;

- (void)calculateArea;

@end

@implementation Square

- (id)initWithSide:(double)side{
    length = side;
    return self;
}

- (void)calculateArea{
    area = length * length;
}

- (void)printArea{
    NSLog(@"The area of square is %f", area);
}


@end
```

Here we inherit our *Rectangle* class from the parent class *Shape* . Here we keep the printArea() method the same as the one in parent class and we implement the calculateArea() method in a different way from that in *Square* class. 
```
@interface Rectangle : Shape
{
    double length;
    double breadth;
}

- (id)initWithLength:(double)rLength andBreadth:(double)rBreadth;


@end

@implementation Rectangle

- (id)initWithLength:(double)rLength andBreadth:(double)rBreadth{
    length = rLength;
    breadth = rBreadth;
    return self;
}

- (void)calculateArea{
    area = length * breadth;
}

@end
```

Finally, we define our main method to test the inheritance. 
```

int main(int argc, const char * argv[])
{
    NSAutoreleasePool * pool = [[NSAutoreleasePool alloc] init];
    
    Square *square = [[Square alloc]initWithSide:10.0];
    [square calculateArea];
    [square printArea];
    
    Rectangle *rect = [[Rectangle alloc]
    initWithLength:10.0 andBreadth:5.0];
    [rect calculateArea];
    [rect printArea];       
     
    [pool drain];
    return 0;
}

```

[inheritance.md]

From the result we can find that, when the instance square calls the printArea() method, the overriden method in *Square* class is called; while when the instance rectangle calls the printArea() method, the original method in *Shape* class is called. 



##Polymorphism  

Polymorphism is one of the pillars of OOP.  Polymorphism refers to a programming language's ability to process objects differently depending on their data type or class. More specifically, it is the ability to redefine methods for derived classes.   

- Polymorphism allows to write code that treats instances of a superclass. At runtime these instances became instances of subclasses.  
- Each subclass instance responds differently to calls to superclass.
- Thus, polymorphism allows different objects to respond to the same message differently.
- Polymorphism enables multiple forms of response to the same message. It handles the switching of methods between the base class and derived class based on the method implementation of the two classes.

For example, given a base class shape, polymorphism enables the programmer to define different area methods for any number of derived classes, such as square, rectangles and triangles. No matter what shape an object is, applying the area method to it will return the correct results.

In Objective-C, polymorphism is the fairly standard subtype polymorphism you find in most class based object oriented languages.  It occurs when there is a hierarchy of classes and they are related by *inheritance*.

```
int main(int argc, const char * argv[])
{
    NSAutoreleasePool * pool = [[NSAutoreleasePool alloc] init];
    NSLog(@"Author: Yun Zhou");
    
    Shape *square = [[Square alloc]initWithSide:10.0];
    [square calculateArea];
    [square printArea];
    
    Shape *rect = [[Rectangle alloc]
    initWithLength:10.0 andBreadth:5.0];
    [rect calculateArea];
    [rect printArea];    
        
    [pool drain];
    return 0;
}
```

In this example, when printArea is invoked, it could be the base implementation or it could be an override defined in the *Square* subclass — the distinction has no impact on how we invoke the method nor does it impact on the type of the variable sqaure. The only determining factor is whether and how the *Square* class overrides this method from the base class.
