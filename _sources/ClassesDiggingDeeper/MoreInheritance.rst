..  Copyright (C)  Brad Miller, David Ranum, Jeffrey Elkner, Peter Wentworth, Allen B. Downey, Chris
    Meyers, and Dario Mitchell.  Permission is granted to copy, distribute
    and/or modify this document under the terms of the GNU Free Documentation
    License, Version 1.3 or any later version published by the Free Software
    Foundation; with Invariant Sections being Forward, Prefaces, and
    Contributor List, no Front-Cover Texts, and no Back-Cover Texts.  A copy of
    the license is included in the section entitled "GNU Free Documentation
    License".

More Inheritance
----------------

In this example we define SFraction, specialized sub-class of Fraction. SFraction objects are automatically reduced to simplest form as they are instantiated.

.. activecode:: c2k

    def gcd(m, n):
        while m % n != 0:
            oldm = m
            oldn = n
            m = oldn
            n = oldm % oldn
        return n

    class Fraction:
        def __init__(self, top, bottom):
            self.num = top        # the numerator is on top
            self.den = bottom     # the denominator is on the bottom

        def __str__(self):
            return '{}/{}'.format(self.__num, self.__den)

    class SFraction(Fraction):
        '''a Fraction in simplest form'''
        def __init__(self, top, bottom):
            common = gcd(top, bottom)
            Fraction.__init__(self, top // common, bottom // common)

    afraction = Fraction(12, 16)
    print(afraction)
    sfraction = SFraction(12, 16)
    print(sfraction)


