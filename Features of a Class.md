# Structure of a class

A class has 3 things :

-   **Name** of the class. *For eg:* BankAccount, File, Document etc.
-   **Attributes**: what identities would represent this class ?. *For eg:* name, color, size, length, FileType etc
-   **Behavior**: what can it do ?. *For eg:* save(), store(), deposit(), withdraw() etc

While modelling an application, if the thing under discussion is a **noun** then it could be an object. _For eg:_ a place, a person, a thing etc. And, a **verb** could be the behavior of an object. _For eg:_ explosion, saving, storing, digestion, run etc

# Fundamental features of a class

There are four fundamental features for a class which is acronymned as **A PIE**
   1. Abstraction
   2. Encapsulation
   3. Inheritance
   4. Polymorphism
   
## 1. Abstraction

During **abstraction** you would identify **what attributes and behaviors** needs to be
inside a class. You should just **focus on the essentials**, ignoring irrelevant details. Thus, abstraction is about **modeling the formation of a class**.

## 2. Encapsulation

Encapsulation is about **information hiding**. It is the **hiding of both attributes and
behaviors** of a class from the reach of external world. Early
days I misunderstood this concept as a way of keeping secret. Actually,
the concept of encapsulation is just to **avoid the external dependencies as
much as possible**, and thereby make a class easy to refactor and evolve.

For example,

Consider a *BankAccount* class, and imagine that you had an attribute *balance*
made as public. It leads to other parts of program referring to the
*balance* attribute directly without invoking *deposit()* or
*withdraw()* behaviors. Thus, other parts of the program can simply directly access the *balance* attribute and
tweak it. Even if you change the logic of *withdrawal* from one way to
other, nobody cares as *balance* is directly accessible to the world. It make the implementation very much tightly
coupled, and you don't have a control over how the balance is updated.

Most important rule of encapsulation is to **hide everything in a class except those which needs
to be explicitly directly accessed by world**

In other words encapsulation is synonymous to the term **black boxing**. In a black box you could only see the
particular input/output sockets placed outside the box. You don't have
any clue on the intrinsic working of this black box.

## 3. Inheritance

Imagine you have abstracted a *Person* class for your program (during analysis, design or coding phase) as below :

```php
class Person {
    name
    age
    address
}
```

Then came a requirement to have a *Customer* class for your program
which would be like :

```php
class Customer {
    name
    age
    address
    customerNumber
}
```

You figured that almost every attributes & behaviors of *Person* class
is duplicated in *Customer* class except for the *customerNumber*
attribute. Hence, you decided to base the *Customer* class upon the
*Person* class, which is called **inheritance**.

```php
class Customer extends Person {
    /*
    These attributes are inherited from Person class
      name
      age
      address
    */
    
    customerNumber
}
```

Thus you have abstracted the **essential commonalities** of a person into *Person* class, and let 
inheritance to do the work for an other similar classes such as _Customer_, _Employee_ etc

The **main advantage of inheritance** is not just that we could reuse codes as much as possible, but it
gives way to **polymorphism**.

## 4. Polymorphism

It is the ability to perform the right behavior for the circumstances. 

For example, take the behavior of mathematical operator `+`. It performs the right behavior on different circumstances such as a string concatenation and mathematical addition.

-   "hello" + "world" = "helloworld"
-   5 + 10 = 15

This is an example for built-in polymorphism in most OOP languages. Similarly, we can make our own polymorphism
into action.
