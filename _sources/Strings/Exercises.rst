..  Copyright (C)  Brad Miller, David Ranum, Jeffrey Elkner, Peter Wentworth, Allen B. Downey, Chris
    Meyers, and Dario Mitchell.  Permission is granted to copy, distribute
    and/or modify this document under the terms of the GNU Free Documentation
    License, Version 1.3 or any later version published by the Free Software
    Foundation; with Invariant Sections being Forward, Prefaces, and
    Contributor List, no Front-Cover Texts, and no Back-Cover Texts.  A copy of
    the license is included in the section entitled "GNU Free Documentation
    License".

.. qnum::
   :prefix: strings-
   :start: 1

Exercises
---------

.. question:: string_1
   :number: 1

   What is the result of each of the following::

      a. 'Python'[1]
      b. "Strings are sequences of characters."[5]
      c. len("wonderful")
      d. 'Mystery'[:4]
      e. 'p' in 'Pineapple'
      f. 'apple' in 'Pineapple'
      g. 'pear' not in 'Pineapple'
      h. 'apple' > 'pineapple'
      i. 'pineapple' < 'Peach'

   .. shortanswer:: ex_8_1



.. question:: string_2

   In Robert McCloskey's book *Make Way for Ducklings*, the names of the ducklings are Jack, 
   Kack, Lack, Mack, Nack, Ouack, Pack, and Quack. This loop tries to output these names in order.

   .. sourcecode:: python

        prefixes = "JKLMNOPQ"
        suffix = "ack"

	for p in prefixes:
	    print(p + suffix)


   Of course, that's not quite right because Ouack and Quack are misspelled.
   Can you fix it?

   .. activecode:: ex_8_2


.. question:: string_3

   Assign to a variable in your program a triple-quoted string that contains
   your favorite paragraph of text - perhaps a poem, a speech, instructions
   to bake a cake, some inspirational verses, etc.

   Write a function that counts the number of alphabetic characters (a through z, or A through Z) in 
   your text and then keeps track of how many are the letter 'e'.  Your function should print an analysis 
   of the text like this::

      Your text contains 243 alphabetic characters, of which 109 (44.8%) are 'e'.

   .. activecode:: ex_8_3

      def count(p):
          # your code here


.. question:: string_4

   Write a function that will return the number of digits in an integer.

   .. activecode:: ex_7_10

      def numDigits(n):
          # your code here

      ====

      from unittest.gui import TestCaseGui

      class myTests(TestCaseGui):

          def testOne(self):
              self.assertEqual(numDigits(2),1,"Tested numDigits on input of 2")
              self.assertEqual(numDigits(55),2,"Tested numDigits on input of 55")
              self.assertEqual(numDigits(1352),4,"Tested numDigits on input of 1352")
              self.assertEqual(numDigits(444),3,"Tested numDigits on input of 444")



      myTests().main()



.. question:: string_5

   Write a function that reverses its string argument.

   .. activecode:: ex_8_5
      :nocodelens:

      def reverse(astring):
          # your code here

      ====

      from unittest.gui import TestCaseGui

      class myTests(TestCaseGui):

        def testOne(self):
            self.assertEqual(reverse("happy"),"yppah","Tested reverse on input of 'happy'")
            self.assertEqual(reverse("Python"),"nohtyP","Tested reverse on input of 'Python'")
            self.assertEqual(reverse(""),"","Tested reverse on input of ''")




      myTests().main()


.. question:: string_6

   Write a function that mirrors its argument. For example, the mirror of 'abc' is 'abccba'.

   .. activecode:: ex_8_6
      :nocodelens:

      def mirror(mystr):
          # your code here

      ====

      from unittest.gui import TestCaseGui

      class myTests(TestCaseGui):

          def testOne(self):
              self.assertEqual(mirror("good"),"gooddoog","Tested mirror on input of 'good'")
              self.assertEqual(mirror("Python"),"PythonnohtyP","Tested mirror on input of 'Python'")
              self.assertEqual(mirror(""),"","Tested mirror on input of ''")
              self.assertEqual(mirror("a"),"aa","Tested mirror on input of 'a'")


      myTests().main()



.. question:: string_41

   Write a function that will return the decimal equivalent of a string that represents a binary integer. 
   **Use the accumulator pattern.**

   .. activecode:: ex_8_41

      def bin2dec(n):
          # your code here


      ====
      from unittest.gui import TestCaseGui
      import random
      class myTests(TestCaseGui):

          def testOne(self):
              a = random.randrange(1,256)
              x = bin(a)[2:]
              self.assertEqual(bin2dec(x),a,"Tested on "+x)
              b = a
              while b == a:
                  b = random.randrange(1,256)
              x = bin(b)[2:]
              self.assertEqual(bin2dec(x),b,"Tested on "+x)
              c = a
              while c == a or c == b:
                  c = random.randrange(1,256)
              x = bin(c)[2:]
              self.assertEqual(bin2dec(x),c,"Tested on "+x)
              d = a
              while d == a or d == b or d == c:
                  d = random.randrange(1,256)
              x = bin(d)[2:]
              self.assertEqual(bin2dec(x),d,"Tested on "+x)

      myTests().main()


.. question:: string_42

   Write a function that will return a string that is the binary equivalent of its positive decimal 
   integer parameter. **Use the string accumulator pattern.**

   .. activecode:: ex_8_42

      def dec2bin(n):
          # your code here


      ====
      from unittest.gui import TestCaseGui
      import random
      class myTests(TestCaseGui):

          def testOne(self):
              a = random.randrange(1,256)
              self.assertEqual(dec2bin(a),bin(a)[2:],"Tested on "+str(a))
              b = a
              while b == a:
                  b = random.randrange(1,256)
              self.assertEqual(dec2bin(b),bin(b)[2:],"Tested on "+str(b))
              c = a
              while c == a or c == b:
                  c = random.randrange(1,256)
              self.assertEqual(dec2bin(c),bin(c)[2:],"Tested on "+str(c))
              d = a
              while d == a or d == b or d == c:
                  d = random.randrange(1,256)
              self.assertEqual(dec2bin(d),bin(d)[2:],"Tested on "+str(d))

      myTests().main()


.. question:: string_7

   Write a function that removes all occurrences of a given letter from a string.

   .. activecode:: ex_8_7
      :nocodelens:

      def remove_letter(theLetter, theString):
          # your code here

      ====


      from unittest.gui import TestCaseGui

      class myTests(TestCaseGui):

        def testOne(self):
            self.assertEqual(remove_letter("a","apple"),"pple","Tested remove_letter on inputs of 'a' and 'apple'")
            self.assertEqual(remove_letter("a","banana"),"bnn","Tested remove_letter on inputs of 'a' and 'banana'")
            self.assertEqual(remove_letter("z","banana"),"banana","Tested remove_letter on inputs of 'z' and 'banana'")



      myTests().main()



.. question:: string_8

   Write a boolean function that recognizes whether or not a string is a palindrome - the same frontwards 
   as backwards. (Hint: use your ``reverse`` function to make this easy!).

   .. activecode:: ex_8_8
      :nocodelens:

      def is_pal(myStr):
          # your code here

      ====

      from unittest.gui import TestCaseGui

      class myTests(TestCaseGui):

      def testOne(self):
          self.assertEqual(is_pal("robert"),False,"Tested is_palindrome on input of 'robert'")
          self.assertEqual(is_pal("bob"),True,"Tested is_palindrome on input of 'bob'")
          self.assertEqual(is_pal("racecar"),True,"Tested is_palindrome on input of 'racecar'")
          self.assertEqual(is_pal("starrats"),True,"Tested is_palindrome on input of 'starrats'")
          self.assertEqual(is_pal(""),True,"Tested is_palindrome on input of ''")




      myTests().main()


.. question:: string_9

   Write a function that counts how many times a substring occurs in a string.

   .. activecode:: ex_8_9
      :nocodelens:

      def count(substr,theStr):
          # your code here


      ====


      from unittest.gui import TestCaseGui

      class myTests(TestCaseGui):

            def testOne(self):
                self.assertEqual(count("is","Mississippi"),2,"Tested count on inputs of 'is' and 'Mississippi'")
                self.assertEqual(count("an","banana"),2,"Tested count on inputs of 'an' and 'banana'")
                self.assertEqual(count("ana","banana"),2,"Tested count on inputs of 'ana' and 'banana'")
                self.assertEqual(count("nana","banana"),1,"Tested count on inputs of 'nana' and 'banana'")
                self.assertEqual(count("nanan","banana"),0,"Tested count on inputs of 'nanan' and 'banana'")
                self.assertEqual(count("aaa","aaaaaa"),4,"Tested count on input of 'aaa' and 'aaaaaa'")




      myTests().main()


.. question:: string_10

   Write a function that removes the first occurrence of a string from another string.

   .. activecode:: ex_8_10
      :nocodelens:

      def remove(substr,theStr):
          # your code here

      ====

      from unittest.gui import TestCaseGui

      class myTests(TestCaseGui):

          def testOne(self):
              self.assertEqual(remove("an","banana"),"bana","Tested remove on inputs of 'an' and 'banana'")
              self.assertEqual(remove("cyc","bicycle"),"bile","Tested remove on inputs of 'cyc' and 'bicycle'")
              self.assertEqual(remove("iss","Mississippi"),"Missippi","Tested remove on inputs of 'iss' and 'Mississippi'")
              self.assertEqual(remove("egg","bicycle"),"bicycle","Tested remove on inputs of 'egg' and 'bicycle'")


      myTests().main()



.. question:: string_11

   Write a function that changes all punctuation characters in a string to the space character. 
   Note an appostrophe between letters isn't punctuation - it's part of contraction or possessive.

   .. activecode:: ex_8_11

      def remove_punct(theStr):
          # your code here



      ====

      from unittest.gui import TestCaseGui

      class myTests(TestCaseGui):

        def testOne(self):
            s = "Cough, cough, cough. Cough, cough, cough."
            self.assertEqual(remove_punct(s),"Cough  cough  cough  Cough  cough  cough ","Tested on "+s)
            s = "You're sick? That's why he's here."
            self.assertEqual(remove_punct(s),"You're sick  That's why he's here ","Tested on "+s)
            s = "Doesn't sound too bad. I'll try to stay awake. {Turns off TV.}"
            self.assertEqual(remove_punct(s),"Doesn't sound too bad  I'll try to stay awake   Turns off TV  ","Tested on "+s)
            s = '!"#$%&()*+,-./:;<=>?@[\]^_`{|}~'
            self.assertEqual(remove_punct(s),"                               ","Tested on "+s)



      myTests().main()


.. question:: string_12


   Here is another interesting L-System called a Hilbert curve.  Use 90 degrees::

       X
       X -> RYFLXFXLFYR
       Y -> LXFRYFYRFXL

   .. activecode:: ex_8_12
      :nocodelens:

.. question:: string_13

   Here is a dragon curve.  Use 90 degrees::

       FX
       X -> XRYFR
       Y -> LFXLY

   .. activecode:: ex_8_13
      :nocodelens:

.. question:: string_14

   Here is something called an arrowhead curve.  Use 60 degrees::

       YF
       X -> YFRXFRY
       Y -> XFLYFLX

   .. activecode:: ex_8_14
      :nocodelens:

.. question:: string_15

   Try the Peano-Gosper curve.  Use 60 degrees::

       FX
       X -> XRYFRRYFLFXLLFXFXLYFR
       Y -> LFXRYFYFRRYFRFXLLFXLY

   .. activecode:: ex_8_15
      :nocodelens:

.. question:: string_16

   The Sierpinski Triangle.  Use 60 degrees::

       FXFLLFFLLFF
       F -> FF
       X -> LLFXFRRFXFRRFXFLL

   .. activecode:: ex_8_16
      :nocodelens:


.. question:: string_17

   Write a function that implements a substitution cipher.  In a substitution
   cipher one letter is substituted for another to garble the message.  For
   example A -> Q, B -> T, C -> G etc.  your function should take two
   parameters, the message you want to encrypt, and a string that represents
   the mapping of the 26 letters in the alphabet.  Your function should
   return a string that is the encrypted version of the message.

   .. activecode:: ex_8_17

.. question:: string_18

   Write a function that decrypts the message from the previous exercise.  It
   should also take two parameters.  The encrypted message,
   and the mixed up alphabet.  The function should return a string that is
   the same as the original unencrypted message.

   .. activecode:: ex_8_18

      def encrypt(message, cipher):

      def decrypt(encrypted, cipher):



.. question:: string_19

   Write a function called  ``remove_dups`` that takes a string and creates a new string by only adding 
   those characters that are not already present.  In other words, there will never be a duplicate 
   letter added to the new string.

   .. activecode:: ex_8_19

      def remove_dups(astring):
          # your code here


      print(remove_dups("mississippi"))   #should print misp

      ====
      from unittest.gui import TestCaseGui

      class myTests(TestCaseGui):

        def testOne(self):
            self.assertEqual(remove_dups("pooh"),"poh","Tested remove_dups on string 'pooh'")
            self.assertEqual(remove_dups("mississippi"),"misp","Tested remove_dups on string 'mississippi'")
            self.assertEqual(remove_dups("potato"),"pota","Tested remove_dups on string 'potato'")
            self.assertEqual(remove_dups("bookkeeper"),"bokepr","Tested remove_dups on string 'bookkeeper'")
            self.assertEqual(remove_dups("oo"),"o","Tested remove_dups on string 'oo'")

      myTests().main()


.. question:: string_20

   Write a function called ``rot13`` that uses the Caesar cipher to encrypt a message.
   The Caesar cipher works like a substitution cipher but each character is replaced
   by the character 13 characters to 'its right' in the alphabet.  So for example
   the letter a becomes the letter n.  If a letter is past the middle of the alphabet
   then the counting wraps around to the letter a again, so n becomes a, o becomes b
   and so on.  *Hint:* Whenever you talk about things wrapping around, it's a good idea
   to think of modulo arithmetic.

   .. activecode:: ex_8_20

      def rot13(mess):
          # Your code here

      print(rot13('abcde'))
      print(rot13('nopqr'))
      print(rot13(rot13('Since rot13 is symmetric you should see this message')))

