Traversal
---------
.. index::
   single: traversal

A common thing to do with a string is start at the beginning, select
each character in turn, do something to it, and continue until the end.
This pattern of processing is called a **traversal**. A natural way to
encode a traversal is with a ``while`` statement.

.. activecode:: traversal_AC_1
  :language: cpp
  :compileargs: [ '-Wall', '-Werror', '-Wno-sign-compare' ]
  :caption: Accessing a string character

  The active code below outputs each letter of string ``fruit``
  using a while loop.
  ~~~~
  #include <string>
  #include <iostream>
  using namespace std;

  int main() {
      int index = 0;
      string fruit = "apple";
      int lengthfruit = fruit.length();
      while (index < lengthfruit) {
          char letter = fruit[index];
          cout << letter << endl;
          index = index + 1;
      }
  }

This loop traverses the string and outputs each letter on a line by
itself. Notice that the condition is ``index < lengthfruit``, which
means that when ``index`` is equal to the length of the string, the
condition is false and the body of the loop is not executed. The last
character we access is the one with the index ``fruit.length()-1``.

.. index::
   single: index

The name of the loop variable is ``index``. An **index** is a variable
or value used to specify one member of an ordered set, in this case the
set of characters in the string. The index indicates (hence the name)
which one you want. The set has to be ordered so that each letter has an
index and each index refers to a single character.

As an exercise, write a function that takes an ``string`` as an argument
and that outputs the letters backwards, all on one line.

.. activecode:: traversal_AC_2 
   :language: cpp
   :compileargs: [ '-Wall', '-Werror', '-Wno-sign-compare' ]

   Try writing the ``reverseWord`` function in the commented section
   of the active code below. If done correctly, the program should output "hello"
   backwards. If you get stuck, you can reveal the extra problem at the end for help. 
   ~~~~
   #include <iostream>
   using namespace std;

   void reverseWord (string word) {
       // ``reverseWord`` should take the letters of ``word``
       // and output them in reverse.
   }

   int main() {
       reverseWord("hello");
   }

.. reveal:: 7_5_1
   :showtitle: Reveal Problem
   :hidetitle: Hide Problem

   .. parsonsprob:: traversal_1
      :numbered: left
      :adaptive:
   
      Let's write the code for the ``reverseWord`` function. ``reverseWord``
      should take a string as a parameter and output the letters backwards.
      -----
      void reverseWord (string input) {
      =====
        int x = input.length() - 1;
      =====
        int x = input.length();  #paired
      =====
        while (x >= 0) {
      =====
        while (x > 0) { #paired
      =====
          cout << input[x];
      =====
          x = x - 1;
        }
      }
      =====
          x = x + 1;
        }
      } #distractor

.. mchoice:: traversal_2
   :practice: T
   :answer_a: 0
   :answer_b: 1
   :answer_c: 2
   :correct: b
   :feedback_a: i goes through the odd numbers starting at 1.
   :feedback_b: Yes, i goes through the odd numbers starting at 1.  o is at position 1 and 8.
   :feedback_c: There are 2 o characters but idx does not take on the correct index values for both.


   How many times is the letter o printed by the following statements?

   .. code-block:: cpp

      string s = "coding rocks";
      int i = 1;
      int length = s.length();
      while (i < length) {
        cout << s[i] << endl;
        i = i + 2;
      }

.. mchoice:: traversal_3
   :practice: T 
   :answer_a: e e n r 1
   :answer_b: e e e e e
   :answer_c: e e n r
   :correct: a
   :feedback_a: Correct! the values of index are 0 0 1 3 6. After this while loop ends.
   :feedback_b: We are updating the value of of <code>index</code>. Not doing so would make it an infinte loop! 
   :feedback_c: Recalculate the values of <code>index</code> at each stage and consider which ones are &lt 7. 


   What is printed when the code is run?

   .. code-block:: cpp

      string truth = "engr101";
      int index = 0;
      int counter = 0;
      while ( index < truth.length() ) {
        cout << truth[index] <<" ";
        index = index + counter;
        counter = counter + 1;
      }
