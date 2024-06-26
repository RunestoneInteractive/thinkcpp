Parameters and Variables are Local
----------------------------------

Parameters and variables only exist inside their own functions. Within
the confines of ``main``, there is no such thing as phil. If you try to use
it, the compiler will complain. Similarly, inside ``printTwice`` there is no
such thing as argument.

.. activecode:: locals_AC_1
   :language: cpp
   :caption: Understanding Parameters

   The following code will show the output of the printTwice function.
   Notice that it is the argument 'b' that is outputted, not the
   variable 'phil'.
   ~~~~
   #include <iostream>
   using namespace std;

   void printTwice (char phil) {
       cout << phil << phil << endl;
   }

   int main () {
       char argument = 'b';
       printTwice (argument);
       return 0;
   }

.. index::
   single: local
   single: local variable

.. index::
   single: stack diagram

Variables like this are said to be **local**. In order to keep track of
parameters and local variables, it is useful to draw a **stack
diagram**. Like state diagrams, stack diagrams show the value of each
variable, but the variables are contained in larger boxes that indicate
which function they belong to.

For example, the state diagram for ``printTwice`` looks like this:

.. figure:: Images/3.9stackdiagram.png
   :scale: 50%
   :align: center
   :alt: image

.. index::
   pair: function; instance

Whenever a function is called, it creates a new **instance** of that
function. Each instance of a function contains the parameters and local
variables for that function. In the diagram an instance of a function is
represented by a box with the name of the function on the outside and
the variables and parameters inside.

In the example, ``main`` has one local variable, argument, and no
parameters. ``printTwice`` has no local variables and one parameter, named
phil.


.. mchoice:: locals_1
   :answer_a: 1 local variable, 1 parameter
   :answer_b: 0 local variables, 1 parameter
   :answer_c: 2 local variables, 0 parameters
   :answer_d: 2 local variables, 1 parameter
   :correct: c
   :feedback_a: A parameter would be located within the parentheses next to the function's name.
   :feedback_b: A parameter would be located within the parentheses next to the function's name.
   :feedback_c: Correct!
   :feedback_d: A parameter would be located within the parentheses next to the function's name.

   How many local variables and parameters does ``main`` have?

   ::

       void printHelloName (string name) {
         cout << "Hello " << name << "!";
       }

       int main () {
         string name1 = "Phil";
         printHelloName(name1);
         string name2 = "Joe";
         printHelloName(name2);
         return 0;
       }


.. mchoice:: locals_2
   :answer_a: 1 local variable, 1 parameter
   :answer_b: 0 local variables, 1 parameter
   :answer_c: 2 local variables, 0 parameters
   :answer_d: 2 local variables, 1 parameter
   :correct: b
   :feedback_a: A local variable exists when a variable is declared within a function.
   :feedback_b: Correct!
   :feedback_c: A local variable exists when a variable is declared within a function.
   :feedback_d: A local variable exists when a variable is declared within a function.

   How many local variables and parameters does ``printHelloName`` have?

   ::

       void printHelloName (string name) {
         cout << "Hello " << name << "!";
       }

       int main () {
         string name1 = "Phil";
         printHelloName(name1);
         string name2 = "Joe";
         printHelloName(name2);
         return 0;
       }


.. fillintheblank:: locals_3

   Whenever we make a function call, we create a(n) |blank| of that function,
   which contains the parameters and local variables for that function.
    
   - :[Ii][Nn][Ss][Tt][Aa][Nn][Cc][Ee]: You could create many instances of one function, each with their own parameters and local variables if you wanted!
     :.*: Try again!

.. mchoice:: locals_4
   :answer_a: 1 call
   :answer_b: 4 calls
   :answer_c: 2 calls
   :answer_d: 3 calls
   :correct: b
   :feedback_a: hi( ) is called from multiple functions.
   :feedback_b: Correct!
   :feedback_c: hi( ) is called from multiple functions.
   :feedback_d: Two calls from one function are indeed two seperate calls.

   How many calls to ``hi`` are made during the exectuion of the entire program?

   ::

       void hi() {
         cout << "hiii !"<<endl;
       }
      
       void printGreeting(){
         hi();
         cout<<"how are you doing today. "<<endl;
         hi();
       }

       int main () {
         hi();
         printGreeting();
         hi();
         return 0;
       }
