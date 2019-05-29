# Object Oriented Design

## Class Diagrams

After having created the **Conceptual Object Model**, you can start
diagramming classes. The class diagram doesn't need to depict every
possible *attributes* and *behaviors*. Instead, you need to show only
the relevant details. It represents :

- **Visibility** (_- private and + public_)
- **Data type** (_of attributes, behavior parameters, behavior return data_)
- **Static** (_attributes and behaviors_)
- **Constructor**

|**Class Diagram with Visibility**  <br/><br/> <img src="attachments/924476033/932803673.png" width="251"/>|
|-----------------------------|
|**Class Diagram with Static Members** <br/><br/>  <img src="attachments/924476033/932803674.png" width="169"/>|


## Inheritance

Inheritance is easily identifiable through **IS A** relationship. Once you have
charted the **Conceptual Object Model**, _"IS A"_ relationship between
classes becomes evident. The inheritance
relationship can be called by different terms : 

- parent class → child class
- base class   → derived class
- super class  → sub class
- abstract class → concrete class

|Illustration of Inheritance through **IS A** relationship|
|----------------------------------------------------------|
|The natural language has the best representation of "IS A" relationship as seen below. <br/> <img src="attachments/924476033/932803909.png" width="409"/>|
|Inspect the classes identified during OOA phase to figure out the inheritance relationship among them. Here, _Checking Account_ **is a** _Bank Account_. <br/> <img src="attachments/924476033/932803911.png" width="550"/>|
|_Savings Account_ **is a** _Bank Account_.  <br/> <img src="attachments/924476033/932803912.png" width="500"/>|
|Inheritance is represented using an arrow with wedge. <br/> <img src="attachments/924476033/932803913.png" width="500"/>|
|You can write specific *attributes* and *behaviors* into the *sub-classes* or *override* existing ones. <br/> <img src="attachments/924476033/932803916.png" width="550"/>|

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
