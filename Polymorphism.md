
#Objective-C Polymorphism


  [<i class="icon-file"></i>Polymorphism Conception](#polymorphism-conception)  

  [<i class="icon-file"></i>Polymorphism Example](#polymorphism-example)  
    


##Polymorphism  Conception

Polymorphism is one of the pillars of OOP.  Polymorphism refers to a programming language's ability to process objects differently depending on their data type or class. More specifically, it is the ability to redefine methods for derived classes.   

- Polymorphism allows to write code that treats instances of a superclass. At runtime these instances became instances of subclasses.  
- Each subclass instance responds differently to calls to superclass.
- Thus, polymorphism allows different objects to respond to the same message differently.
- Polymorphism enables multiple forms of response to the same message. It handles the switching of methods between the base class and derived class based on the method implementation of the two classes.

For example, given a base class shape, polymorphism enables the programmer to define different area methods for any number of derived classes, such as square, rectangles and triangles. No matter what shape an object is, applying the area method to it will return the correct results.


## Polymorphism Example
In Objective-C, polymorphism is the fairly standard subtype polymorphism you find in most class based object oriented languages.  It occurs when there is a hierarchy of classes and they are related by *inheritance*.

Here we use the example about "Shape" in [Inheritance](Inheritance.md). But we modify the code in main method by using Polymorphism philosophy. 

Instead of initializing the *square* instance like this,  

```
Square *square = [[Square alloc]initWithSide:10.0];
```

We initialize the *square* instance as below,

```
Shape *square = [[Square alloc]initWithSide:10.0];
``` 

And we do the same modification to rectangle instance initialization. And the main method is like below. 

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
