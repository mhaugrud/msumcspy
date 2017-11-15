..  Copyright (C)  Brad Miller, David Ranum, Jeffrey Elkner, Peter Wentworth, Allen B. Downey, Chris
    Meyers, and Dario Mitchell.  Permission is granted to copy, distribute
    and/or modify this document under the terms of the GNU Free Documentation
    License, Version 1.3 or any later version published by the Free Software
    Foundation; with Invariant Sections being Forward, Prefaces, and
    Contributor List, no Front-Cover Texts, and no Back-Cover Texts.  A copy of
    the license is included in the section entitled "GNU Free Documentation
    License".

Exercises
---------

.. question:: dict_ex_1
   :number: 1

           Write a program that allows the user to enter a string.  It then prints a
           table of the letters of the alphabet in alphabetical order which occur in
           the string together with the number of times each letter occurs. Case should
           be ignored. A sample run of the program might look this this::

               Please enter a sentence: ThiS is String with Upper and lower case Letters.
               a  2
               c  1
               d  1
               e  5
               g  1
               h  2
               i  4
               l  2
               n  2
               o  1
               p  2
               r  4
               s  5
               t  5
               u  1
               w  2
               $

           .. activecode:: ex_11_01


.. question:: dict_ex_2

   Give the Python interpreter's response to each of the following from a
   continuous interpreter session:

   a.
      .. sourcecode:: python

          >>> d = {'apples': 15, 'bananas': 35, 'grapes': 12}
          >>> d['banana']

   b.
      .. sourcecode:: python

          >>> d['oranges'] = 20
          >>> len(d)

   c.
      .. sourcecode:: python

          >>> 'grapes' in d

   d.
      .. sourcecode:: python

          >>> d['pears']

   e.
      .. sourcecode:: python

          >>> d.get('pears', 0)

   f.
      .. sourcecode:: python

          >>> fruits = d.keys()
          >>> fruits.sort()
          >>> print(fruits)

   g.
      .. sourcecode:: python

          >>> del d['apples']
          >>> 'apples' in d


   Be sure you understand why you get each result. Then apply what you have learned to fill in the body of the function below, and add code for the indicated tests:

   .. activecode:: q2_dict_answer

       def add_fruit(inventory, fruit, quantity=0):
            pass

       # make these tests work...
       new_inventory = {}
       add_fruit(new_inventory, 'strawberries', 10)
       # test that 'strawberries' is in new_inventory
       # test that new_inventory['strawberries'] is 10
       add_fruit(new_inventory, 'strawberries', 25)
       # test that new_inventory['strawberries'] is now 35

.. question:: dict_ex_3

   The following file called ``princess.txt`` is the script for the opening scene of The Princess Bride.

   .. datafile:: princess.txt

      Grandson: Cough, cough, cough. Cough, cough, cough. {Grandson is on the bed, playing video game.}
      Mother: {Enters.} Hi, honey.
      Grandson: Hi, Mom.
      Mother: {Kisses son and feels his forehead.} You feeling any better?
      Grandson: A little bit.
      Mother: Guess what?
      Grandson: What?
      Mother: Your Grandfather's here. {Opens curtains.}
      Grandson: Mom, can't you tell him I'm sick?
      Mother: You're sick? That's why he's here.
      Grandson: He'll pinch my cheek. I hate that.
      Mother: Maybe he won't.
      Grandfather: {Entering with a flourish.} Heyyyy!! How's the sickie? Heh? {Pinches boy's cheek.  Boy looks at mother accusingly.}
      Mother: I think I'll leave you two pals alone. {Exits.}
      Grandfather: I brought you a special present.
      Grandson: What is it?
      Grandfather: Open it up.
      Grandson: {Opens the package. Disappointed.} A book?
      Grandfather: That's right. When I was your age, television was called books. And this is a special book. It was the book my father used to read to me when I was sick, {takes book} and I used to read it to your father. And today I'm gonna read it to you.
      Grandson: Has it got any sports in it?
      Grandfather: Are you kidding? Fencing, fighting, torture, revenge, giants, monsters, chases, escapes, true love, miracles...
      Grandson: Doesn't sound too bad. I'll try to stay awake. {Turns off TV.}
      Grandfather: Oh, well, thank you very much, very nice of you. Your vote of confidence is overwhelming. All right. {Puts glasses on.} The Princess Bride, by S. Morgenstern. Chapter One. Buttercup was raised on a small farm in the country of Florin.


   Write a program that list all the words (alphabetically) in princess.txt and the
   number of times each occurs.

   .. activecode:: ex_11_02
      :available_files: princess.txt

      f = open('princess.txt', 'r')




.. question:: dict_ex_4

   Write a program that lists all words in princess.txt according to their length. All words that are the same
   length should be in one group. These words should be in alphabetical order. The groups should be in
   numeric order.

   .. activecode:: ex_11_03
      :available_files: princess.txt

.. question:: dict_ex_5

   Here's a table of English to Pirate translations

   ==========  ==============
   English     Pirate
   ==========  ==============
   sir	        matey
   hotel	    fleabag inn
   student	    swabbie
   boy	        matey
   madam	    proud beauty
   professor	foul blaggart
   restaurant	galley
   your	    yer
   excuse	    arr
   students	swabbies
   are	        be
   lawyer	    foul blaggart
   the	        th'
   restroom	head
   my	        me
   hello	    avast
   is	        be
   man	        matey
   ==========  ==============

   Write a program that asks the user for a sentence in English and then translates that
   sentence to Pirate.
               


   .. activecode:: ex_11_04



