
#Objective-C Program Structure

In this part, we will present a "Hello World" sample code of Objective C program and give an introduction of the overall structure of Objective C program. 

First of all, let us look at the sample code which will print the "Hello World". 

```
#import <Foundation/Foundation.h>

@interface MyClass:NSObject
- (void)MyMethod;
@end

@implementation MyClass

- (void)MyMethod{
   NSLog(@"Hello, World! \n");
}

@end

int main()
{
   /* This is the "Hello World" sample code */
   MyClass *myClass = [[MyClass alloc]init];
   [myClass MyMethod];
}
```

Then we are going to dive into the details of each part of the code.

1. **Preprocessor command**. The first line of the program *#import <Foundation/Foundation.h>* informs Objective-C compiler to include Foundation.h file before going to actual compilation. 

2. **Interface**. The line *@interface MyClass:NSObject* shows how to create an interface. And the next line *(void)MyMethod*; shows how to declare a method. *@end* marks the end of an interface.

3. **Inplementation**. The line *@implementation MyClass* shows the concrete implementation of interface MyClass. *(void)MyMethod{}* gives the implementation of the MyMethod. And here NSLog(...) is used to print the message "Hello, World!". *@end* marks the end of an implementation.

4. **Main function**. The line *int main()* is the main function where program execution begins. Objective C use /*...*/ to add comments. 


Now when we compile and run the program, we will get the following result.

```
Executing the program....
$demo

2015-12-13 14:24:43.161 demo[21365] Hello, World! 

```



 
