..  Copyright (C)  Brad Miller, David Ranum, Jeffrey Elkner, Peter Wentworth, Allen B. Downey, Chris
    Meyers, and Dario Mitchell.  Permission is granted to copy, distribute
    and/or modify this document under the terms of the GNU Free Documentation
    License, Version 1.3 or any later version published by the Free Software
    Foundation; with Invariant Sections being Forward, Prefaces, and
    Contributor List, no Front-Cover Texts, and no Back-Cover Texts.  A copy of
    the license is included in the section entitled "GNU Free Documentation
    License".

Methods with Parameters
-----------------------
          
Let's add the ``deposit`` and ``withdraw`` methods to see better how methods
work.  These methods will need some additional data to do their work: the amount to deposit or withdraw.


.. activecode:: oop1_4
    
    class Account:
        """ Account class for representing and manipulating bank accounts. """
        
        def __init__(self):
            """ Create a new account with zero balance"""
            self.balance = 0.00

        def getBalance(self):
            return self.balance

        def deposit(self, amount):
            self.balance += amount

        def withdraw(self, amount):
            self.balance -= amount

  
    p = Account()
    print(p.getBalance())
    p.deposit(150)
    print(p.getBalance())
    p.withdraw(50)
    print(p.getBalance())


Notice that the caller of ``deposit`` or ``withdraw`` does not explicitly supply an argument to match the ``self`` parameter.  This is true of all method calls. The definition will always
have one additional parameter as compared to the invocation.  

You may ask, "Why did we write two methods instead of just one that could handle either type of transaction?"  One reason is that bankers get rather upset if you withdraw more money from your account than you have on deposit. Run the activecode below. Then edit the withdraw method to check that the balance is sufficient before adjusting the balance.


.. activecode:: oop1_5
    
    class Account:
        """ Account class for representing and manipulating bank accounts. """
        
        def __init__(self):
            """ Create a new account with zero balance"""
            self.balance = 0.00

        def getBalance(self):
            return self.balance

        def deposit(self, amount):
            self.balance += amount

        def withdraw(self, amount):
            self.balance -= amount

  
    p = Account()
    print(p.getBalance())
    p.deposit(150)
    print(p.getBalance())
    p.withdraw(200)
    print(p.getBalance())


What would happen if a clever account holder deposited a negative amount to the account. Run the activecode below to see. Edit the deposit method to check that the amount parameter is not negative before it adjusts the balance.


.. activecode:: oop1_6
    
    class Account:
        """ Account class for representing and manipulating bank accounts. """
        
        def __init__(self):
            """ Create a new account with zero balance"""
            self.balance = 0.00

        def getBalance(self):
            return self.balance

        def deposit(self, amount):
            self.balance += amount

        def withdraw(self, amount):
            if self.balance >= amount:
                self.balance -= amount

    p = Account()
    print(p.getBalance())
    p.deposit(150)
    print(p.getBalance())
    p.withdraw(200)
    print(p.getBalance())
    p.deposit(-200)
    print(p.getBalance())

.. note::
    We could consider a negative balance to be an illegal state for an account. The methods in a well designed class ensure an object will never get into an illegal state.  A class is responsible for maintaining the itegrity of its objects.

