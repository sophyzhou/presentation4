
#Objective-C Polymorphism

Polymorphism is one of the pillars of object-oriented programming. From Understanding and Applying Polymorphism in PHP, by Steve Guidetti: "Polymorphism describes a pattern in object oriented programming in which classes have different functionality while sharing a common interface."  

  [<i class="icon-file"></i>Polymorphism Conception](#polymorphism-conception)  

  [<i class="icon-file"></i>Polymorphism Example](#polymorphism-example)  
    


##Polymorphism  Conception

Polymorphism refers to a programming language's ability to present the same interface for processing objects differently depending on their data type or class. More specifically, it is the ability to redefine methods for derived classes. Polymorphism has some characteristics as below:    

- Polymorphism allows to write code that treats instances of a superclass. At runtime these instances became instances of subclasses.  
- Each subclass instance responds differently to calls to superclass.
- Thus, polymorphism allows different objects to respond to the same message differently.
- Polymorphism enables multiple forms of response to the same message. It handles the switching of methods between the base class and derived class based on the method implementation of the two classes.

For example, given a base class *shape*, polymorphism enables the programmer to define different area methods for any number of derived classes, such as circle, rectangles and triangles. The beauty of polymorphism is that the code working with the different subclasses does not need to know which subclass it is using since they’re all used the same way. In other words, no matter what shape an object is, applying the area method to it will return the correct results. 


## Polymorphism Example

Here we use the same example of "Shape" in [Inheritance](Inheritance.md). But we modify the code in main method by using Polymorphism philosophy. 

Instead of initializing the *circle* instance like this,  

```
Circle *circle = [[Circle alloc]initWithSide:10.0];
```

We initialize the *circle* instance as below,

```
Shape *circle = [[Circle alloc]initWithSide:10.0];
``` 

And we do the same modification to rectangle instance initialization. And the main method is like below. 

```
int main(int argc, const char * argv[])
{
    NSAutoreleasePool * pool = [[NSAutoreleasePool alloc] init];
    NSLog(@"Author: Yun Zhou");
    
    Shape *circle = [[Circle alloc]initWithSide:10.0];
    [circle calculateArea];
    [circle printArea];
    
    Shape *rect = [[Rectangle alloc]
    initWithLength:10.0 andBreadth:5.0];
    [rect calculateArea];
    [rect printArea];    
        
    [pool drain];
    return 0;
}
```

Then we compiled and execute this code, the result is the same with that in [Inheritance](Inheritance.md)

```
Executing the program....
$demo

2015-12-13 14:38:14.777 demo[24892] Author: Yun Zhou
2015-12-13 14:38:14.778 demo[24892] Polymorphism
2015-12-13 14:38:14.778 demo[24892] The area of circle is 314.000000
2015-12-13 14:38:14.778 demo[24892] The area is 50.000000

```

In this example, when *printArea()* is invoked, it could be the base implementation or it could be an override defined in the *Circle* subclass — the distinction has no impact on how we invoke the method nor does it impact on the type of the variable circle. The only determining factor is whether and how the *Circle* class overrides this method from the base class.
