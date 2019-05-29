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

### Specifics of a Class Diagram
#### Inheritance

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
|Inspect the classes identified during OOA phase to figure out the inheritance relationship among them. Here, _Checking Account_ **is a** _Bank Account_. <br/> <img src="attachments/924476033/932803911.png" width="400"/>|
|_Savings Account_ **is a** _Bank Account_.  <br/> <img src="attachments/924476033/932803912.png" width="400"/>|
|Inheritance is represented using an arrow with wedge. <br/> <img src="attachments/924476033/932803913.png" width="500"/>|
|You can write specific *attributes* and *behaviors* into the *sub-classes* or *override* existing ones. <br/> <img src="attachments/924476033/932803916.png" width="550"/>|

#### Abstract Class

There are cases when you don't want to instantiate a class (for eg:
*BankAccount*) simply because there doesn't exist a plain *BankAccount*.
It makes sense to exist only the right form of *BankAccount* such as
*CheckingAccount, SavingsAccount, InvestmentAccount* etc. As in the
above example *BankAccount* can be an abstract
class which cannot be instantiated but hold the attributes and
function definitions - usable only when they gets inherited.

#### Interface

Implementing an Interface is like we are signing a contract. It is best
to program application using interfaces more often than inheritance.

For eg: Let's assume you are going to make several classes which are
supposed to be printable (means it should have method `print()` ). Then
you should implement every class with the *Printable* interface, where
*Printable *is the class where we define the `print()` method.

|Illustration of Interface|
|--------------------------|
|<img src="attachments/924476033/936281755.png" width="270"/>|
|<img src="attachments/924476033/936281757.png" width="350"/>|
|<img src="attachments/924476033/936281758.png" width="450"/>|
|<img src="attachments/924476033/936281759.png" width="430"/>|

#### Association

Association is a generic term indicating that an object is related with another object (aggregation,
composition etc). **Aggregation** &
**Composition** are two types of
associations in OOP. 

Aggregation is similar to Composition as both indicates a "HAS A"
relationship. But, in composition, when the owning object is destroyed
the owned objects also gets destroyed. For eg: A *document* object owns
*page* objects, and when *document* object is destroyed, the *page*
objects also gets destroyed. So, in composition the object lifetime of
owned object is dependent on the owner object.

|Aggregation & Association|
|--------------------------|
|<img src="attachments/924476033/936281833.png" width="410"/>|
|<img src="attachments/924476033/936281835.png" width="321"/>|
|<img src="attachments/924476033/936281837.png" width="370"/>|

Open diamond indicates *aggregation*.

Closed diamond indicates *composition*.

## UML Diagrams

There are **14 types of UML diagrams**. But, rarely do we need more
than a few like *Use Case Diagram, Class Diagram, Sequence Diagram* and
sometimes *State Machine Diagram*. Like in any other stages of OOA, the
necessity of drawing UML also premises on the need. They are required
only If some of them are essential to understand the application.

<img src="attachments/924476033/936286165.png" width="322"/><br/>
