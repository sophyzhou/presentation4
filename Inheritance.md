
#Objective-C Inheritance

Inheritance is a very important concept in object-oriented programming. In this chapter we will use an analogy in natural world to illustrate the conception of inheritance. And then we will provide an example of inheritance in Objective C.  

  [<i class="icon-file"></i>Inheritance Conception](#inheritance-conception)  
  
  [<i class="icon-file"></i>Inheritance Example](#inheritance-example)  
 
 
##Inheritance Conception

"In the natural world, taxonomy defines groups of biological organisms on the basis of shared characteristics and giving names to those groups like species, genus, and family. These groups are hierarchical, such that groups of a given rank can be aggregated to form a super group of higher rank: multiple species may belong to one genus, and multiple genera to one family. "  

referenced from: https://en.wikipedia.org/wiki/Taxonomy_%28biology%29

As shown in the figure below, although Humans and Gorillas are differenct species, but they share a certain amount of common similarities and they are taxonomically related - they all belong to the same Hominidae family.


![Alt text](/image/humansgorillas.png)   
Source: https://developer.apple.com/library/mac/documentation/Cocoa/Conceptual/ProgrammingWithObjectiveC/DefiningClasses/DefiningClasses.html#//apple_ref/doc/uid/TP40011210-CH3-SW1

The concept of *inheritance* brings something from a natural world perspective to programming world. In the world of object-oriented programming, objects are also categorized into hierarchical groups. The class at the top of the hierarchy is known as the **base class** or **root class** and the derived classes as **subclasses** or **child classes**. The class from which a subclass is derived is called the **parent class** or **superclass**. 

As humans and Gorillas inherit characteristics of the Hominidae family, the derived class inherits all of the features of the parent class and also adds some features of its own or *override* some methods in the parent class.

Unlike C++, Objective-C only support *single inheritance* which means a subclass can only be derived from a single direct parent class. While any number of subclasses may be derived from a class.  

Classes need not only be derived from a root class. A subclass can also inherit from another subclass.


##Inheritance Example

Here is a simple example of how inheritance works in objective-C.
First of all, we define the **parent class**, *Shape* class. Two methods, *printArea()* and *calculateArea()* are defined.  The *calculateArea()* method is empty which waits to be implemented in the subclasses.  

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

Here we inherit our *Circle* class from the parent class *Shape* . We override the *printArea()* method and we implement the *calculateArea()* method. 

```
@interface Circle : Shape
{
    CGFloat radius;
}

- (id)initWithSide:(CGFloat)side;

- (void)calculateArea;

@end

@implementation Circle

- (id)initWithSide:(CGFloat)side{
    radius = side;
    return self;
}

- (void)calculateArea{
    area = 3.14 * radius * radius;
}

- (void)printArea{
    NSLog(@"The area of circle is %f", area);
}

@end
```

Here we inherit our *Rectangle* class from the parent class *Shape* . We keep the *printArea()* method the same as the one in parent class and we implement the *calculateArea()* method in a different way from that in *Circle* class. 
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
    NSLog(@"Author: Yun Zhou");

    Circle *circle = [[Circle alloc]initWithSide:10.0];
    [Circle calculateArea];
    [Circle printArea];
    
    Rectangle *rect = [[Rectangle alloc]
    initWithLength:10.0 andBreadth:5.0];
    [rect calculateArea];
    [rect printArea];       
     
    [pool drain];
    return 0;
}

```

And we compile and execute the code, the result is like below:

```
Executing the program....
$demo

2015-12-13 14:36:36.127 demo[24443] Author: Yun Zhou
2015-12-13 14:36:36.127 demo[24443] The area of circle is 314.000000
2015-12-13 14:36:36.127 demo[24443] The area is 50.000000

```

we can find that the *printArea()* method in the superclass is overriden by the subclass *Circle*. And the empty *calculateArea()* method in the superclass is implemented by subclass *Circle* and *Rectangle* in differenct ways.  
