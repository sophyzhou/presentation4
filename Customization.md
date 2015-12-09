
#Objective-C Class Customization

Sometimes, you may want to extend an existing class by adding utility behavior that is useful only in certain circumstances.

"In situations like this, it doesn’t always make sense to add the utility behavior to the original class interface. Such behavior may be unlikely needed during majority of times in an application. Moreover, it doesn’t always make sense to subclass the existing class, because you may want such utility behavior available not only to the original class but also any subclasses of that class."

referenced from
https://developer.apple.com/library/mac/documentation/Cocoa/Conceptual/ProgrammingWithObjectiveC/CustomizingExistingClasses/CustomizingExistingClasses.html#//apple_ref/doc/uid/TP40011210-CH6-SW1

Instead, Objective-C provides us two ways to add our own methods to the existing classes by**categories** and **extensions**.  


  [<i class="icon-file"></i>Categories](#categories)  
  
  [<i class="icon-file"></i>Extensions](#extensions.)  
    


##Categories
Using a category is an easier way to add method to an existing class for your own application. Here are some important points about categories one should notice:

- A category can be declared for any class, even if you don't have the original implementation source code.
- A category can be applied to override existing methods in the original class, but this is really a bad behavior. If you override an existing method in the original class, and then you want to modify its behavior again with overriding method in another category, there is no way for Objective-C to know which implementation to be used. 
- At runtime, there's no difference between a method added by a category and one that is implemented by the original class.

The syntax to declare a category uses the **@interface** keyword, and it specifies the name of the category in **parentheses**.  But it does not indicate any inheritance from a subclass. 

```
@interface ClassName (CategoryName)

@end
```

Now, let's look at a sample category implementation. We want to add a category to the Cocoa class NSString. This category will make it possible for us to add a new method *getAuthorNameString* which return the author name string. It is shown below.

```
#import <Foundation/Foundation.h>

@interface NSString(AuthorNameAdditions)

+(NSString *)getAuthorNameString;

@end

@implementation NSString(AuthorNameAdditions)

+(NSString *)getAuthorNameString{
    return @"Author: Yun Zhou";
}

@end


int main(int argc, const char * argv[])
{
    
   NSAutoreleasePool * pool = [[NSAutoreleasePool alloc] init];
   NSString *AuthorNameString = [NSString getAuthorNameString];
   NSLog(@"Accessing Category: %@",AuthorNameString);
   [pool drain];
    return 0;
}
```

Now when we compile and run the program, we will get the following result.

[category.png]

##Extensions

Extensions are a close relative to categories, but it can only be added to a class for which you have the source code at compile time (the class is compiled at the same time as the class extension). Here are some important points about extensions one should notice:

- Unlike category, an extension cannot be declared for any class, only for the classes that have original implementation.
- Any method or variable declared inside the extensions is not accessible even to the inherited classes.

The syntax to declare a extension uses the **@interface** keyword, and it just adds parentheses. But it does not indicate any inheritance from a subclass. 

```
@interface ClassName ()

@end
```

Because no name is given in the parentheses, class extensions are often referred to as *anonymous categories*.

A class extension can add its own properties and instance variables to a class. If you declare a property in a class extension, like this:

```
@interface Author ()
@property NSObject *extraAuthor;
@end
```