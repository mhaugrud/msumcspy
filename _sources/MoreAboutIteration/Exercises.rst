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


.. question:: moreiter_ex_1
   :number: 1


           Add a print statement to Newton's ``sqrt`` function that
           prints out ``better`` each time it is calculated. Call your modified
           function with 25 as an argument and record the results.

           .. activecode:: ex_7_7

              def newtonSqrt(n):
                  # your code here



.. question:: moreiter_ex_2

   Write a function ``print_triangular_numbers(n)`` that prints out the first
   n triangular numbers. A call to ``print_triangular_numbers(5)`` would
   produce the following output::

       1       1
       2       3
       3       6
       4       10
       5       15

   (*hint: use a web search to find out what a triangular number is.*)

   .. activecode:: ex_7_8

      def print_triangular_numbers(n):
          # your code here


.. question:: moreiter_ex_3

           Write a function, ``is_prime``, that takes a single integer argument
           and returns ``True`` when the argument is a *prime number* and ``False``
           otherwise.

           .. activecode:: ex_7_9

              def is_prime(n):
                  # your code here

              ====
              from unittest.gui import TestCaseGui

              class myTests(TestCaseGui):

                  def testOne(self):
                      self.assertEqual(is_prime(2),True,"Tested on 2, which is a prime number.")
                      self.assertEqual(is_prime(4187),False,"Tested on 4187, which is not a prime number. It is divisible by 53 and 79.")
                      self.assertEqual(is_prime(22),False,"Tested on 22, which is not a prime number. It is divisible by 2 and 11.")
                      self.assertEqual(is_prime(4813),True,"Tested on 4813, which is a prime number.")

              myTests().main()


.. question:: moreiter_ex_4

   Modify the walking turtle program so that rather than a 90 degree left or right turn the
   angle of the turn is determined randomly at each step.

    .. actex:: ex_7_14
       :nocodelens:




.. question:: moreiter_ex_5

           Modify the turtle walk program so that you have two turtles each with a
           random starting location.  Keep the turtles moving until one of them leaves the screen.

           .. activecode:: ex_7_13
              :nocodelens:

              import random
              import turtle

              def moveRandom(wn, t):


              def areColliding(t1, t2):


              def isInScreen(w, t):


              t1 = turtle.Turtle()
              t2 = turtle.Turtle()
              wn = turtle.Screen()

              t1.shape('turtle')
              t2.shape('circle')

              leftBound = -wn.window_width() / 2
              rightBound = wn.window_width() / 2
              topBound = wn.window_height() / 2
              bottomBound = -wn.window_height() / 2

              t1.up()
              t1.goto(random.randrange(leftBound, rightBound),
                      random.randrange(bottomBound, topBound))
              t1.setheading(random.randrange(0, 360))
              t1.down()

              t2.up()
              t2.goto(random.randrange(leftBound, rightBound),
                      random.randrange(bottomBound, topBound))
              t2.setheading(random.randrange(0, 360))
              t2.down()


              while isInScreen(wn, t1) and isInScreen(wn, t2):
                  moveRandom(wn, t1)
                  moveRandom(wn, t2)

              wn.exitonclick()


.. question:: moreiter_ex_6

   Modify the previous turtle walk program so that the turtle turns around
   when it hits the wall or when one turtle collides with another turtle.

   .. activecode:: ex_7_12
      :nocodelens:




.. question:: moreiter_ex_7

           Write a function to remove all the red from an image.

           .. raw:: html

               <img src="../_static/LutherBellPic.jpg" id="luther.jpg">
               <h4 style="text-align: left;">For this and the following exercises, use the
               luther.jpg photo.</h4>

           .. activecode:: ex_7_15
              :nocodelens:


.. question:: moreiter_ex_8

   Write a function to convert the image to grayscale.

   .. activecode:: ex_7_16
      :nocodelens:


.. question:: moreiter_ex_9

           Write a function to convert an image to black and white.

           .. activecode:: ex_7_17
              :nocodelens:

              import image

              def convertBlackWhite(input_image):

              win = image.ImageWin()
              img = image.Image("luther.jpg")

              bw_img = convertBlackWhite(img)
              bw_img.draw(win)

              win.exitonclick()


.. question:: moreiter_ex_10

   Sepia Tone images are those brownish colored images that may remind you of
   times past.  The formula for creating a sepia tone is as follows:

   ::

        newR = (R × 0.393 + G × 0.769 + B × 0.189)
        newG = (R × 0.349 + G × 0.686 + B × 0.168)
        newB = (R × 0.272 + G × 0.534 + B × 0.131)

   Write a function to convert an image to sepia tone. *Hint:*
   Remember that rgb values must be integers between 0 and 255.

   .. activecode:: ex_7_18
      :nocodelens:

.. question:: moreiter_ex_11

           Write a function to uniformly enlarge an image by a factor of 2 (double the size).


           .. activecode:: ex_7_19
              :nocodelens:

              import image

              def double(oldimage):


              win = image.ImageWin()
              img = image.Image("luther.jpg")

              bigimg = double(img)
              bigimg.draw(win)

              win.exitonclick()


.. question:: moreiter_ex_12

   After you have scaled an image too much it looks blocky.  One way of
   reducing the blockiness of the image is to replace each pixel with the
   average values of the pixels around it.  This has the effect of smoothing
   out the changes in color.  Write a function that takes an image as a
   parameter and smooths the image.  Your function should return a new image
   that is the same as the old but smoothed.

   .. activecode:: ex_7_20
      :nocodelens:

.. question:: moreiter_ex_13

           Write a general pixel mapper function that will take an image and a pixel mapping function as
           parameters.  The pixel mapping function should perform a manipulation on a single pixel and return
           a new pixel.

           .. activecode:: ex_7_21
              :nocodelens:

              import image

              def pixelMapper(oldimage, rgbFunction):


              def graypixel(oldpixel):


              win = image.ImageWin()
              img = image.Image("luther.jpg")

              newim = pixelMapper(img, graypixel)
              newim.draw(win)

              win.exitonclick()


.. question:: moreiter_ex_14

   When you scan in images using a scanner they may have lots of noise due to
   dust particles on the image itself or the scanner itself,
   or the images may even be damaged.  One way of eliminating this noise is
   to replace each pixel by the median value of the pixels surrounding it.

   .. activecode:: ex_7_22
      :nocodelens:

.. question:: moreiter_ex_15

           Research the Sobel edge detection algorithm and implement it.

           .. activecode:: ex_7_23
              :nocodelens:


