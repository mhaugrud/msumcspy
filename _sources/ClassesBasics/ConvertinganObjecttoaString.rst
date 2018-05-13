..  Copyright (C)  Brad Miller, David Ranum, Jeffrey Elkner, Peter Wentworth, Allen B. Downey, Chris
    Meyers, and Dario Mitchell.  Permission is granted to copy, distribute
    and/or modify this document under the terms of the GNU Free Documentation
    License, Version 1.3 or any later version published by the Free Software
    Foundation; with Invariant Sections being Forward, Prefaces, and
    Contributor List, no Front-Cover Texts, and no Back-Cover Texts.  A copy of
    the license is included in the section entitled "GNU Free Documentation
    License".


Creating a String from an Object
--------------------------------

 
When we're working with classes and objects, it is often necessary to print an object (that is to print 
the state of an object).

Consider the example below.

.. activecode:: c1i
    
    class Account:
        '''Account class to model bank accounts'''
        
        def __init__(self, name):
            '''Create a new account for owner name and a zero balance'''
            self.__owner = name
            self.__balance = 0.00

        def getBalance(self):
            return self.__balance

        def deposit(self, amount):
            '''increase balance by a positive amount'''
            if amount >= 0:
                self.__balance += amount

        def withdraw(self, amount):
            '''reduce balance by amount but do not an allow overdraft'''
            if self.__balance >= amount:
                self.__balance -= amount

    p = Account('Jan')
    p.deposit(150)
    print(p)

The ``print`` function shown above produces a string representation of the Account ``p``. 
The default functionality provided by Python tells you that ``p`` is an object of type ``Account``. 
However, it does not tell you anything about the specific state of the Account.

.. index:: override, method; magic

We can improve on this representation if we include a special method called ``__str__``.  Notice that this 
method uses the same naming convention as the constructor, that is two underscores (dunder) before and 
after the name.  Python commonly uses this naming technique for special methods (**magic methods**).

The ``__str__`` method is responsible for creating and returning a string for an object the class. You as 
the programmer, get to choose what an ``Account`` string should look like. In this case, we have 
decided that the string representation will include the owner name as well as the value of the balance 
attribute with some formatting.

When we change the meaning of a pre-defined method, we say that we **override** the method.


.. activecode:: c1j
    
    class Account:
        '''Account class to model bank accounts'''
        
        def __init__(self, name):
            '''Create a new account for owner name and a zero balance'''
            self.__owner = name
            self.__balance = 0.00

        def getBalance(self):
            return self.__balance

        def deposit(self, amount):
            '''increase balance by a positive amount'''
            if amount >= 0:
                self.__balance += amount

        def withdraw(self, amount):
            '''reduce balance by amount but do not an allow overdraft'''
            if self.__balance >= amount:
                self.__balance -= amount

        def __str__(self):
            return "{} ${:,.2f}".format(self.__owner, self.__balance)

    p = Account('Jan')
    p.deposit(150)
    print(str(p))
          

When you run the program above you can see that the ``str`` type constructer function uses the ``__str__``
method that we wrote.

.. admonition:: Extend the program ...

   On line 27, type ``print(p)`` and run the program.
 
   You will see that printing an object by itself also automatically uses the ``__str__`` method.




.. note::
   ``__init__`` and ``__str__`` are known as **magic methods**. We will see more of them in the future.

