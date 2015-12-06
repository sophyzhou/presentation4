
#Objective-C Data Encapsulation

Encapsulation is an important concept in object-oriented programming. By using class methods to access data stored in object properties, we can separate how that data is returned from how it is stored internally.

  [<i class="icon-file"></i>Encapsulation Conception](#encapsulation-conception)  

  [<i class="icon-file"></i>Encapsulation Example](#polymorphism-example)  
    


##Encapsulation  Conception
**Data encapsulation**, also known as **data hiding**, is the mechanism whereby the implementation details of a class are kept hidden from the user. The user can only perform a restricted set of operations on the hidden members of the class by executing special methods.

Data encapsulation provides a cushion between the developer of a class and the user of a class. It binds together the data and functions that manipulate the data and that keeps both safe from outside interference and misuse.

Another benefit of data encapsulation is that when a developer distributes his class, the people using it donʼt have to worry about the internals of the class at all. In simple terms, the user is provided with what the developer wanted them to have, and "protects" everything else. The developer can change anything internal without the user having to rewrite their code. 

This is important because the structure of the data and how it is formatted can and will change over time. By encapsulating the data using class methods, we protect ourselves from change by making sure the data returned is always consistent. If we access the object properties directly, we would need to go through our code and make changes every time the structure or format of the data changes.

## Encapsulate Example
https://developer.apple.com/library/mac/documentation/Cocoa/Conceptual/ProgrammingWithObjectiveC/EncapsulatingData/EncapsulatingData.html