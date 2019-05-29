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

### A. Use Case

For writing a use case, there are very well established templates. You just need to fill in the templates. But, it could be
an overkill sometimes as such a formal format covers a hell lot of
details. So typically a Use Case needs bare minimum of 3 essential
points - a **Title, Actor, Scenario**.

#### Structure of a Use Case

##### 1. Title

Title of a use case must be a **short phrase & active verb**

_For eg:_
- **Register** new member
- **Transfer** funds
- **Purchase** items
- **Create** new page
- **Collect** late payments
- **Process** accounts

##### 2. Actor

Actors are external entities that use our application to achieve certain
goals. It is important to remember that actors are external to the
application. It could be :

-   a specific role of a user such as administrator, member, guest
-   designation such as executive role, data entry staff
-   functions such as customer, customer care staff
-   abstract roles like requestor/approver
-   external systems such as data sources, web services, other apps,
    backup systems, some machines and so on.

To reduce complexity of use cases you can replace a complex scenario with an actor.

A primary actor is one who requests/initiates action, and all others are secondary actors.

##### 3. Scenario

-   A **scenario is an actor's goal** that is achieved from our application in a single
    encounter. 
-   Sometimes, a use case would include multiple scenarios.
-   It has to be written in an active voice.
-   To get a hint on what can be considered a scenario, take for example
    the title "Sign into application". This can't be a meaningful
    scenario because, the goal of user is not specified here. Why do you
    log into the application is not clear. Hence, this is just a part of
    the scenario, but not a scenario in itself.
    
Example for a use case:

```
Title: Purchase items
Actor: Customer
Scenario: 
1. Customer chooses to enter the checkout process
2. Customer is shown confirmation page for their order, allowing to change quantities
3. Customer inputs shipping address
4. Customer selects payment method
5. System validates payment details
6. System creates order number that can be used for tracking
7. System displays confirmation message
8. System sents an email confirmation to the customer
```

#### Diagramming use cases

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

<img src="attachments/924476033/934135539.png" width="550"/><br/>

### B. User Story

A *user story* is similar to *use case* but written in a very simple
sentence. Like use case there is a particular format for user story.
User stories are most convenient in agile or extreme programming, where
one or more user stories needs to be finished within a sprint.

Template :

```
As a {type of user}
I want {goal}
so that {reason}
```

Examples :

```
As a Reader
I want to change the font and color scheme
so that I can read in different lighting conditions
```

```
As a Bank Customer
I want to change my PIN online
so that I don't need to visit bank branch
``` 

## 3. Conceptual Object Modeling

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

|**Illustration of how to make a Conceptual Object Model from _Use Case/User Stories_**|  
|---------------------------------------------------------------------------------------|
|**Step 1. Scan user stories and use cases to identify nouns** <br/><br/> <img src="attachments/924476033/932801977.png" width="500"/>|
|**Step 2. Make a list of nouns** <br/><br/> <img src="attachments/924476033/932801979.png" width="275"/>|
|**Step 3. Filter the list of nouns by eliminating duplicates & irrelevant ones** <br/><br/> <img src="attachments/924476033/932801980.png" width="275"/>|
|**Step 4. Box the nouns** <br/><br/> <img src="attachments/924476033/932801981.png" width="451"/>|
|**Step 5. Connect related boxes** <br/><br/> <img src="attachments/924476033/932801982.png" width="451"/>|
|**Step 6. Scan user stories and use cases to identify verbs** <br/><br/> <img src="attachments/924476033/932801983.png" width="500"/>|
|**Step 7. Make a list of verbs** <br/><br/> <img src="attachments/924476033/932801984.png" width="650"/>|
|**Step 8. Mark verbs against corresponding nouns. Then you have a _Conceptual Object Model_** <br/><br/> <img src="attachments/924476033/932801986.png" width="450"/>|
