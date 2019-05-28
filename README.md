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

# Different stages of Object Oriented Software Development
## 1. Define Requirements

At the end of requirements analysis phase, you would have a
documentation describing the functional and non-functional requirements
of the application. 

**Functional requirements** describe what the **application "must" do**. It captures the **Features** / **Capabilities** of the application. **Non-Functional requirements** are not capabilities or features, but they are some rules or notions which are supposed to be followed such as performance, security etc.


## 2. Object Oriented Analysis

So far we have documented the requirements in terms of what the **application "must" do**. Now, its time to
figure out **how a user would interact with our application**. There are two common
procedures used in OOA phase - **use cases** & **user stories**.

### Use Case

For writing a use case, there are very well established templates. You just need to fill in the templates. But, it could be
an overkill sometimes as such a formal format covers a hell lot of
details. So typically a Use Case needs bare minimum of 3 essential
points - a **Title, Actor, Scenario**.

#### Structure of a Use Case

1. Title

Title of a use case must be a **short phrase & active verb**

_For eg:_
- **Register** new member
- **Transfer** funds
- **Purchase** items
- **Create** new page
- **Collect** late payments
- **Process** accounts

2. Actor

Actors are external entities that use our application to achieve certain
goals. It is important to remember that actors are external to the
application. It could be :

-   a specific role of a user such as administrator, member, guest
-   designation such as executive role, data entry staff
-   functions such as customer, customer care staff
-   abstract roles like requestor/approver
-   external systems such as data sources, web services, other apps,
    backup systems, some machines and so on.

To reduce complexity of use cases you can replace a complex scenario
with an actor.

A primary actor is one who
requests/initiates action, and all others are <span
class="underline">secondary actors.

#### Scenario

-   A **scenario is an actor's
    goal*** that is achieved from our application in a single
    encounter. 
-   Sometimes, a use case would include multiple scenarios like the
    *Purchase items* scenario below. 
-   To get a hint on what can be considered a scenario, take for example
    the title "log into application". This can't be a meaningful
    scenario because, the goal of user is not specified here. Why do you
    log into the application is not clear. Hence, this is just a part of
    the scenario, but not a scenario in itself.

<img src="attachments/924476033/934135393.png" width="193"/><br/>

Examples of scenario:

**<img src="attachments/924476033/924483210.png" width="187"/><br/>**

**<img src="attachments/924476033/924483212.png" width="250"/><br/>**

**<img src="attachments/924476033/924483238.png" width="250"/><br/>  
**

### Diagramming use cases

-   A use case diagram fits several use cases in a single diagram,
    because with use case diagramming we are trying to visualize all the
    use cases together to see system functions altogether.
-   Use case diagrams are only just a support for the written
    descriptions. It is no way a replacement for use case description.
-   In the diagram below :
    -   The central box indicates the application. Anything outside the
        box is external to the application
    -   Use cases of the application is written inside ellipses.
    -   Primary actors are usually depicted towards the left of the
        application.
    -   Actors are represented using stick figures. But, if the actor is
        not human, you could put them in a box with *angle quotes* to
        denote it as an actor. for eg: *Analytics System* in the diagram

<img src="attachments/924476033/934135539.png" width="250"/><br/>

## User Story

A *user story* is similar to *use case *but written in a very simply
sentence. Like use case there is a particular format for user story.
User stories are most convenient in agile or extreme programming, where
one or more user stories needs to be finished within a sprint.

Template :

<img src="attachments/924476033/932798694.png" width="160"/><br/>

  

Examples :

<img src="attachments/924476033/932798701.png" width="104"/><br/>

<img src="attachments/924476033/932798702.png" width="103"/><br/>

<img src="attachments/924476033/932798709.png" width="104"/><br/>

<img src="attachments/924476033/932798711.png" width="117"/><br/>

  

Compare use case vs user story :

<img src="attachments/924476033/932798749.png" width="201"/><br/>

## Conceptual Modeling

Conceptual modeling is object oriented construction of a model of the
software. It involves the following steps:

1.  Collect together all the **user
    stories** and **use
    cases** defined so far, and scan the written descriptions to
    identify **nouns** and make a list of nouns.
2.  Nouns are potential objects. **Filter the list** of nouns by
    eliminating duplicates and irrelevant ones.
3.  **Box** the nouns.
4.  **Connect** related boxes. **Tag** the relationship. Specify the
    **multiplicity** if needed.
5.  **Identify responsibilities** of different objects by **marking
    verbs** from the **user stories** and
    **use cases**. This helps to
    distribute responsibilities between different objects rather than
    accumulating a lot of responsibilities unnecessarily towards *actor*
    objects like *customer*.
    -   Sometimes people make mistake by identifying responsibilities as
        to be in *Actor* side. To handle such situations ask the
        question yourself *"In which object should a responsibility
        behavior live in ?"*
        1.  Eg 1: the behavior "check order status" sounds like a
            responsibility of *Customer*. But, this is supposed to be
            implemented in the *Order* object simply because this
            behavior is better to live in *Order* object.
        2.  Eg 2: the behavior "verify items in cart" again sounds like
            responsibility of Customer. But, it is better to be
            implemented in the *Order* object as "Display totals" as it
            serves the goal.

  

<img src="attachments/924476033/932801977.png" width="150"/><br/>

<img src="attachments/924476033/932801979.png" width="150"/><br/>

<img src="attachments/924476033/932801980.png" width="150"/><br/>

<img src="attachments/924476033/932801981.png" width="251"/><br/>

<img src="attachments/924476033/932801982.png" width="251"/><br/>

<img src="attachments/924476033/932801983.png" width="250"/><br/>

<img src="attachments/924476033/932801984.png" width="250"/><br/>

<img src="attachments/924476033/932801986.png" width="250"/><br/>

## CRC Cards

CRC (Class - Responsibility - Collaborators) is an alternate way for
modeling objects.

Each card indicates an object, with class name on top, responsibilities
marked on left and collaborator objects in the right.

        Format of a CRC card looks like :

<img src="attachments/924476033/936301528.png" width="380"/><br/>

Each CRC card represents a class like the following :

<img src="attachments/924476033/936301456.png" width="1028"/><br/>

Once all the CRC cards are laid out. It helps you to see which classes
relates each other and organize CRC cards accordingly.

<img src="attachments/924476033/936301460.png" width="1067"/><br/>

# Object Oriented Design

## Class Diagrams

After having created the conceptual model
or the CRC cards, you can start
diagramming classes. The class diagram doesn't need to depict every
possible *attributes* and *behaviors. *Instead, you need to show only
the relevant details. It represents ***Visibility** (- private* and *+
public), **Data type** (of attributes, behavior parameters, behavior
return data), **Static** (*underlined *attributes* and *behaviors),*
**Constructor** *.*

*<img src="attachments/924476033/932803673.jpg" width="411"/><br/>*

**<img src="attachments/924476033/932803674.jpg" width="288"/><br/>**

### Inheritance

Inheritance is easily identifiable by the **IS A** relationship. Once you have
charted the conceptual model, it would
speak for itself there appears "IS A" relationship between certain
classes. They fall under the inheritance relationship. The inheritance
relationship can be called by different terms : 

parent class → child class

base class   → derived class

super class  → sub class

abstract class → concrete class

  

-   The natural language has the best representation of "IS A"
    relationship as seen below.

  

 <img src="attachments/924476033/932803909.png" width="409"/><br/>

-   Inspect the classes identified during OOA phase to figure out the
    inheritance relationship among them. Here, *Checking Account *is a
    *Bank Account*.

  
<img src="attachments/924476033/932803911.png" width="250"/><br/>  
  

-   *Savings Account *is a *Bank Account*  
    *  
    *

<img src="attachments/924476033/932803912.png" width="250"/><br/>

-   Inheritance is represented using an arrow with wedge.  
      

<img src="attachments/924476033/932803913.png" width="250"/><br/>

-   You can write specific *attributes* and *behaviors *into the
    *sub-classes* or *override* existing ones  
      

<img src="attachments/924476033/932803916.png" width="250"/><br/>

### Abstract Class

There are cases when you don't want to instantiate a class (for eg:
*BankAccount*) simply because there doesn't exist a plain *BankAccount*.
It makes sense to exist only the right form of *BankAccount* such as
*CheckingAccount, SavingsAccount, InvestmentAccount* etc. As in the
above example *BankAccount *can be an abstract
class which cannot be instantiated but hold the attributes and
function definitions - usable only when they gets inherited.

### Interface

Implementing an Interface is like we are signing a contract. It is best
to program application using interfaces more often than inheritance.

For eg: Let's assume you are going to make several classes which are
supposed to be printable (means it should have method `print()` ). Then
you should implement every class with the *Printable* interface, where
*Printable *is the class where we define the `print()` method.

<img src="attachments/924476033/936281755.png" width="150"/><br/>

<img src="attachments/924476033/936281757.png" width="250"/><br/>

<img src="attachments/924476033/936281758.png" width="414"/><br/>

<img src="attachments/924476033/936281759.png" width="352"/><br/>

### Association

Association is a generic term indicating that an object is <span
class="underline">related with another object (aggregation,
composition etc). **Aggregation** &
**Composition** are two types of
associations in OOP. 

Aggregation is similar to Composition as both indicates a "HAS A"
relationship. But, in composition, when the owning object is destroyed
the owned objects also gets destroyed. For eg: A *document *object owns
*page* objects, and when *document* object is destroyed, the *page*
objects also gets destroyed. So, in composition the object lifetime of
owned object is dependent on the owner object.

<img src="attachments/924476033/936281833.png" width="250"/><br/>

<img src="attachments/924476033/936281835.png" width="331"/><br/>

<img src="attachments/924476033/936281837.png" width="250"/><br/>

Open diamond indicates *aggregation*.

Closed diamond indicates *composition*.

## UML Diagrams

There are **14 types** **of UML diagrams.** But, rarely do we need more
than a few like *Use Case Diagram, Class Diagram, Sequence Diagram* and
sometimes *State Machine Diagram*. Like in any other stages of OOA, the
necessity of drawing UML also premises on the need. They are required
only If some of them are essential to understand the application.

<img src="attachments/924476033/936286165.png" width="252"/><br/>

## Design Patterns

When you have clarity on the classes needed for the application, and the
sequence of operations between objects. It is time to refine the current
design of application based on the already well known designs patterns
of software development. There are **23 design patterns** so far**.**

<img src="attachments/924476033/936286205.png" width="250"/><br/>

# Object Oriented Design Principles

## General Design Principles

### DRY

Don't Repeat Yourself.

### YAGNI 

You Ain't Gonna Need It.

Eg: If your software need to create a database abstraction, you don't
need to consider every database providers other than what is currently
in use.

### KISS 

Keep It Simple, Stupid

Eg: When an aircraft is designed, a jet aircraft is to be maintainable
with the common simple tools so that any average mechanic could fix it
during war combat maintenance. Likewise, the software applications must
not be crafted in complex way. 

Eg: If your software needs to import excel document, keep it simple by
importing just a csv so that you don't need to code for processing excel
formatting, graphs, error handling etc.

<img src="attachments/924476033/936286495.png" width="400"/><br/>

## SOLID

<img src="attachments/924476033/936286525.png" width="353"/><br/>

<img src="attachments/924476033/936286527.png" width="396"/><br/>

<img src="attachments/924476033/936286528.png" width="453"/><br/>

<img src="attachments/924476033/936286538.png" width="492"/><br/>

<img src="attachments/924476033/936286530.png" width="358"/><br/>

  

<table>
<tbody>
<tr class="odd">
<td><div class="content-wrapper">
<p><img src="attachments/924476033/936286532.png" width="362" height="250" /></p>
</div></td>
<td><div class="content-wrapper">
<p><img src="attachments/924476033/936286536.png" width="528" height="250" /></p>
</div></td>
<td><div class="content-wrapper">
<p><img src="attachments/924476033/936286537.png" width="517" height="250" /></p>
</div></td>
</tr>
</tbody>
</table>

## GRASP

 <img src="attachments/924476033/936287107.png" width="401"/><br/>

<img src="attachments/924476033/936287110.png" width="384"/><br/>

<img src="attachments/924476033/936287113.png" width="480"/><br/>

<img src="attachments/924476033/936287114.png" width="421"/><br/>

<img src="attachments/924476033/936287108.png" width="425"/><br/>

<img src="attachments/924476033/936287111.png" width="504"/><br/>

  

<img src="attachments/924476033/936287115.png" width="450"/><br/><img src="attachments/924476033/936287178.png" width="458"/><br/>

<img src="attachments/924476033/936287116.png" width="445"/><br/>

<img src="attachments/924476033/936287117.png" width="420"/><br/>

# Further Reference

<img src="attachments/924476033/936287118.png" width="400"/><br/>

\`<img src="attachments/924476033/936287123.png" width="250"/><br/><img src="attachments/924476033/936287124.png" width="250"/><br/><img src="attachments/924476033/936287119.png" width="250"/><br/><img src="attachments/924476033/936287121.png" width="250"/><br/><img src="attachments/924476033/936287125.png" width="250"/><br/>
