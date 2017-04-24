..  Copyright (C)  Brad Miller, David Ranum, Jeffrey Elkner, Peter Wentworth, Allen B. Downey, Chris
    Meyers, and Dario Mitchell.  Permission is granted to copy, distribute
    and/or modify this document under the terms of the GNU Free Documentation
    License, Version 1.3 or any later version published by the Free Software
    Foundation; with Invariant Sections being Forward, Prefaces, and
    Contributor List, no Front-Cover Texts, and no Back-Cover Texts.  A copy of
    the license is included in the section entitled "GNU Free Documentation
    License".

.. qnum::
   :prefix: strings-14-
   :start: 1

The Accumulator Pattern with Strings
------------------------------------


Combining the ``in`` operator with string concatenation using ``+`` and the accumulator pattern, we can
write a function that removes all the vowels from a string.  The idea is to start with a string and iterate over each character, checking to see if the character is a vowel.  As we process the characters, we will build up a new string consisting of only the nonvowel characters.  To do this, we use the accumulator pattern.

Remember that the accumulator pattern allows us to keep a "running total".  With strings, we are not accumulating a numeric total.  Instead we are accumulating characters onto a string.

The general steps of the string accumulator pattern are:

.. sourcecode:: python

    initialize the output string to an empty string

    for each character in another string:
        (if appropriate) concatenate that character to the output string


.. activecode:: ch08_acc1
    
    def removeVowels(s):
        vowels = "aeiouAEIOU"
        sWithoutVowels = ""
        for aChar in s:
            if aChar not in vowels:
                sWithoutVowels = sWithoutVowels + aChar
        return sWithoutVowels 
       
    print(removeVowels("compsci"))
    print(removeVowels("aAbEefIijOopUus"))

Line 5 uses the ``not in`` operator to check whether the current character is not in the string ``vowels``. The alternative to using this operator would be to write a very large ``if`` statement that checks each of the individual vowel characters.  Note we would need to use logical ``and`` to be sure that the character is not any of the vowels.

.. sourcecode:: python

    if aChar != 'a'  and aChar != 'e'  and aChar != 'i'  and
       aChar != 'o'  and aChar != 'u'  and aChar != 'A'  and
       aChar != 'E'  and aChar != 'I'  and aChar != 'O'  and
       aChar != 'U':      
       
         sWithoutVowels = sWithoutVowels + aChar

                  
      

Look carefully at line 6 in the above program (``sWithoutVowels = sWithoutVowels + aChar``).  We will do this for every character that is not a vowel.  This should look
very familiar.  As we were describing earlier, it is an example of the accumulator pattern, this time using a string to "accumulate" the final result.
In words it says that the new value of ``sWithoutVowels`` will be the old value of ``sWithoutVowels`` concatenated with
the value of ``aChar``.  We are building the result string character by character. 

Take a close look also at the initialization of ``sWithoutVowels``.  We start with an empty string and then begin adding
new characters to the end.

Step through the function using codelens to see the accumulator variable grow.

.. codelens:: ch08_acc2
    
    def removeVowels(s):
        vowels = "aeiouAEIOU"
        sWithoutVowels = ""
        for aChar in s:
            if aChar not in vowels:
                sWithoutVowels = sWithoutVowels + aChar
        return sWithoutVowels 
       
    print(removeVowels("compsci"))

**Check your understanding**

.. mchoice:: test_question8_11_1
   :answer_a: BALLBALLBALLBALL
   :answer_b: BALL
   :answer_c: LLAB
   :correct: c
   :feedback_a: item is a single character.
   :feedback_b: The order is wrong.
   :feedback_c: Yes, the order is reversed due to the order of the concatenation.

   What is printed by the following statements:
   
   .. code-block:: python

      s = "BALL"
      r = ""
      for item in s:
          r = item + r
      print(r)


.. note::

   This workspace is provided for your convenience.  You can use this activecode window to try out anything you like.

   .. activecode:: scratch_08_03


