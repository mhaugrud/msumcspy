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

#.


            What is the result of each of the following:

            a. 'Python'[1]
            #. "Strings are sequences of characters."[5]
            #. len("wonderful")
            #. 'Mystery'[:4]
            #. 'p' in 'Pineapple'
            #. 'apple' in 'Pineapple'
            #. 'pear' not in 'Pineapple'
            #. 'apple' > 'pineapple'
            #. 'pineapple' < 'Peach'


#. In Robert McCloskey's
   book *Make Way for Ducklings*, the names of the ducklings are Jack, Kack, Lack,
   Mack, Nack, Ouack, Pack, and Quack.  This loop tries to output these names in order.

   .. sourcecode:: python

        prefixes = "JKLMNOPQ"
        suffix = "ack"

	for p in prefixes:
	    print(p + suffix)


   Of course, that's not quite right because Ouack and Quack are misspelled.
   Can you fix it?

    .. activecode:: ex_8_2

#.

           Assign to a variable in your program a triple-quoted string that contains
           your favorite paragraph of text - perhaps a poem, a speech, instructions
           to bake a cake, some inspirational verses, etc.

           Write a function that counts the number of alphabetic characters (a through z, or A through Z) in your text and then keeps track of how many are the letter 'e'.  Your function should print an analysis of the text like this::

               Your text contains 243 alphabetic characters, of which 109 (44.8%) are 'e'.

           .. activecode:: ex_8_3

              def count(p):
                  # your code here


#. Print out a neatly formatted multiplication table, up to 12 x 12.

   .. activecode:: ex_8_4


#.

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



#. Write a function that reverses its string argument.

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

#.

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



#. Write a function that removes all occurrences of a given letter from a string.

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



#.

           Write a function that recognizes palindromes. (Hint: use your ``reverse`` function to make this easy!).

           .. activecode:: ex_8_8
              :nocodelens:

              def is_palindrome(myStr):
                  # your code here

              ====


              from unittest.gui import TestCaseGui

              class myTests(TestCaseGui):

                  def testOne(self):
                      self.assertEqual(is_palindrome("abba"),True,"Tested is_palindrome on input of 'abba'")
                      self.assertEqual(is_palindrome("abab"),False,"Tested is_palindrome on input of 'abab'")
                      self.assertEqual(is_palindrome("straw warts"),True,"Tested is_palindrome on input of 'straw warts'")
                      self.assertEqual(is_palindrome("a"),True,"Tested is_palindrome on input of 'a'")
                      self.assertEqual(is_palindrome(""),True,"Tested is_palindrome on input of ''")




              myTests().main()


#. Write a function that counts how many times a substring occurs in a string.

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


#.

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



#. Write a function that removes all occurrences of a string from another string.

   .. activecode:: ex_8_11

      def remove_all(substr,theStr):
          # your code here



      ====

      from unittest.gui import TestCaseGui

      class myTests(TestCaseGui):

        def testOne(self):
            self.assertEqual(remove_all("an","banana"),"ba","Tested remove_all on inputs of 'an' and 'banana'")
            self.assertEqual(remove_all("cyc","bicycle"),"bile","Tested remove_all on inputs of 'cyc' and 'bicycle'")
            self.assertEqual(remove_all("iss","Mississippi"),"Mippi","Tested remove_all on inputs of 'iss' and 'Mississippi'")
            self.assertEqual(remove_all("eggs","bicycle"),"bicycle","Tested remove_all on inputs of 'eggs' and 'bicycle'")



      myTests().main()


#.

           Here is another interesting L-System called a Hilbert curve.  Use 90 degrees::

               L
               L -> +RF-LFL-FR+
               R -> -LF+RFR+FL-

           .. activecode:: ex_8_12
              :nocodelens:

#. Here is a dragon curve.  Use 90 degrees.::

       FX
       X -> X+YF+
       Y -> -FX-Y

   .. activecode:: ex_8_13
      :nocodelens:

#.

           Here is something called an arrowhead curve.  Use 60 degrees.::

               YF
               X -> YF+XF+Y
               Y -> XF-YF-X

           .. activecode:: ex_8_14
              :nocodelens:

#. Try the Peano-Gosper curve.  Use 60 degrees.::

       FX
       X -> X+YF++YF-FX--FXFX-YF+
       Y -> -FX+YFYF++YF+FX--FX-Y

   .. activecode:: ex_8_15
      :nocodelens:

#.

            The Sierpinski Triangle.  Use 60 degrees.::

               FXF--FF--FF
               F -> FF
               X -> --FXF++FXF++FXF--

           .. activecode:: ex_8_16
              :nocodelens:

#. Write a function that implements a substitution cipher.  In a substitution
   cipher one letter is substituted for another to garble the message.  For
   example A -> Q, B -> T, C -> G etc.  your function should take two
   parameters, the message you want to encrypt, and a string that represents
   the mapping of the 26 letters in the alphabet.  Your function should
   return a string that is the encrypted version of the message.

   .. activecode:: ex_8_17

#.

           Write a function that decrypts the message from the previous exercise.  It
           should also take two parameters.  The encrypted message,
           and the mixed up alphabet.  The function should return a string that is
           the same as the original unencrypted message.

           .. activecode:: ex_8_18

              def encrypt(message, cipher):

              def decrypt(encrypted, cipher):



#. Write a function called  ``remove_dups`` that takes a string and creates a new string by only adding those characters that are not already present.  In other words,
   there will never be a duplicate letter added to the new string.

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


#.

           Write a function called ``rot13`` that uses the Caesar cipher to encrypt a message.
           The Caesar cipher works like a substitution cipher but each character is replaced
           by the character 13 characters to 'its right' in the alphabet.  So for example
           the letter a becomes the letter n.  If a letter is past the middle of the alphabet
           then the counting wraps around to the letter a again, so n becomes a, o becomes b
           and so on.  *Hint:* Whenever you talk about things wrapping around its a good idea
           to think of modulo arithmetic.

           .. activecode:: ex_8_20

              def rot13(mess):
                  # Your code here

              print(rot13('abcde'))
              print(rot13('nopqr'))
              print(rot13(rot13('Since rot13 is symmetric you should see this message')))

