.. index:: inheritance, class; child, class; sub, class; super, class; parent

Inheritance
-----------

Often we build a class but then we need new class that is slightly different. It may need additional 
features or the existing behavior may need to be modified. Instead of building this new class from scratch, 
we can define it based on an existing similar class. 

.. important::
   The third principle of object-oriented programming is that we build new classes from existing classes. 
   **Inheritance** enables us to define a child (or sub or derived) class based on a parent (or super) 
   class. The child class inherits the features, both attributes and methods, of the parent class. The 
   programmer can then add or modify attributes or methods of the child class.

.. index:: inheritance; specialization

Specialization
~~~~~~~~~~~~~~

Suppose our bank introduces a new line of credit (LOC) type account. An overdraft (negative balance) is 
permitted up to a specified limit. The maximum overdraft amount (line of credit) is established when the 
account is opened.

We start by defining ``LOC`` as a child class of ``Account``. The name of the parent class appears in 
parentheses after the name of the new class.

.. activecode:: c2a
    
    class Account:
        def __init__(self, name):
            self.__owner = name
            self.__balance = 0.00

        def getBalance(self):
            return self.__balance

        def deposit(self, amount):
            self.__balance += amount

        def withdraw(self, amount):
            if self.__balance >= amount:
                self.__balance -= amount

    class LOC(Account):
        '''LOC inherits everything from Account'''

    a = LOC('Joe')
    a.deposit(100)
    print(a.getBalance())
    a.withdraw(300)
    print(a.getBalance())


At this point a LOC account operates exactly the same as a regular account.


Next we write the LOC constructor.

.. activecode:: c2b
    
    class Account:
        def __init__(self, name):
            self.__owner = name
            self.__balance = 0.00

        def getBalance(self):
            return self.__balance

        def deposit(self, amount):
            self.__balance += amount

        def withdraw(self, amount):
            if self.__balance >= amount:
                self.__balance -= amount

    class LOC(Account):
        def __init__(self, name, line):
            self.__line = line
            Account.__init__(self, name)  # perform the parent class initialization

    a = LOC('Joe', 500)
    a.deposit(100)
    print(a.getBalance())
    a.withdraw(300)
    print(a.getBalance())

The LOC constructor has a parameter to specify the LOC account's line of credit. This amount is used 
to initialize a new attribute, unique to the LOC account. Next the constructor asks the parent class 
to perform its constructor method. Notice we still cannot withdraw more than we have on deposit.

Now we modify the LOC ``withdraw`` method to also check the object's ``__line`` attribute.


.. activecode:: c2c
    
    class Account:
        def __init__(self, name):
            self.__owner = name
            self.__balance = 0.00

        def getBalance(self):
            return self.__balance

        def deposit(self, amount):
            self.__balance += amount

        def withdraw(self, amount):
            if self.__balance >= amount:
                self.__balance -= amount

    class LOC(Account):
        def __init__(self, name, line):
            self.__line = line
            Account.__init__(self, name)

        def withdraw(self, amount):
            '''allow overdraft up to line of credit'''
            if self._Account__balance + self.__line >= amount:
                self._Account__balance -= amount

    a = LOC('Joe' 500)
    a.deposit(100)
    print(a.getBalance())
    a.withdraw(300)
    print(a.getBalance())
    a.withdraw(400) # trying to withdraw too much
    print(a.getBalance())

.. note::
   ``self._Account__balance`` allows ``LOC`` to access the private ``__balance`` attribute from the 
   parent ``Account`` class.

Both Account and LOC have a ``withdraw`` method, both with exactly the same name. The LOC (child) 
withdraw **overrides** the Account (parent) withdraw. Now we can withdraw more than we have on deposit, 
but not more than the account's line of credit.

.. note::
   This form of inheritance is called **specialization**. We may include additional attributes in the
   child class. The child class may have an alternate way to perform an action that the parent already 
   performs. 




