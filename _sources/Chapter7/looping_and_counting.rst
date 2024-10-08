
.. _loopcount:

Looping and counting
--------------------

.. activecode:: looping_and_counting_AC_1
  :language: cpp
  :caption: Looping and counting

  The active code below counts the number of times the letter ``'a'``
  appears in a string ``fruit``.
  ~~~~
  #include <iostream>
  using namespace std;

  int main() {
      string fruit = "banana";
      size_t count = 0;

      size_t index = 0;
      while (index < fruit.length()) {
          if (fruit[index] == 'a') {
              count = count + 1;
          }
          index = index + 1;
      }
      cout << count << endl;
  }

.. index:: 
   single: counter
   single: increment
   single: decrement

This program demonstrates a common idiom, called a **counter**. The
variable ``count`` is initialized to zero and then incremented each time
we find an ``’a’``. (To **increment** is to increase by one; it is the
opposite of **decrement**, and unrelated to **excrement**, which is a
noun.) When we exit the loop, ``count`` contains the result: the total
number of a’s.

.. mchoice:: looping_counting_1
   :practice: T
   :answer_a: 5 4 3 2 1
   :answer_b: -5 -4 -3 -2 -1
   :answer_c: -4 -3 -2 -1 0
   :correct: c
   :feedback_a: Notice that x is negative.
   :feedback_b: Notice that the value of x is incremented before it is printed.
   :feedback_c: The value of x is incremented before it is printed so the first value printed is -4.


   What does the following code print?

   .. code-block:: cpp
      :linenos:

      int x = -5;
      while (x < 0) {
        x = x + 1;
        cout << x << " ";
      }


.. parsonsprob:: looping_counting_2
   :numbered: left
   :adaptive:

   As an exercise, encapsulate this code in a function named
   ``countLetters``, and generalize it so that it accepts the string and
   the letter as arguments. In the function, declare ``length``, ``count``, and ``index`` in that order.
   Within the main function, declare ``city`` and ``letter`` in that order.
   -----
   size_t countLetters(string s, char letter) {
   =====
      size_t length = s.length();
   =====
      size_t count = 0;
   =====
      size_t index = 0;
   =====
      while (index < length) {
   =====
        if (s[index] == letter) {
   =====
          count = count + 1; 
        }
   =====
        index = index + 1; 
      }
   =====
      return count; 
   }
   =====
   int main() {
   =====
      string city = "New Baltimore";
   =====
      char letter = "e";
   =====
      cout << countLetters(city, letter); 
   }


.. parsonsprob:: looping_counting_3
   :numbered: left
   :adaptive:

   The following is the correct code for printing the even numbers from 0 to 10, but it also includes some extra code that you won't need. Drag the needed blocks from the left and put them in the correct order on the right.
   -----
   x = x + 1; #distractor
   =====
   x = 0;
   =====
   while (x <= 10) {
   =====
   while (x < 10) { #distractor
   =====
      cout << x << endl;
   =====
      x = x + 2;
   }

.. mchoice:: looping_counting_4
   :practice: T


   What is the value of ``counter`` right before main returns 0?

   .. code-block:: cpp
      :linenos:

      string word_1 = "understand";
      string word_2 = "underwaa";

      size_t end_1 = word_1.length();
      size_t end_2 = word_2.length();

      if ( end_2 < end_1 ){
         end_1 = end_2;
      }

      size_t index = 0;
      size_t counter = 0;

      while ( index < end_1 ) {
        if ( word_1[index] == word_2[index] ){
           counter = counter + 1;
        }
        else {
           counter = counter - 1;
        }
        index = index + 1;
      }
      
      return 0;

   - The code dosen't reach ``return 0`` because we index out of bounds in ``word_2``.

     - We set ``end_1`` to be the smaller of the two lengths so we don't index out of bounds.

   - 2

     - Not all the letters after index 4 differ in the two words.

   - 3

     - We decrement the value of counter when we don't have matching letters.

   - 4

     + Correct! we have 6 matching letters and 2 differing letters upto the length of ``word_2``.
