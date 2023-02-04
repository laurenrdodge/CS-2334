# Class Notes Week 1

(for a better view of code fragments look at them in the "Edit file" tab)



**Problem Solving 101**

- Understand the Problem
- Design a Solution
- Consider Alternatives And Refine
- Implement the Solution
- Test the Solution

**char [] vs. String:** One is a primitive data type and the other is a class.


**What is a class?**

Class: a means of creating new types
- Group data elements that describe some abstract concept
- These data elements can be primitive dats or other objects
- Provide methods that operate on these data elements

***THIS IS IMPORTANT FOR ORGANIZING YOUR DATA***


**WHAT IS AN OBJECT?**

Object: one instance of a class
- Occupies a block of memory in the ***heap*** that contains the values of the data elemennts (not on the stack)
- Each instance has its own memeory
- The set of values store in this memory block is called the ***state*** of the object
- In code, we refer to object instances using a ***reference*** to the memory block


**MEMORY ALLOCATION**

There are two different memory loaction in the RAM:

**Stack** - where method calls occur; has the primitive data types (ex: int, char); important info is stored here; stores the reference to the heap

**Heap** - where arrays are stored; slow to access; where all class objects are stored

**Don't put everything on the stack.**

<img width="453" alt="Screenshot 2023-01-26 at 3 52 56 PM" src="https://user-images.githubusercontent.com/123114320/214959060-03a0be5d-0f76-4377-b6b5-63ded896464b.png">


**INSTANCE METHODS**

Some specific types of instance methods:

- **Accessors:** Methods used to report the state of objects
- **Mutators:** Methods used to change the state of objects

*Syntax: reference.method(parameters)*

***"." is a member access operator***


**INSTANCE METHODS: SPECIAL CASES**

Some specific types of instance methids
- **Getters:** Accessor methods used to report the low-level state of objects
- **Setters** Mutator methods used to change the low-level state of objects

Mutator Methods:

- If there are no methods that change the state of an object. These are called **immutable classes** (e.g. String, Integer, Float classes)
- There may be many methods that change the object's state (e.g. StringBuffer class). We call these classes ***mutable***.


**A CLASS IS A CONTRACT**

The set of instance methods define the legal ways that an object may be accessed/changed
- All operations on an object: must **always** leave the object in a consistent state
  - Enforce through variable visibility and through proper method definition

- Best practice:
  - On entry to a method: assume that the object is in a consistent state
  - On exit, ensure that ut is still consistent

Examples:

**What would an inconsistent state be for a triangle object?**

Properties: Height, Base, Width, Area


**A CLASS AS AN "ENCAPSULATOR"**

- A class hides many details from the outside world
- The user of a class only has to worry about the class' public interface
  -Easier to understand how to use the class
  - The implementation of the underlying class can change without the user knowing


**UNIFIED MODELING LANGUAGE (UML)**

UML is a spatial representation that describes:

- The definition of a class
- How the different classes relate to one-another


**UML CLASS DIAGRAMS**

Name of class at top
- Middle section contains data
  - Name: type
- Bottom section contains methods
  - Name(param1: type, param2: type...): return type
- Plus (+) means public
- Minus (-) means private


**PUBLIC VS. PRIVATE DATA**

We should always use private data, don't use public data because it can be changed. You cannot guarantee it won't be altered.

**Public Pros:**

-Easy accesss to all data by otheer classes
- Don't have to implement getters ans setters


**Public Cons:** 

- Can’t protect the data from other classes – easy 
to get into an inconsistent state
- Therefore, the class cannot make any guarantees about how it behaves

For this class:

- We want our classes to protect themselves
- All instance variables will be declared as private or protected (more on the latter soon)
- All external access to instance variables will be through public methods


**INSTANCES VS. CLASS DATA**

- Each object gets its own copy of ***instance data***
- All objects in a class share one copy of ***class data***
  - In UML, class variables are underlined
  - In the class definition, class variables are declared as ***static***
  
  **Examples:**
  
 1. Suppose we were going to design a post-it note application
 
- What is the state of the Note?
- How might the state be changed?

2. How are we going to store things like the number of characters that are allowed in a note?
- Why is instance data not appropriate for this?


**CLASS VARIBALES**

Only one copy of the variables for all instances in the class

- Declare as static:

*private static final int maxCharacters = 100;*

*private static int numNotes = 0;*


**CLASS METHODS**

- Many class methods have no access to instance data
  - There is no object, so there is no instance data
  - Example: examine toString() in Integer class for both instance and class methods


**METHOD OVERLOADING**

**Overloading:** using the same method name, but different parameters

- Common when we want to assume default parameters
- (or) When different types convey similar types of information

*public void addValue(int val);*

*public void addValue(double val);*

**"this"**

- The “**this**” keyword is a reference that refers 
to the object on which an instance method 
was called on

***GOOD FOR PRACTICE BUT CAN COMPLICATE THINGS***


**"this" REFERRING TO THE CALLED OBJECT**

*class Person{*

  *private String name;*
  
  *private int age;*
  
  *public Person(String name, int age){*
  
    *this.name = name;*
    
    *this.age = age;*
    
  *}*
  
*}*

**"this" AS A CONSTRUCTOR**

*class Person{*

  *private String name;*
  
  *private int age;*
  
  *public Person(String name, int age){*
  
    *this.name = name;*
    
    *this.age = age;*
    
  *}*
  
  *public Person(String name){*
  
    *this(name, 20);*
    
  *}*
  
  *public Person(){*
  
    *this(“Bob”, 42);*
    
  *}*
  
*}*


**CLASSES WITHIN CLASSES**

- One of the “big wins” with object-oriented programming is that we can define classes hierarchically
- Now that we have a “Player”, we can create new classes that contain Player

*class Course {*

  *private int courseNumber;*
  
  *private Person instructor;*
  
  *private ArrayList<Person> teachingAssistants;*
  
  *private ArrayList<Person> students;*
  
  *:*
  
  *:*
  
*}*


