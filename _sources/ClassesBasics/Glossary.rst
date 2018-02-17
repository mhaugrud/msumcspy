..  Copyright (C)  Brad Miller, David Ranum, Jeffrey Elkner, Peter Wentworth, Allen B. Downey, Chris
    Meyers, and Dario Mitchell.  Permission is granted to copy, distribute
    and/or modify this document under the terms of the GNU Free Documentation
    License, Version 1.3 or any later version published by the Free Software
    Foundation; with Invariant Sections being Forward, Prefaces, and
    Contributor List, no Front-Cover Texts, and no Back-Cover Texts.  A copy of
    the license is included in the section entitled "GNU Free Documentation
    License".

Glossary
--------

.. glossary::


    accessor
        A method that returns information about the state of an object.

    attribute
        One of the named data items that makes up an instance. The name of a **private** attribute 
        begins with two underscores (dunder).

    class
        A user-defined compound type. A class can also be thought of as a
        template for the objects that are instances of it.
        
    constructor
        Every class has a "factory" for making new class instances.  The default constructor 
        ``__init__`` is called by the same name as the class. It may include parameters
        specifying how to properly set up the state of the new object. Any other method that
        returns a new instance of the class is also considered a constructor.

    information hiding
        Private attributes cannot be directly accessed outside of the class definition. They 
        can only be manipulated through the class methods.
            
    initializer method
        A special method in Python (called ``__init__``) 
        that is invoked automatically to set a newly-created object's
        attributes to their initial (factory-default) state.
        
    instance
        An object whose type is of some class.  Instance and object are used
        interchangeably.
        
    instantiate
        To create an instance of a class, and to run its initializer. 
        
    method
        A function that is defined inside a class definition and is invoked on
        instances of that class. 

    mutator
        A method that changes the state of an object. It alters one or more
        attributes of an existing object. A well designed mutator ensures the
        attributes never get set to illegal values.

    object
        A compound data type that is often used to model a thing or concept in
        the real world.  It bundles together the data and the operations that 
        are relevant for that kind of data.  Instance and object are used
        interchangeably.

    object-oriented language
        A language that provides features, such as user-defined classes and
        inheritance, that facilitate object-oriented programming.

    object-oriented programming
        A powerful style of programming in which data and the operations 
        that manipulate it are organized into classes and methods.        



