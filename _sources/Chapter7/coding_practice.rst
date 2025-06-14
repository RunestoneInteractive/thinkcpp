Coding Practice
---------------

.. tabbed:: cp_7_1

    .. tab:: Question

        A palindrome is a word, phrase, or sentence that reads the same forwards and backwards.
        Write a function ``isPalindrome`` that takes a ``string input`` as a parameter and returns 
        a boolean that is true if the input is a palindrome and false otherwise. Run and test your code!

        .. activecode:: cp_7_AC_1q
           :language: cpp
           :compileargs: [ '-Wall', '-Werror' ]
           :practice: T

           #include <iostream>
           #include <cctype>
           using namespace std;

           bool isPalindrome (string input) {
               // Write your implementation here.
           }
           ====
           #define DOCTEST_CONFIG_IMPLEMENT_WITH_MAIN
           #include "doctest.h"

           TEST_CASE("factorial function") {
               CHECK(isPalindrome("racecar"));
               CHECK(isPalindrome("no lemon, no melon"));
               CHECK_FALSE(isPalindrome("kangaroo"));
           }


    .. tab:: Answer

        Below is one way to implement the program. We use the ``isalpha`` function
        to ignore the non alphabetical characters. Then we continuously check to see 
        if the letters in the front are equal to the ones in the back until we reach the 
        middle of the string.

        .. activecode:: cp_7_AC_1a
           :language: cpp
           :compileargs: [ '-Wall', '-Werror' ]
           :optional:

           #include <iostream>
           #include <cctype>
           using namespace std;

           bool isPalindrome (string input) {
               size_t front = 0;
               size_t back = input.length() - 1;
               while (front < back) {
                   while (!isalpha(input[front])) {
                       front++;
                   }
                   while (!isalpha(input[back])) {
                       back--;
                   }
                   if (input[front] != input[back]) {
                       return false;
                   }
                   front++;
                   back--;
               }
               return true;
           }
           ====
           #define DOCTEST_CONFIG_IMPLEMENT_WITH_MAIN
           #include "doctest.h"

           TEST_CASE("factorial function") {
               CHECK(isPalindrome("racecar"));
               CHECK(isPalindrome("no lemon, no melon"));
               CHECK_FALSE(isPalindrome("kangaroo"));
           }

.. selectquestion:: cp_7_AC_2q_sq
    :fromid: cp_7_AC_2q, cp_7_AC_2q_pp
    :toggle: lock

.. tabbed:: cp_7_3

    .. tab:: Question

        Write a void function ``censorWord`` that censors a given word from a given string and prints
        out the new string. ``censorWord`` should take two strings ``input`` and ``word`` as parameters
        and prints out ``input`` with every occurence of ``word`` censored with asterisks. For example, 
        ``censorWord ("I really, really, really, really, really, really like you", "really")`` results in 
        the following output:

        :: 
   
           I ******, ******, ******, ******, ******, ****** like you

        .. activecode:: cp_7_AC_3q
           :language: cpp
           :compileargs: [ '-Wall', '-Werror' ]
           :practice: T

           #include <iostream>
           using namespace std;

           void censorWord (string input, string word) {
               // Write your implementation here.
           }

           int main() {
               censorWord ("I really, really, really, really, really, really like you", "really");
           }


    .. tab:: Answer

        Below is one way to implement the program. We use a while loop to
        repeatedly search for instances of word in input. Once found, we replace 
        the length of the word with asterisks.

        .. activecode:: cp_7_AC_3a
           :language: cpp
           :compileargs: [ '-Wall', '-Werror' ]
           :optional:

           #include <iostream>
           using namespace std;

           void censorWord(string input, string word) {
               size_t length = word.length();
               while (input.find(word) != string::npos) {
                   int index = input.find(word);
                   size_t i = 0;
                   while (i < length) {
                       input[index + i] = '*';
                       i++;
                   }
               }
               cout << input;
           }

           int main() {
               censorWord ("I really, really, really, really, really, really like you", "really");
           }

.. selectquestion:: cp_7_AC_4q_sq
    :fromid: cp_7_AC_4q, cp_7_AC_4q_pp
    :toggle: lock

.. tabbed:: cp_7_5

    .. tab:: Question

        ROT13 is a simple letter substitution cipher that shifts every letter forward by 13,
        looping around if necessary. For example, the letter 'a', 1st in the alphabet, becomes
        the letter 'n', 14th in the alphabet. The letter 'r', 18th in the alphabet, becomes the 
        letter 'e', 5th in the alphabet. Since the alphabet has 26 letters and 13 is exactly half, 
        a message encrypted using ROT13 can be decrypted by calling ROT13 on the encrypted message.
        Write the function ``ROT13``, which takes a ``string input`` as a parameter and returns 
        an encrypted ``string``. Test your function in ``main``.

        .. activecode:: cp_7_AC_5q
           :language: cpp
           :compileargs: [ '-Wall', '-Werror' ]
           :practice: T

           #include <iostream>
           #include <cctype>
           using namespace std;

           string ROT13 (string input) {
               // Write your implementation here.
           }

           int main() {
               string original = "Encrypt me then decrypt me!";
               string encrypted = ROT13 (original);
               string decrypted = ROT13 (encrypted);
               cout << "Original string: " << original << endl;
               cout << "Encrypted string: " << encrypted << endl;
               cout << "Decrypted string: " << decrypted << endl;

               // Uncomment and run the code below once your function works!
               // string secretMessage = "Pbatenghyngvbaf! Lbh'ir fhpprffshyyl vzcyrzragrq EBG13 naq qrpbqrq gur frperg zrffntr :)";
               // cout << ROT13 (secretMessage) << endl;
           }


    .. tab:: Answer

        Below is one way to implement the ``ROT13`` function. We use a ``while`` loop to
        go through all the letters in the ``string``. If the letter is between 'a' and 'n' or 
        'A' and 'N', we use character operations to add 13 to each letter. Otherwise,
        we subtract 13 from each letter. We return the encrypted message at the end.

        .. activecode:: cp_7_AC_5a
           :language: cpp
           :compileargs: [ '-Wall', '-Werror' ]
           :optional:

           #include <iostream>
           #include <cctype>
           using namespace std;

           string ROT13(string input) {
               size_t n = 0;
               while (n < input.length()) {
                   if (isalpha(input[n])) {
                       if ((input[n] >= 'a' && input[n] < 'n') || (input[n] >= 'A' && input[n] < 'N')) {
                           input[n] = input[n] + 13;
                       }
                       else {
                           input[n] = input[n] - 13;
                       }
                   }
                   n++;
               }
               return input;
           }

           int main() {
               string original = "Encrypt me then decrypt me!";
               string encrypted = ROT13 (original);
               string decrypted = ROT13 (encrypted);
               cout << "Original string: " << original << endl;
               cout << "Encrypted string: " << encrypted << endl;
               cout << "Decrypted string: " << decrypted << endl;

               // Uncomment and run the code below once your function works!
               // string secretMessage = "Pbatenghyngvbaf! Lbh'ir fhpprffshyyl vzcyrzragrq EBG13 naq qrpbqrq gur frperg zrffntr :)";
               // cout << ROT13 (secretMessage) << endl;
           }

.. selectquestion:: cp_7_AC_6q_sq
    :fromid: cp_7_AC_6q, cp_7_AC_6q_pp
    :toggle: lock

.. tabbed:: cp_7_7

    .. tab:: Question

        Write the function ``capitalize``, which takes a ``string input`` as a parameter.
        ``capitalize`` capitalizes the first letter of every word, and returns the new ``string``.

        .. activecode:: cp_7_AC_7q
           :language: cpp
           :compileargs: [ '-Wall', '-Werror' ]
           :practice: T

           #include <iostream>
           #include <cctype>
           using namespace std;

           string capitalize (string input) {
               // Write your implementation here.
           }

           int main() {
               cout << capitalize ("every word in this string should be capitalized!") << endl;
               cout << capitalize ("this String As well") << endl;
           }


    .. tab:: Answer

        Below is one way to implement the ``capitalize`` function. We use a ``while`` loop to
        go through all the ``char``\s in the ``string``. We capitalize the first character
        and all characters following a space using ``toupper``. At the end, we return the ``string``.

        .. activecode:: cp_7_AC_7a
           :language: cpp
           :compileargs: [ '-Wall', '-Werror' ]
           :optional:

           #include <iostream>
           #include <cctype>
           using namespace std;

           string capitalize (string input) {
               size_t n = 0;
               while (n < input.length()) {
                   if (n == 0) {
                       input[n] = toupper(input[n]);
                   }
                   else if (input[n-1] == ' ') {
                       input[n] = toupper(input[n]);
                   }
                   n++;
               }
               return input;
           }

           int main() {
               cout << capitalize ("every word in this string should be capitalized!") << endl;
               cout << capitalize ("this String As well") << endl;
           }

.. selectquestion:: cp_7_AC_8q_sq
    :fromid: cp_7_AC_8q, cp_7_AC_8q_pp
    :toggle: lock

.. tabbed:: cp_7_9

    .. tab:: Question

        Write the function ``longestWord``, which takes a ``string input`` as a parameter.
        ``longestWord`` returns the words with the most letters in ``input``. If there's a tie,
        return the first word. Use the ``substr`` function. Run and test your code!

        .. activecode:: cp_7_AC_9q
           :language: cpp
           :compileargs: [ '-Wall', '-Werror' ]
           :practice: T

           #include <iostream>
           using namespace std;

           string longestWord (string input) {
               // Write your implementation here.
           }
           ====
           #define DOCTEST_CONFIG_IMPLEMENT_WITH_MAIN
           #include "doctest.h"

           TEST_CASE("longestWord function") {
               CHECK_EQ(longestWord("what is the longest word in this string"), "longest");
               CHECK_EQ(longestWord("these words are very close in size"), "these");
               CHECK_EQ(longestWord("vowels"), "vowels");
           }


    .. tab:: Answer

        Below is one way to implement the ``longestWord`` function. We use a ``while`` loop to
        go through all the ``char``\s in the ``string``. We use variables to keep track of the
        longest word, the longest amount of letters, and the length of the current word. We
        can determine the length of a word by counting the number of ``char``\s between spaces.
        If the length is greater than the max, length becomes the new max and we update the longest word.
        This keeps repeating until we reach the end of the string, and the longest word is returned.

        .. activecode:: cp_7_AC_9a
           :language: cpp
           :compileargs: [ '-Wall', '-Werror' ]
           :optional:

           #include <iostream>
           using namespace std;

           string longestWord (string input) {
               size_t n = 0;
               string longest;
               size_t maxLength = 0;
               while (n < input.length()) {
                   size_t wordLength = 0;
                   while (input[n] != ' ' && n < input.length()) {
                       wordLength++;
                       n++;
                   }
                   if (wordLength > maxLength) {
                       maxLength = wordLength;
                       longest = input.substr(n - maxLength, maxLength);
                   }
                   n++;
               }
               return longest;
           }
           ====
           #define DOCTEST_CONFIG_IMPLEMENT_WITH_MAIN
           #include "doctest.h"

           TEST_CASE("longestWord function") {
               CHECK_EQ(longestWord("what is the longest word in this string"), "longest");
               CHECK_EQ(longestWord("these words are very close in size"), "these");
               CHECK_EQ(longestWord("vowels"), "vowels");
           }

.. selectquestion:: cp_7_AC_10q_sq
    :fromid: cp_7_AC_10q, cp_7_AC_10q_pp
    :toggle: lock
