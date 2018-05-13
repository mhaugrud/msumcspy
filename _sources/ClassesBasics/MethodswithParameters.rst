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
          
We could write another method to change the current balance. If so, we would need to supply a parameter 
indicating what value the balance should become.

.. activecode:: c1d0
    
    class Account:
        '''Account class to model bank accounts'''
        
        def __init__(self, name):
            '''Create a new account for owner name and a zero balance'''
            self.owner = name
            self.balance = 0.00

        def getBalance(self):
            return self.balance

        def setBalance(self, amount):
            self.balance = amount

    p = Account('Jan')
    print(p.getBalance())
    p.setBalance(150)
    print(p.getBalance())


.. warning::
    This would be a bad design choice. The Account class is meant to model a bank account. If we go to the 
    bank, we do not ask the teller to change our balance to some specified amount. Instead, we either make 
    a deposit or withdrawal. These actions indirectly change the balance.


Instead, let's add ``deposit`` and ``withdraw`` methods to better model how accounts actually work.


.. activecode:: c1d
    
    class Account:
        '''Account class to model bank accounts'''
        
        def __init__(self, name):
            '''Create a new account for owner name and a zero balance'''
            self.owner = name
            self.balance = 0.00

        def getBalance(self):
            return self.balance

        def deposit(self, amount):
            self.balance += amount

        def withdraw(self, amount):
            self.balance -= amount

  
    p = Account('Jan')
    print(p.getBalance())
    
    print(p.getBalance())
    
    print(p.getBalance())


.. admonition:: Extend the program ...

   - On line 21, make a deposit to the account
   - On line 23, make a withdrawal from the account
   - Run and notice how the balance changes

Notice that the caller of ``deposit`` or ``withdraw`` does not explicitly supply an argument to match the 
``self`` parameter.  This is true of all method calls. The definition will always
have one additional parameter as compared to the invocation. 

.. index:: method; constructor, method; accessor, method; mutator

.. note::
   Our class methods fall into three categories:

   #. constructor - create a new object of the class
   #. accessor - return some information about the state of an object
   #. mutator - change the state of an object

You may ask, "Why did we write two methods instead of just one that could handle either type of transaction?"  
One reason is that bankers get rather upset if you withdraw more money from your account than you have on deposit. 
Run the activecode below. 


.. activecode:: c1e
    
    class Account:
        '''Account class to model bank accounts'''
        
        def __init__(self, name):
            '''Create a new account for owner name and a zero balance'''
            self.owner = name
            self.balance = 0.00

        def getBalance(self):
            return self.balance

        def deposit(self, amount):
            self.balance += amount

        def withdraw(self, amount):
            self.balance -= amount

  
    p = Account('Jan')
    print(p.getBalance())
    p.deposit(150)
    print(p.getBalance())
    p.withdraw(200)
    print(p.getBalance())


.. important::

   We can consider a negative balance to be an illegal state for an account. The methods in 
   a well designed class ensure an object will never get into an illegal state.  

   **A class is responsible for maintaining the integrity of its objects**.

