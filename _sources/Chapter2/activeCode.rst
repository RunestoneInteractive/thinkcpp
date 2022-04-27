Activecode Exercises
--------------------

Answer the following **Activecode** questions to assess what you have learned in this chapter.


.. tabbed:: VARS_a1

   .. tab:: Question

      .. activecode:: VARS_a1q
         :language: cpp

         Fix the code below so that it runs without errors.  Hint: you might need to change the names of some variables.
         ~~~~
         #include <iostream>
         using namespace std;

         int main () {
             char true = 'T';
             char false = 'F';

             cout << true << " is short for true. ";
             cout << false << " is short for false." << endl;
         }
         
   .. tab:: Answer

      .. activecode:: VARS_a1a
         :language: cpp

         Below is one way to fix the program.  ``true`` and ``false`` are keywords, so they cannot be used as variable names.
         ~~~~
         #include <iostream>
         using namespace std;

         int main () {
             char t = 'T';
             char f = 'F';
             cout << t << " is short for true. ";
             cout << f << " is short for false." << endl;
         }    


.. selectquestion:: VARS_a2_sq
   :fromid: VARS_a2, VARS_a2_p
   :toggle: lock


.. tabbed:: VARS_a3

   .. tab:: Question

      .. activecode:: VARS_a3q
         :language: cpp

         Fix the code below so that it prints "Cady scored 90% on the exam." 
         ~~~~
         #include <iostream>
         using namespace std;

         int main() {
             // Modify the next line so that Cady = 0.9.
             int Cady = 3 * 5 * (6 / 100);

             // DO NOT MODIFY ANYTHING BELOW THIS LINE.
             cout << "Cady scored " << Cady * 100 << "% on the exam.";
         }

   .. tab:: Answer

      .. activecode:: VARS_a3a
         :language: cpp

         Below is one way to fix the program.  We want to use doubles so that our result isn't rounded down to 0 through integer division.
         ~~~~
         #include <iostream>
         using namespace std;

         int main() {
             double Cady = 3 * 5 * (6 / 100.0);
             cout << "Cady scored " << Cady * 100 << "% on the exam.";
         }    


.. selectquestion:: VARS_a4_sq
   :fromid: VARS_a4, VARS_a4_p
   :toggle: lock


.. tabbed:: VARS_a5

   .. tab:: Question

      .. activecode:: VARS_a5q
         :language: cpp

         Fix the code below so that assigns ``a`` its correct value of ``'a'``.  Hint: use character operations!
         ~~~~
         #include <iostream>
         using namespace std;

         int main () {
            char a = 's';

            // Fix the line below.  Do NOT change the numbers!  Instead, 
            // change the location of the parentheses.
            a = a - 3 * 4 + (1 + 3);

            // DO NOT MODIFY ANYTHING BELOW THIS LINE.
            cout << a;
         }

   .. tab:: Answer

      .. activecode:: VARS_a5a
         :language: cpp

         Below is one way to complete the program.  There are many creative ways that you could use the order of operations to come up with a complex expression that will bring you to ``'a'``, here is one way.
         ~~~~
         #include <iostream>
         using namespace std;
      
         int main () {
            char a = 's';
            a = a - (3 * (4 + 1) + 3);
            cout << a;
         }


.. selectquestion:: VARS_a6_sq
   :fromid: VARS_a6, VARS_a6_p
   :toggle: lock


.. tabbed:: VARS_a7

   .. tab:: Question

      .. activecode:: VARS_a7q
         :language: cpp

         Write code that prints "Eat", "More", and "Chicken" on 3 consecutive lines. Be sure to inclue any necessary headers.
         ~~~~
         int main () {

         }

   .. tab:: Answer

      .. activecode:: VARS_a7a
         :language: cpp

         Below is one way to implement the solution.
         ~~~~
         #include <iostream>
         using namespace std;

         int main () {
             cout << "Eat" << endl;
             cout << "More" << endl;
             cout << "Chicken" << endl;
         } 


.. selectquestion:: VARS_a8_sq
   :fromid: VARS_a8, VARS_a8_p
   :toggle: lock


.. tabbed:: VARS_a9

   .. tab:: Question

      .. activecode:: VARS_a9q
         :language: cpp

         You have about three hours and fifteen minutes of homework to do today.  Rather than starting it right away, you choose to procrastinate by calculating how many seconds you'll be spending on your work.  Convert the time to seconds and store the result in ``seconds``.  Be sure to inclue any necessary headers.
         ~~~~
         int main () {

             // DO NOT MODIFY ANYTHING BELOW THIS LINE.
             cout << "Your solution had seconds = " << seconds << endl;  cout << "The correct solution has seconds = 11700";
         }

   .. tab:: Answer

      .. activecode:: VARS_a9a
         :language: cpp

         Below is one way to implement the solution.
         ~~~~
         #include <iostream>
         using namespace std;

         int main () {
             int hours = 3;
             int minutes = 15;
             int totalMinutes = minutes + 60 * hours;
             int seconds = totalMinutes * 60;
         }


.. selectquestion:: VARS_a10_sq
   :fromid: VARS_a10, VARS_a10_p
   :toggle: lock
