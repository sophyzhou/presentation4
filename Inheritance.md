
#Objective-C Inheritance



  [<i class="icon-file"></i>Inheritance Conception](#inheritance-conception)  
  
  [<i class="icon-file"></i>Inheritance Example](#inheritance-example)  
 

##Inheritance Conception

In the natural world, taxonomy defines groups of biological organisms on the basis of shared characteristics and giving names to those groups like species, genus, and family. These groups are hierarchical, such that groups of a given rank can be aggregated to form a super group of higher rank: multiple species may belong to one genus, and multiple genera to one family. 

As shown in the figure below, although Humans and Gorillas are differenct species, they share a lot of common similarities and they are taxonomically related since they all belong to the same Hominidae family.


![Alt text](/image/humansgorillas.png) 
Source: https://developer.apple.com/library/mac/documentation/Cocoa/Conceptual/ProgrammingWithObjectiveC/DefiningClasses/DefiningClasses.html#//apple_ref/doc/uid/TP40011210-CH3-SW1

The concept of *inheritance* brings something from a natural world perspective to programming world. In the world of object-oriented programming, objects are also categorized into hierarchical groups. The class at the top of the hierarchy is known as the **base class** or **root class** and the derived classes as **subclasses** or **child classes**. The class from which a subclass is derived is called the **parent class**. 

In the same way that humans and Gorillas inherit certain characteristics as members of the Hominidae family, the derived class inherits all of the features of the parent class and also adds some features of its own or *override* some methods in the parent class.

Objective-C only support *single inheritance* which means a subclass can only be derived from a single direct parent class. While any number of subclasses may be derived from a class.  

Classes need not only be derived from a root class. A subclass can also inherit from another subclass.


##Inheritance Example



 
