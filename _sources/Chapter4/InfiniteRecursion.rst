Infinite Recursion
------------------

.. index::
   single: base case

In the examples in the previous section, notice that each time the
functions get called recursively, the argument gets smaller by one, so
eventually it gets to zero. When the argument is zero, the function
returns immediately, *without making any recursive calls*. This
case—when the function completes without making a recursive call—is
called the **base case**.

.. index::
   single: infinite recursion

If a recursion never reaches a base case, it will go on making recursive
calls forever and the program will never terminate. This is known as
**infinite recursion**, and it is generally not considered a good idea.

In most programming environments, a program with an infinite recursion
will not really run forever. Eventually, something will break and the
program will report an error. 

.. warning::
   Infinite recursion is the first example we have seen of a run-time 
   error (an error that does not appear until you run the program).

You should write a small program that recurses forever and run it to see
what happens. Below is an example. The function adds to the number **n**
instead of subtracting, which means it is always larger than 0. Therefore,
the function executes "forever." Unfortunately, if there was a snip of live
code put in below, the ebook's page would extend down forever because a new
line is being created infinitely.

::

    #include <iostream>
    #include <cmath>
    using namespace std;

    void nLines(int n) {
      if (n > 0) {
        cout << endl;
        nLines(n + 1);
      }
    }

    int main() {
      void nLines(10);
    }


.. fillintheblank:: unbounded_recursion_1

   If a recursive function never reaches its |blank| |blank|, then the function
   will continue executing indefinitely.  This is called |blank| |blank|.

   - :[Bb][Aa][Ss][Ee]: Correct!
     :x: Try again!
   - :[Cc][Aa][Ss][Ee]: Correct!
     :x: Try again!
   - :[Ii][Nn][Ff][Ii][Nn][Ii][Tt][Ee]: Correct!
     :.*: Try again!
   - :[Rr][Ee][Cc][Uu][Rr][Ss][Ii][Oo][Nn]: Correct!
     :.*: Try again!


.. mchoice:: unbounded_recursion_2
   :answer_a: The function will print "Not Negative!"
   :answer_b: The function will print "Not Negative!" more than once.  Then it will print "Negative!" and will stop executing.
   :answer_c: The function will print "Negative!"
   :answer_d: The function will never stop executing, there will be infinite recursion.
   :correct: c
   :feedback_a: The function will never print "Not Negative!" since we start with a negative number!
   :feedback_b: The function will never print "Not Negative!" since we start with a negative number!
   :feedback_c: We start with a negative number, so the function will reach the base case.
   :feedback_d: We start with a negative number, so the function will reach the base case.

   Take a look at the code below.  What will happen if you were to run it on
   your machine?

   ::

       #include <iostream>
       using namespace std;

       void isNegative(int n) {
         if (n >= 0) {
           cout << "Not Negative!";
           isNegative(n - 1);
         }
         cout << "Negative!";
       }

       int main() {
         isNegative(-10);
       }


.. mchoice:: unbounded_recursion_3
   :answer_a: The function will print "Not Negative!"
   :answer_b: The function will print "Not Negative!" more than once.  Then it will print "Negative!" and will stop executing.
   :answer_c: The function will print "Negative!"
   :answer_d: The function will never stop executing, there will be infinite recursion.
   :correct: b
   :feedback_a: The function will print "Not Negative!", but it won't stop there!
   :feedback_b: The function will print "Not Negative!" until it reaches a negative number.
   :feedback_c: The function will eventually print "Not Negative!", but that's not all!
   :feedback_d: Since we decrement each time, the base case will be reached.

   Suppose we have already defined isNegative (see previous question).
   What will happen if we run the code with this input?

   ::

       #include <iostream>
       using namespace std;

       int main() {
         isNegative(10);
       }


.. mchoice:: unbounded_recursion_4
   :answer_a: The function will print "Not Negative!"
   :answer_b: The function will print "Not Negative!" more than once.  Then it will print "Negative!" and will stop executing.
   :answer_c: The function will print "Negative!"
   :answer_d: The function will never stop executing, there will be infinite recursion.
   :correct: d
   :feedback_a: The function will print "Not Negative!" but it won't stop there!
   :feedback_b: The function will print "Not Negative!" more than once.  But will it print "Negative"?
   :feedback_c: We start with a positive number, so the function simply won't print "Not Negative!"
   :feedback_d: Our input is incremented with every recursive call, so if we start with a positive number, we will never reach the base case.

   The isNegative function has been **edited** as shown below.  What will 
   happen now when we run the code?

   ::

       #include <iostream>
       using namespace std;

       void isNegative(int n) {
         if (n >= 0) {
           cout << "Not Negative!";
           isNegative(n + 1);
         }
         cout << "Negative!";
       }

       int main() {
         isNegative(10);
       }
