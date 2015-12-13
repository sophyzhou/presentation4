
#Objective-C Data Encapsulation

Encapsulation is an important concept in object-oriented programming. We will talk about this topic by the following order. 

  [<i class="icon-file"></i>Data Encapsulation Conception](#data-encapsulation-conception)  
  [<i class="icon-file"></i>Data Encapsulation in Objective-C](#data-encapsulation-in-objective-c)  
  [<i class="icon-file"></i>Example](#example)  
    


##Data Encapsulation  Conception
"**Data encapsulation**, also known as data hiding, is the mechanism whereby the implementation details of a class are kept hidden from the user. The user can only perform a restricted set of operations on the hidden members of the class by executing special functions commonly called methods. ” 
--referenced from Wiki(https://en.wikipedia.org/wiki/Data_encapsulation)
                                                  
Data encapsulation provides a cushion between the developer of a class and the user of a class. It binds together the data and functions that manipulate the data and that keeps both safe from outside interference and misuse. When developers distributes their class, the users do not have to care about the internals of the class at all. Users are only provided with what developers wanted them to have. When developers make some modification of the internal code, users do not need to rewrite their code. 

Encapsulation is important because the structure of the data and how it is formatted may change over time. By encapsulating the data using **class methods**, we can separate how that data is returned from how it is stored internally. This could make sure the data returned is always consistent. 

## Data Encapsulation in Objective-C

**Accessor methods**, also called **getters** and **setters** are methods belonging to a class that allow the programmer to get and set the values of instance variables contained within that class.  

Objective-C could create accessor methods automatically. These are called **synthesized accessor** methods and are implemented through the use of the @property. The synthesized methods follow the naming conventions as below:

- **Setter method**:  starts with the word “set” and then uses the capitalized property name. The setter method for a property called *firstName* will be called *setFirstName:*.
- **Getter method**: has the same name as the property. The getter method for a property called *firstName* will also be called *firstName*.




## Example

The following code demonstrates *Product* class @interface definition file with two instance variables, *productPrice* and *productNumber* declared as properties via the @property directive.

```
#import <Foundation/Foundation.h>
@interface Product: NSObject
@property double productPrice;
@property long productNumber;
-(void) setProduct: (long) y andPrice: (double) x;
-(void) displayProductInfo;
@end
```

In assigning a name to a synthesized accessor **setter method**, Objective-C takes the name of the instance variable (for example *productPrice*), capitalizes the first letter (*ProductPrice*) and then pre-fixes it with set (*setProductPrice*). For example:

```
Product *product1;
product1 = [[Product alloc] init];

[product1 setProductPrice: 765.87];
[product1 setProductNumber: 1234567];
```

In the case of the **getter method**, this simply adopts the name of the property. For example, the getter method name for the *productNumber* property is also *productNumber*:

```
long myProduct = [product1 productNumber];
```
