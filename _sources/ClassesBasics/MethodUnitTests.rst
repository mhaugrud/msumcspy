..  Copyright (C)  Brad Miller, David Ranum, Jeffrey Elkner, Peter Wentworth, Allen B. Downey, Chris
    Meyers, and Dario Mitchell.  Permission is granted to copy, distribute
    and/or modify this document under the terms of the GNU Free Documentation
    License, Version 1.3 or any later version published by the Free Software
    Foundation; with Invariant Sections being Forward, Prefaces, and
    Contributor List, no Front-Cover Texts, and no Back-Cover Texts.  A copy of
    the license is included in the section entitled "GNU Free Documentation
    License".

.. index:: unit test

Method Unit Testing
-------------------
          
In the Function chapter we learned how it is important to write unit tests for our functions.
It is perhaps even more important to write unit tests for our methods. However, it is somewhat
more involved to write these unit tests. This is because we must first create an object. Then
we use the method we want to test. Finally, we use another method to examine the object. We can
then see if the method we are testing, properly changed the state of the object.



.. activecode:: c1f
    
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

  
    if __name__ == "__main__":
        import test
        print('testing deposit method')
        a = Account('Jan')
        a.deposit(100)
        a.deposit(5)
        test.testEqual(a.getBalance(),105) # the balance after 2 deposits
        a.deposit(-50)                     # what if a negative amount
        test.testEqual(a.getBalance(),105) # the balance should not change
        print('testing withdraw method')
        b = Account('Dan')
        b.deposit(100)
        b.withdraw(80)
        test.testEqual(b.getBalance(),20)  # after deposit and withdraw
        b.withdraw(25)                     # what if withdraw too much?
        test.testEqual(b.getBalance(),20)  # the balance should not change


When you run the example, two tests pass. However, two fail. The first fails because
the ``deposit`` method should not allow a negative ``amount`` parameter. This is an
illegal operation. The second fails because the ``withdraw`` method should not the 
``amount`` parameter to be more than the account's ``balance``. This causes the
account to be in an illegal state.


.. admonition:: Extend the program ...

   Do not change the unit tests

   - Edit the ``deposit`` method in the above activecode to check that ``amount`` is not  
     negative before adjusting ``balance``.

   - Edit the ``withdraw`` method in the above activecode to check that ``amount`` is 
     not too large before adjusting ``balance``.




