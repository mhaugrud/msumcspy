..  Copyright (C)  Brad Miller, David Ranum, Jeffrey Elkner, Peter Wentworth, Allen B. Downey, Chris
    Meyers, and Dario Mitchell.  Permission is granted to copy, distribute
    and/or modify this document under the terms of the GNU Free Documentation
    License, Version 1.3 or any later version published by the Free Software
    Foundation; with Invariant Sections being Forward, Prefaces, and
    Contributor List, no Front-Cover Texts, and no Back-Cover Texts.  A copy of
    the license is included in the section entitled "GNU Free Documentation
    License".

Adding Other Methods to our Class
---------------------------------
          
The key advantage of using a class like ``Account`` rather than something like a simple variable ``balance`` now becomes apparent.  We can add methods to
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

.. activecode:: chp13_classes4
    
    class Account:
        """ Account class for representing and manipulating bank accounts. """
        
        def __init__(self):
            """ Create a new account with zero balance"""
            self.__balance = 0.00
    
        def getBalance(self):
            return self.__balance

    
    p = Account()
    print(p.getBalance())

Note that the ``getBalance`` method simply returns the value of ``self.__balance`` from the object itself.  In other words, the implementation of the method is to go to the state of the object itself and get the value of ``balance``.  This is like asking the bank teller "What is my current balance?"

It could write another method to change the current balance. We would need to supply a parameter for the method to indicate how much the balance should become.

.. sourcecode:: python
    :linenos:
    
    class Account:
        """ Account class for representing and manipulating bank accounts. """
        
        def __init__(self):
            """ Create a new account with zero balance"""
            self.__balance = 0.00

        def getBalance(self):
            return self.__balance

        def setBalance(self, amount):
            self.__balance += amount

However this would be a bad design choice. The Account class is meant to model a bank account. If we go to the bank, we do not ask the teller to change our balance to some specified amount. Instead, we either make a deposit or withdrawal. These actions indirectly change the balance.

Let's add another method, ``deposit``, to see better how methods
work.  This method will need some additional information to do its work: the amount to deposit.  It will perform a more complex task. In addition to altering the balance, it will also append the deposit amount to the list of transactions.


.. activecode:: chp13_classes5
    
    class Account:
        """ Account class for representing and manipulating bank accounts. """
        
        def __init__(self):
            """ Create a new account with zero balance"""
            self.__balance = 0.00
    

        def getBalance(self):
            return self.__balance

        def deposit(self, amount):
            self.__balance += amount

    
    p = Account()
    print(p.getBalance())
    p.deposit(150)
    print(p.getBalance())


Notice that the caller of ``deposit`` does not explicitly 
supply an argument to match the ``self`` parameter.  This is true of all method calls. The definition will always
have one additional parameter as compared to the invocation.  

The ``withdraw`` method operates in a similar manner. However, we append the amount of the withdrawal as a negative number.


.. activecode:: chp13_classes6
    
    class Account:
        """ Account class for representing and manipulating bank accounts. """
        
        def __init__(self):
            """ Create a new point at the origin """
            self.__balance = 0
            self.__start = 0
            self.__trans = []
    

        def getBalance(self):
            return self.__balance

        def deposit(self, amount):
            self.__balance += amount
            self.__trans.append(amount)

        def withdraw(self, amount):
            self.__balance -= amount
            self.__trans.append(-amount)

  
    p = Account()
    print(p.getBalance())
    p.deposit(150)
    print(p.getBalance())
    p.withdraw(30)
    print(p.getBalance())
    p.withdraw(20)
    print(p.getBalance())



    
