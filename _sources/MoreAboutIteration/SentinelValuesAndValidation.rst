..  Copyright (C)  Brad Miller, David Ranum, Jeffrey Elkner, Peter Wentworth, Allen B. Downey, Chris
    Meyers, and Dario Mitchell.  Permission is granted to copy, distribute
    and/or modify this document under the terms of the GNU Free Documentation
    License, Version 1.3 or any later version published by the Free Software
    Foundation; with Invariant Sections being Forward, Prefaces, and
    Contributor List, no Front-Cover Texts, and no Back-Cover Texts.  A copy of
    the license is included in the section entitled "GNU Free Documentation
    License".

.. qnum::
   :prefix: iter-x-
   :start: 1
   
More Uses of Indefinite Iteration
---------------------------------


Validating Input
~~~~~~~~~~~~~~~~~~~

You can use a ``while`` loop when you want to **validate** input;  when you want to make sure the user has entered valid input for a prompt. Let's say you want a function that asks a yes-or-no question. In this case, you want to make sure that the person using your program enters either a y for yes or n for no. 
Here is a program that uses a ``while`` loop to keep asking until it receives a valid answer. When you run the following code, try typing something other than y or n to see how the code reacts:
    
.. activecode:: ch07_validation

    response = 'x' # initial value ensures loop body will execute
    while not(response == 'y' or response == 'n'):    
        response = input('Do you like brussel sprouts? (y or n): ')


    if response == 'y':
        print('You can have mine.')
    else:
        print('Neither do I.')
        

.. admonition:: Modify the program ...

   In line 2, change ``not(response == 'y' or response == 'n')`` to ``response != 'y' and response != 'n'``. The program will still work the same. 
       
Sentinel Values
~~~~~~~~~~~~~~~

Indefinite loops are much more common in the real world than definite loops.

* If you are selling tickets to an event, you don't know in advance how   many tickets you will sell. You keep selling tickets as long as people come   to the door and there's room in the hall.
* When the baggage crew unloads a plane, they don't know in advance how many   suitcases there are. They just keep unloading while there are bags left in the   cargo hold. (Why *your* suitcase is always the last one is an entirely different problem.)
* When you go through the checkout line at the grocery, the clerks don't know in advance how many items there are. They just keep ringing up items as   long as there are more on the conveyor belt.

Let's implement the last of these in Python, by asking the user for prices and keeping a running total and count of items. When the last item is entered, the program gives the grand total, number of items, and average price. We'll need these variables:
    
* ``total`` - this will start at zero
* ``count`` - the number of items, which also starts at zero
* ``moreItems`` - a boolean that tells us whether more items are waiting; this starts as True

The pseudocode (code written half in English, half in Python) for the body of the loop looks something like this::
    
    while moreItems
        ask for price
        add price to total
        add one to count

This pseudocode has no option to set ``moreItems`` to ``False``, so it would run forever. In a grocery store, there's a little
plastic bar that you put after your last item to separate your groceries from those of the person behind you; that's how the clerk knows you have no more items. We don't have a "little plastic bar" data type in Python, so we'll do the next best thing: we will use a ``price`` of zero to mean "this is my last item." In this program, zero is a **sentinel value**, a value used to signal the end of the loop. Here's the code:
    
.. activecode:: ch07_sentinel

    def checkout():
        total = 0
        count = 0
        moreItems = True
        while moreItems:
            price = float(input('Enter price of item (0 when done): '))
            if price != 0:
                count = count + 1
                total = total + price
                print('Subtotal: $', total)
            else:
                moreItems = False

        print('Total items:', count)
        print('Total $', total)
        average = total / count
        print('Average price per item: $', average)
        
    checkout()

Run the program a couple of times with different values to see that it works. However, there are still a few problems with this program.


.. admonition:: Modify the program ...

   * If you enter a negative number, it will be added to the total and count. Modify the code  so that negative numbers give an error message instead (but don't end the loop) Hint: ``elif`` is your friend.
   * If you enter zero the first time you are asked for a price, the loop will end, and the program  will try to divide by zero. Use an ``if``/``else`` statement before the average calculation to avoid the division by zero and tell the user that you can't compute an average without data.

.. index::
    single: validation
    single: input; validating
    single: sentinel value
    single: value; sentinel
    