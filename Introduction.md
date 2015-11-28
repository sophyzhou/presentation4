
#Objective-C Introduction

Objective-C is the primary programming language for Apple’s iOS and OS X operating systems. It is a compiled, general purpose language which can build everything from command line utilities to animated GUIs. It also provides many tools for maintaining large, scalable frameworks.


  [<i class="icon-file"></i>Relation with C and C++](#relation-with-c-and-c)  
  
 [<i class="icon-file"></i>Benefits of Objective-C](#benefits-of-objective-c)  
 
 [<i class="icon-file"></i>Framework](#framework)  
 
 

##Relation with C and C++

Objective-C is a super-set of the C programming language which is implemented as set of extensions to C. Objective-C inherits the syntax, primitive types, and flow control statements of C and adds syntax for defining classes and methods.

Like C++, Objective-C is designed to give C a full capability for object-oriented programming, but the two languages accomplished this using fundamentally distinct philosophies. Objective-C is decidedly more dynamic, deferring most of its decisions to run-time rather than compile-time. This is reflected in many of the design patterns underlying iOS and OS X development.

Comparing with C++, the resulting code of Objective-C is more descriptive so that it is virtually less possible to misunderstand or misuse it. For example, the following sample code shows a C++ method call with its Objective-C equivalent.

```
// C++
sophy->drive("Boulder", "New York")
// Objective-C
[sophy driveCar:@"Boulder" toDestination:@"New York"]
```


##Benefits of Objective-C

Developers use Objective-C for various reasons.   
1.  **First**, it’s an object-oriented language. The kind of functionality that’s packaged in the Cocoa frameworks can only be delivered through object-oriented techniques.   
2. **Second**, because Objective-C incorporates C, you get all the benefits of C when working within Objective-C. You can choose when to apply object-oriented way (define a new class, for example) and when to stick to procedural programming techniques (define a structure and some functions instead of a class).  
3. **Moreover**, Objective-C is a fundamentally simple language. Its syntax is descriptive, unambiguous, so that it is easy to learn for beginners.   
4. **Also**, Objective-C is the most dynamic of the object-oriented languages based on C. The compiler preserves a great deal of information about the objects themselves for use at runtime. Dynamism gives Objective-C programs unusual flexibility and power in mainly two ways: 

- Objective-C supports an open style of dynamic binding, a style that can accommodate a simple architecture for interactive user interfaces. 
- Dynamism enables the construction of sophisticated development tools. 


## Framework

As with most programming languages, Objective-C is a relatively simple syntax backed by an extensive standard library.  Among many different standard libraries,  **Apple’s Cocoa** and **Cocoa Touch** frameworks are by far the most popular, which define the API for building OS X and iOS apps respectively. 


