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
        
    class-level attribute
        An attribute that is declared in a class but not in a particular method. It is shared
        by all instances of the class.

    deep copy
        To copy the contents of an object as well as any embedded objects, and
        any objects embedded in them, and so on; implemented by the
        ``deepcopy`` function in the ``copy`` module.
        
    deep equality
        Equality of values, or two references that point to objects that have
        the same value.
            
    inheritance
        A class can be declared as a **child** of a **parent** class. The child inherits all the
        features of the parent. 

    override
        A child class inherits the methods of its parent. However, a method may be redefined in the
        child (with the same name as in the parent) to operate differently.

    polymorphism
        Taking on different forms. A polymorphic method operates differently depending on the class 
        of the object - either as the recipient of the message or as an argument to the method. 
        
    shallow copy
        To copy the contents of an object, including any references to embedded
        objects; implemented by the ``copy`` function in the ``copy`` module.
        
    shallow equality
        Equality of references, or two references that point to the same object.


