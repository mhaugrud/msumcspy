Inheritance (cont)
------------------

Now suppose our bank offers Savings accounts. This type of Account accrues (earns) interest based on its balance.

We start by saying that LOC is a child class of Account. Then we add the accrue method to pay interest.

.. activecode:: oop2_7
    
    class Account:
        def __init__(self):
            self.balance = 0.00

        def getBalance(self):
            return self.balance

        def deposit(self, amount):
            self.balance += amount

        def withdraw(self, amount):
            if self.balance >= amount:
                self.balance -= amount

    class Savings(Account):
        ''' Savings inherits everything from Account '''
        __rate = 0.01
        def accrue(self):
            self.deposit(Savings.__rate * self.balance)

    a = Savings()
    a.deposit(100)
    print(a.getBalance())
    a.accrue()
    print(a.getBalance())



.. note::
   This form of inheritance is called **augmentation**. The child class has a new capability that was not available in the parent. 



