
#Objective-C Introduction

Objective-C is the primary programming language for Apple’s iOS and OS X operating systems. It is a compiled, general-purpose and object-oriented language which can build everything from command line utilities to animated GUIs. It also provides many tools for maintaining large, scalable frameworks.


  [<i class="icon-file"></i>Relation with C and C++](#relation-with-c-and-c)  
  
 [<i class="icon-file"></i>Benefits of Objective-C](#benefits-of-objective-c)  
 
 [<i class="icon-file"></i>Framework](#framework)  
 
 

##Relation with C and C++

Objective-C is implemented as set of extensions to C. It inherits the syntax, primitive types, and flow control statements of C and adds syntax for defining classes and methods.

Both Objective C and C++ are designed to give C full object-oriented features for programming, but the two languages accomplished this in fundamentally difference ways. Since Objective C defers most of its decisions to run-time rather than compile-time, it has more dynamic capacities in the langurage itself. 

Another big difference between C++ and Objective C is the syntax. Comparing with C++, the resulting code of Objective-C is more descriptive so that it is virtually less possible to misunderstand or misuse it. For example, the following sample code shows a C++ method call with its Objective-C equivalent.

```
// C++
sophy->drive("Boulder", "New York")
// Objective-C
[sophy driveCar:@"Boulder" toDestination:@"New York"]
```


##Benefits of Objective-C

Developers use Objective-C for various reasons.   
- **Object-oriented Features**. Object-oriented techniques could facilitate us to take advantages of functionality which is packaged in the Cocoa frameworks.   
2. **Benifits inherited from C**. Because Objective-C inherites from C and extend C capacities, you get all the benefits of C when working within Objective-C. You can choose when to apply object-oriented way and when to stick to procedural programming techniques.  
3. **Simplicity**. It is easy to learn for beginners, since its syntax is simple, descriptive, unambiguous.  
4. **Dynamic Capacities**. Objective-C is the most dynamic object-oriented language based on C. The dynamic capacities enable Objective-C programs to have more flexibility.  


## Framework

As with most programming languages, Objective-C is a relatively simple syntax backed by an extensive standard library.  Among many different standard libraries,  **Apple’s Cocoa** and **Cocoa Touch** frameworks are by far the most popular, which define the API for building OS X and iOS apps respectively. 


