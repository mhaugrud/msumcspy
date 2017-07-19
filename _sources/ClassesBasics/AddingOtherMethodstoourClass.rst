..  Copyright (C)  Brad Miller, David Ranum, Jeffrey Elkner, Peter Wentworth, Allen B. Downey, Chris
    Meyers, and Dario Mitchell.  Permission is granted to copy, distribute
    and/or modify this document under the terms of the GNU Free Documentation
    License, Version 1.3 or any later version published by the Free Software
    Foundation; with Invariant Sections being Forward, Prefaces, and
    Contributor List, no Front-Cover Texts, and no Back-Cover Texts.  A copy of
    the license is included in the section entitled "GNU Free Documentation
    License".

Adding Other Methods to Our Class
---------------------------------
          
The key advantage of using a class like ``Account`` rather than something like a simple variable like ``balance`` now becomes apparent.  We can add methods to
the ``Account`` class that are sensible operations for accounts.  Had we chosen to use a simple
variable to represent the account, we would not have this capability.
Creating a class like ``Account`` brings an exceptional
amount of "organizational power" to our programs, and to our thinking. 
We can group together the sensible operations, and the kinds of data 
they apply to, and each instance of the class can have its own state.       
          
A **method** behaves like a function but it is invoked on a specific
instance.  For example, with a turtle named ``tess``,  ``tess.right(90)`` asks the ``tess`` object to perform its
``right`` method and turn 90 degrees.   Methods are accessed using dot notation.  

Let's add a simple method to allow an account to give us information about its state.  The ``getBalance`` method, when invoked, will return the value of the balance attribute.  The implementation of this method is straight forward since we already know how
to write functions that return values.  One thing to notice is that even though the ``getBalance`` method does not need any other parameter information to do its work, there is still one formal parameter, ``self``.  As we stated earlier, all methods defined in a class that operate on objects of that class will have ``self`` as their first parameter.  Again, this serves as reference to the object itself which in turn gives access to the state data inside the object.

.. activecode:: c1c
    
    class Account:
        '''Account class for representing and manipulating bank accounts'''
        
        def __init__(self):
            '''Create a new account with zero balance'''
            self.balance = 0.00
    
        def getBalance(self):
            return self.balance

    
    p = Account()
    print(p.getBalance())

Note that the ``getBalance`` method simply returns the value of ``self.balance`` from the Account itself.  In other words, the implementation of the method is to go to the state of the object itself and get the value of ``balance``.  This is like asking the bank teller "What is my current balance?"

We could write another method to change the current balance. If so, we would need to supply a parameter for the method to indicate how much the balance should become.

.. sourcecode:: python
    
    class Account:
        '''Account class for representing and manipulating bank accounts'''
        
        def __init__(self):
            '''Create a new account with zero balance'''
            self.balance = 0.00

        def getBalance(self):
            return self.balance

        def setBalance(self, amount):
            self.balance = amount

.. warning::
    This would be a bad design choice. The Account class is meant to model a bank account. If we go to the bank, we do not ask the teller to change our balance to some specified amount. Instead, we either make a deposit or withdrawal. These actions indirectly change the balance.

