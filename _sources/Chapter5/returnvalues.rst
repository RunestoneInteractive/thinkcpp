Return Values
-------------

Some of the built-in functions we have used, like the math functions,
have produced results. That is, the effect of calling the function is to
generate a new value, which we usually assign to a variable or use as
part of an expression. For example:

::

    double e = exp (1.0);
    double height = radius * sin (angle);

But so far all the functions we have written have been ``void``
functions; that is, functions that return no value. When you call a ``void``
function, it is typically on a line by itself, with no assignment:

::

    nLines (3);
    countdown (n-1);

..	index::
	  pair: functions; fruitful functions

In this chapter, we are going to write functions that return things,
which I will refer to as **fruitful** functions, for want of a better
name. The first example is area, which takes a double as a parameter,
and returns the area of a circle with the given radius:

::

    double area (double radius) {
      double pi = acos (-1.0);
      double area = pi * radius * radius;
      return area;
    }

The first thing you should notice is that the beginning of the function
definition is different. Instead of ``void``, which indicates a ``void``
function, we see ``double``, which indicates that the return value from this
function will have type ``double``.

.. note::
   Functions can have any return type in C++.  The return type is always
   specified before the name of the function.

Also, notice that the last line is an alternate form of the return
statement that includes a return value. This statement means, “return
immediately from this function and use the following expression as a
return value.” The expression you provide can be arbitrarily
complicated, so we could have written this function more concisely:

::

    double area (double radius) {
      return acos(-1.0) * radius * radius;
    }

..	index::
	  pair: variables; temporary variables

On the other hand, **temporary** variables like area often make
debugging easier. In either case, the type of the expression in the
return statement must match the return type of the function. In other
words, when you declare that the return type is ``double``, you are making a
promise that this function will eventually produce a ``double``. If you try
to return with no expression, or an expression with the wrong type, the
compiler will take you to task.

Sometimes it is useful to have multiple return statements, one in each
branch of a conditional:

::

    double absoluteValue (double x) {
      if (x < 0) {
        return -x;
      } 
      else {
        return x;
      }
    }

Since these returns statements are in an alternative conditional, only
one will be executed. Although it is legal to have more than one return
statement in a function, you should keep in mind that as soon as one is
executed, the function terminates without executing any subsequent
statements.

.. warning::
   If you put return statements inside of a chain of conditionals, then 
   you have to guarantee that *every possible path* through the program 
   hits a return statement.  If you forget, your code will have errors.

..	index::
	  pair: code; dead code

Code that appears after a return statement, or any place else where it
can never be executed, is called **dead code**. Some compilers warn you
if part of your code is dead.

.. activecode:: return_vals_AC_1
   :language: cpp
   :caption: Return Values

   Notice that there are two return statements in the code below.
   What if we pass zero as an argument, and neither conditional
   returns true?
   ~~~~
   #include <iostream>
   using namespace std;

   double absoluteValue (double x) {
       if (x < 0) {
           return -x;
       } 
       else if (x > 0) {
           return x;
       }                          // WRONG!!
   }

   int main () {
       cout << absoluteValue(0);
       return 0;
   }

This program is not correct because if x happens to be 0, then neither
condition will be true and the function will end without hitting a
return statement. Unfortunately, many C++ compilers do not catch this
error. As a result, the program may compile and run, but the return
value when ``x == 0`` could be anything, and will probably be different in
different environments.

By now you are probably sick of seeing compiler errors, but as you gain
more experience, you will realize that the only thing worse than getting
a compiler error is *not* getting a compiler error when your program is
wrong.

Here’s the kind of thing that’s likely to happen: you test ``absoluteValue``
with several values of x and it seems to work correctly. Then you give
your program to someone else and they run it in another environment. It
fails in some mysterious way, and it takes days of debugging to discover
that the problem is an incorrect implementation of ``absoluteValue``. If
only the compiler had warned you!

From now on, if the compiler points out an error in your program, you
should not blame the compiler. Rather, you should *thank* the compiler for
finding your error and sparing you days of debugging. Some compilers
have an option that tells them to be extra strict and report all the
errors they can find. You should turn this option on all the time. The
implementation below would fix the error in the code.

.. activecode:: return_vals_AC_2
   :language: cpp
   :caption: Return Values

   This code fixes the error in the previoius implementation of
   absoluteValue.  If we pass 0 as an argument, the function will
   return 0.  Thus, every route through the conditonal is satisfied.
   ~~~~
   #include <iostream>
   using namespace std;

   double absoluteValue (double x) {
       if (x < 0) {
           return -x;
       } 
       else if (x > 0) {
           return x;
       }
       return x;       // Corrected! 
   }

   int main () {
      cout << absoluteValue(0);
      return 0;
   }

As an aside, you should know that there is a function in the math
library called fabs that calculates the absolute value of a
double—correctly.


.. mchoice:: return_vals_1
   :answer_a: double
   :answer_b: int
   :answer_c: string
   :answer_d: char
   :correct: c
   :feedback_a: There are no doubles used in this function.
   :feedback_b: The parameter does not have to be the same type as the return type.
   :feedback_c: The variable "outside" is being returned, which is of string type.
   :feedback_d: The return type is actually a string of chars.

   What should the return type of the below function be?

   ::

       ________ weather (int temp) {
        string outside = "";
        if (temp < 50) {
          outside = "cold";
        }
        else {
          outside = "warm"
        }
        return outside;
       }


.. mchoice:: return_vals_2
   :answer_a: 4
   :answer_b: 2
   :answer_c: 16
   :answer_d: The function does not return.
   :correct: b
   :feedback_a: The function returns y before reaching the line where y is doubled.
   :feedback_b: Because the return statement in the timesTwo function returns prior to the modification of y, 2 is returned and then printed.
   :feedback_c: The function returns y before reaching the line where y is doubled.
   :feedback_d: The function has an integer return type, so it WILL return an int.

   What will print?

   ::

       #include <iostream>
       using namespace std;

       int timesTwo(int x) {
         int y = x;
         return y;
         y = y * 2;
       }

       int main () {
         int i = 2;
         cout << timesTwo(i);
         return 0;
       }

.. mchoice:: dead_code_printing_1
   :answer_a: You get a child discount yay! 
   :answer_b: Sorry you have to pay full price. 
   :answer_c: nothing gets printed
   :answer_d: 9.50
   :correct: c
   :feedback_a: The function returns goes to the else block as age is not less than 5.
   :feedback_b: The function returns 9.50 before reaching the output statment.
   :feedback_c: The return statement is encountered before the cout statement.
   :feedback_d: Although 9.50 is returned there is no printing of this value.

   What will print?

   ::

       #include <iostream>
       using namespace std;

       double ticket_price(int age) {
          if(age<5){
              return 5.50;
              cout<<" You get a child discount yay!"<<endl;
          }

          else{
              return 9.50;
              cout<<" Sorry you have to pay full price."<<endl;
          }
          return 0.0; //to avoid compiler error
       }

       int main () {
         int years = 5;
         double price = ticket_price(5);
         return 0;
       }

.. fillintheblank:: return_vals_3

   A variable that exists only inside a function, is called a |blank| variable.

   - :[Tt][Ee][Mm][Pp][Oo][Rr][Aa][Rr][Yy]: Temporary variables are useful for calculating and returning values inside functions since they are short-lived.
     :.*: Try again!
  
