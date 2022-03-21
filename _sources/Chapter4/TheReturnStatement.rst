The Return Statement
--------------------

.. index::
   single: return statement

The ``return`` statement allows you to terminate the execution of a function
before you reach the end. One reason to use it is if you detect an error
condition:

.. activecode:: return_AC_1
   :language: cpp
   :caption: Terminating a Function with a Return

   This program will terminate with a return statement if the argument
   provided is not positive.  Try running the code as is.  If you get
   an error message, try changing the value of y.
   ~~~~
   #include <iostream>
   #include <cmath>
   using namespace std;

   void printLogarithm (double x) {
       if (x <= 0.0) {
           cout << "Positive numbers only, please." << endl;
           return;
       }
       double result = log (x);
       cout << "The log of x is " << result;
   }

    int main() {
        double y = -9.8;
        printLogarithm(y);
        return 0;
    }

This defines a function named ``printLogarithm`` that takes a ``double`` named x
as a parameter. The first thing it does is check whether x is less than
or equal to zero, in which case it displays an error message and then
uses ``return`` to exit the function. The flow of execution immediately
returns to the caller and the remaining lines of the function are not
executed.

I used a floating-point value on the right side of the condition because
there is a floating-point variable on the left.

Remember that any time you want to use a function from the math
library, you have to include the header file ``<cmath>``.

Putting ``return 0;`` in your code ends your program. Let's look back at a program from section 4.3. How would your answer change?




.. mchoice:: return_1
   :answer_a: One! Two! Three!
   :answer_b: Two! Three!
   :answer_c: Three!
   :answer_d: Two!
   :answer_e: One!
   :correct: b
   :feedback_a: Take a look at the first conditional statement more closely.
   :feedback_b: 8 is not greater than 8, so it doesn't meet the first condition.
   :feedback_c: All of the following are "if" statements, with no return. There are no "else" statements.
   :feedback_d: All of the following are "if" statements, with no return. There are no "else" statements.
   :feedback_e: Take a look at the first conditional statement more closely.

   What will print?

   ::

       #include <iostream>
       using namespace std;

       int main () {
         int x = 8;
         if (x > 8) {
           cout << "One! ";
         }
         if (x > 6) {
           cout << "Two! ";
         }
         if (x > 3) {
           cout << "Three!" << endl;
         }
         return 0;
       }


.. mchoice:: return_2
   :answer_a: One! Two! Three!
   :answer_b: Two! Three!
   :answer_c: Three!
   :answer_d: Two!
   :answer_e: One!
   :correct: d
   :feedback_a: Try again! 8 is not greater than 8, so the first condition will not be met.
   :feedback_b: Try again! Remember what "return 0" is for!
   :feedback_c: Try again! 8 is greater than 6!
   :feedback_d: Correct!
   :feedback_e: Take a look at the first conditional statement more closely.

   What will print?

   ::

       #include <iostream>
       using namespace std;

       int main () {
         int x = 8;
         if (x > 8) {
           cout << "One! ";
           return 0;
         }
         if (x > 6) {
           cout << "Two! ";
           return 0;
         }
         if (x > 3) {
           cout << "Three!" << endl;
           return 0;
         }
         return 0;
       }
