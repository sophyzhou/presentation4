
#Objective-C Inheritance



  [<i class="icon-file"></i>Inheritance Conception](#inheritance-conception)  
  
  [<i class="icon-file"></i>Inheritance Example](#inheritance-example)  
 

##Inheritance Conception
![Alt text](/image/humansgorillas.png) 
Source: https://developer.apple.com/library/mac/documentation/Cocoa/Conceptual/ProgrammingWithObjectiveC/DefiningClasses/DefiningClasses.html#//apple_ref/doc/uid/TP40011210-CH3-SW1

The concept of inheritance brings something of a real-world view to programming. In the world of object-oriented programming, objects are also categorized into hierarchical groups. The class at the top of the hierarchy is known as the **base class** or **root class** and the derived classes as **subclasses** or **child classes**. The class from which a subclass is derived is called the **parent class**. 

In the same way that humans inherit certain characteristics as members of the Hominidae family, the derived class inherits all of the features of the parent class and also adds some features of its own or *override* some methods in the parent class.

Objective-C only support *single inheritance* which means a subclass can only be derived from a single direct parent class. While any number of subclasses may be derived from a class.  

Classes need not only be derived from a root class. A subclass can also inherit from another subclass with the potential to create large and complex class hierarchies.


##Inheritance Example



 
