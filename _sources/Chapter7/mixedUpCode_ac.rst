Activecode Exercises
----------------------

Answer the following **Activecode** questions to
assess what you have learned in this chapter.


.. tabbed:: mucp_7_1_ac

    .. tab:: Question

        .. activecode:: mucp_7_1_ac_q
            :language: cpp
            :compileargs: [ '-Wall', '-Werror' ]

            Write a program that prints the 4th character of word, 
            and finds and replaces all instances of 'i' with 'e'.
            Finally, print out the string.            
            ~~~~
            #include <iostream> 
            #include <string>
            using namespace std;
            // YOUR CODE HERE


    .. tab:: Answer

        .. activecode:: mucp_7_1_ac_a
            :language: cpp
            :compileargs: [ '-Wall', '-Werror' ]

            Below is one way to write the program using the word 'irritating' as the string. 
            ~~~~
            #include <iostream>
            #include <string>
            using namespace std;

            int main() {
                string word = "irritating";
                cout << word[3] << endl;
                while (word.find('i') != string::npos) {
                    word[word.find('i')] = 'e';
                }
                cout << word << endl;
            }


.. tabbed:: mucp_7_2_ac

    .. tab:: Question

        .. activecode:: mucp_7_2_ac_q
            :language: cpp
            :compileargs: [ '-Wall', '-Werror' ]

            An anagram is a play on words by rearranging the letters of the original words
            to form new words. For example, the letters in "listen" can be rearranged to
            make "silent". Write a program that rearranges "night" into "thing" and prints the anagram.          
            ~~~~
            #inlcude <iostream>
            #include <string>
            using namespace std;
            // YOUR CODE HERE


    .. tab:: Answer

        .. activecode:: mucp_7_2_ac_a
            :language: cpp
            :compileargs: [ '-Wall', '-Werror' ]

            Below is one way to write the program.
            ~~~~
            #include <iostream>
            #include <string>
            using namespace std;

            int main() {
                string original = "night";
                string anagram = original;
                anagram[0] = original[original.find('t')];
                anagram[1] = original[original.find('h')];
                anagram[2] = original[original.find('i')];
                anagram[3] = original[original.find('n')];
                anagram[4] = original[original.find('g')];
                cout << anagram;
            }


.. tabbed:: mucp_7_3_ac

    .. tab:: Question

        .. activecode:: mucp_7_3_ac_q
            :language: cpp
            :compileargs: [ '-Wall', '-Werror' ]

            Let's write the function ``longerString``, which takes two parameters, 
            first and second. If first has more letters
            than second, longerString prints "first is longer than second",
            and vice versa. If they have the same number of letters, longerString 
            prints "first and second are the same length".        
            ~~~~
            #include <iostream>
            #include <string>
            using namespace std;
            // YOUR CODE HERE


            // DO NOT MODIFY BELOW THIS LINE
            int main() {
                longerString("longer", "string");
                longerString("string", "second");
            }

    .. tab:: Answer

        .. activecode:: mucp_7_3_ac_a
            :language: cpp
            :compileargs: [ '-Wall', '-Werror' ]

            Below is one way to write the function ``longerString``.
            ~~~~
            #include <iostream>
            #include <string>
            using namespace std;

            void longerString (string first, string second) {
                if (first.length() > second.length()) {
                    cout << first << " is longer than " << second << endl;
                }
                else if (first.length() < second.length()) {
                    cout << second << " is longer than " << first << endl;
                }
                else {
                    cout << first << " and " << second << " are the same length" << endl;
                }
            }

            int main() {
                longerString("longer", "string");
                longerString("string", "second");
            }


.. tabbed:: mucp_7_4_ac

    .. tab:: Question

        .. activecode:: mucp_7_4_ac_q
            :language: cpp
            :compileargs: [ '-Wall', '-Werror' ]

            Let's write the code for the ``cipherText`` function. cipherText 
            should be a void function that takes the string input as a parameter,
            increases the value of each character by 1 (i.e. "bad" turns into "cbe"),
            and prints the encrypted string.            
            ~~~~
            #include <iostream>
            #include <string>
            using namespace std;
            // YOUR CODE HERE


            // DO NOT MODIFY BELOW THIS LINE
            int main() {
                cipherText("bad");
            }

    .. tab:: Answer

        .. activecode:: mucp_7_4_ac_a
            :language: cpp
            :compileargs: [ '-Wall', '-Werror' ]

            Below is one way to write the function ``cipherText``.
            ~~~~
            #include <iostream>
            #include <string>
            using namespace std;

            void cipherText (string input) {
                size_t i = 0;
                while (i < input.length()) {
                    input[i] = input[i] + 1;
                    i++;
                }
                cout << input;
            }

            int main() {
                cipherText("bad");
            }


.. tabbed:: mucp_7_5_ac

    .. tab:: Question

        .. activecode:: mucp_7_5_ac_q
            :language: cpp
            :compileargs: [ '-Wall', '-Werror' ]

            Write a program that prints out the number of occurences of the character 't'
            in the string tongue_twister, with declaration in the order of ``tongue_twister``, ``count``, and ``i``.
            Declare the string tongue_twister as 'twelve twins twirled twelve twigs.'         
            ~~~~
            #include <iostream>
            #include <string>
            using namespace std;
            // YOUR CODE HERE


    .. tab:: Answer

        .. activecode:: mucp_7_5_ac_a
            :language: cpp
            :compileargs: [ '-Wall', '-Werror' ]

            Below is one way to write the program.
            ~~~~
            #include <iostream>
            #include <string>
            using namespace std;

            int main() {
                string tongue_twister = "twelve twins twirled twelve twigs";
                int count = 0;
                size_t i = 0;
                while (i < (int)tongue_twister.length()) {
                    if (tongue_twister[i] == 't') {
                        count++;
                    }
                    i++;
                }
                cout << count;
            }


.. tabbed:: mucp_7_6_ac

    .. tab:: Question

        .. activecode:: mucp_7_6_ac_q
            :language: cpp
            :compileargs: [ '-Wall', '-Werror' ]

            Write a program that prints out the index of the second instance of the 
            character 'i'. Use ``string quote = "Your time is limited, so don't waste it living someone else's life.``
            ~~~~
            #include <iostream>
            #include <string>
            using namespace std;
            // YOUR CODE HERE


    .. tab:: Answer

        .. activecode:: mucp_7_6_ac_a
            :language: cpp
            :compileargs: [ '-Wall', '-Werror' ]

            Below is one way to write the program.
            ~~~~
            #include <iostream>
            #include <string>
            using namespace std;

            int main() {
                string quote = "Your time is limited, so don't waste it living someone else's life.";
                size_t first = quote.find("i");
                int index = quote.find('i', first + 1);
                cout << index;
            }

                   
.. tabbed:: mucp_7_7_ac

    .. tab:: Question

        .. activecode:: mucp_7_7_ac_q
            :language: cpp
            :compileargs: [ '-Wall', '-Werror' ]

            Deep in the forest live the 7 dwarves named Sorty, Torty, Vorty,
            Worty, Xorty, Yorty, and Zorty. Write a program that prints
            out each of their names.
            ~~~~
            #include <iostream> 
            #include <string>
            using namespace std;
            // YOUR CODE HERE


    .. tab:: Answer

        .. activecode:: mucp_7_7_ac_a
            :language: cpp
            :compileargs: [ '-Wall', '-Werror' ]
            
            Below is one way to write the program.
            ~~~~
            #include <iostream>
            #include <string>
            using namespace std;

            int main() {
                string suffix = "orty";
                char letter = 'S';
                while (letter <= 'Z') {
                    if (letter != 'U') {
                        cout << letter + suffix << endl;
                    }
                    letter++;
                }
            }


.. tabbed:: mucp_7_8_ac

    .. tab:: Question

        .. activecode:: mucp_7_8_ac_q
            :language: cpp
            :compileargs: [ '-Wall', '-Werror' ]

            On the strange planet of Noes, there's a law that prohibits the usage of the letter "e". 
            As a result, they hired you to write a function called ``censorE`` that replaces all occurences
            of the letter "e" in a string with an asterisk and returns the censored string. For example, 
            if the input is "hello world", the function returns "h*llo world".
            ~~~~
            #include <iostream>
            #include <string>
            using namespace std;
            // YOUR CODE HERE


            ==== 
            #define DOCTEST_CONFIG_IMPLEMENT_WITH_MAIN
            #include "doctest.h"

            TEST_CASE("censorE function") {
                CHECK_EQ(censorE("after"), "aft*r");
                CHECK_EQ(censorE("hello world"), "h*llo world");
                CHECK_EQ(censorE("censor"), "c*nsor");
            }

    .. tab:: Answer

        .. activecode:: mucp_7_8_ac_a
            :language: cpp
            :compileargs: [ '-Wall', '-Werror' ]

            Below is one way to write the censorE function.
            ~~~~
            #include <iostream>
            #include <string>
            using namespace std;

            string censorE (string input) {
                size_t i = 0;
                while ((unsigned)i < input.length()) {
                    if (input[i] == 'e') {
                        input[i] = '*';
                    }
                    i++;
                }
                return input;
            }

            ==== 
            #define DOCTEST_CONFIG_IMPLEMENT_WITH_MAIN
            #include "doctest.h"

            TEST_CASE("censorE function") {
                CHECK_EQ(censorE("after"), "aft*r");
                CHECK_EQ(censorE("hello world"), "h*llo world");
                CHECK_EQ(censorE("censor"), "c*nsor");
            }

.. tabbed:: mucp_7_9_ac

    .. tab:: Question

        .. activecode:: mucp_7_9_ac_q
            :language: cpp
            :compileargs: [ '-Wall', '-Werror' ]

            Your work for the planet of Noes impressed the nearby planets of Noas, Nois, Noos, and Nous.
            They want you to write different functions that censor out each planet's corresponding forbidden letter.
            However, your galaxy brain knows better than to write a different function for each planet.
            Using generalization, write the function ``censorLetter`` which takes input and a char to censor 
            as parameters and returns a censored string. For example, censorLetter("Bye world", 'o') returns the
            string "Bye w*rld".
            ~~~~
            #include <iostream> 
            #include <string>
            using namespace std;
            // YOUR CODE HERE


            ====
            #define DOCTEST_CONFIG_IMPLEMENT_WITH_MAIN
            #include "doctest.h"

            TEST_CASE("censorLetter function") {
                CHECK_EQ(censorLetter("Bye world", 'o'), "Bye w*rld");
                CHECK_EQ(censorLetter("Hello world", 'l'), "He**o wor*d");
                CHECK_EQ(censorLetter("Goodbye world", 'd'), "Goo*bye worl*");
            }

    .. tab:: Answer

        .. activecode:: mucp_7_9_ac_a
            :language: cpp
            :compileargs: [ '-Wall', '-Werror' ]

            Below is one way to write the censorLetter function.
            ~~~~
            #include <iostream>
            #include <string>
            using namespace std;
            
            string censorLetter (string input, char letter) {
                size_t i = 0;
                while (i < input.length()) {
                    if (input[i] == letter) {
                        input[i] = '*';
                    }
                    i++;
                }
                return input;
            }

            ====
            #define DOCTEST_CONFIG_IMPLEMENT_WITH_MAIN
            #include "doctest.h"

            TEST_CASE("censorLetter function") {
                CHECK_EQ(censorLetter("Bye world", 'o'), "Bye w*rld");
                CHECK_EQ(censorLetter("Hello world", 'l'), "He**o wor*d");
                CHECK_EQ(censorLetter("Goodbye world", 'd'), "Goo*bye worl*");
            }


.. tabbed:: mucp_7_10_ac

    .. tab:: Question

        .. activecode:: mucp_7_10_ac_q
            :language: cpp
            :compileargs: [ '-Wall', '-Werror' ]

            Let's write a function called ``alphaCombine`` which takes
            two strings, first and second,
            and returns a string which concatenates first and second in
            alphabetical order. For example,
            alphabetizer ("zebra, mega") returns the string
            "megazebra" since "mega" comes before "zebra" in the alphabet.        
            ~~~~
            #include <iostream>
            #include <string>
            using namespace std;
            // YOUR CODE HERE


            ====
            #define DOCTEST_CONFIG_IMPLEMENT_WITH_MAIN
            #include "doctest.h"

            TEST_CASE("alphaCombine function") {
                CHECK_EQ(alphaCombine("zebra","mega"), "megazebra");
                CHECK_EQ(alphaCombine("alpha","combine"), "alphacombine");
                CHECK_EQ(alphaCombine("combine","alpha"), "alphacombine");
            }

    .. tab:: Answer

        .. activecode:: mucp_7_10_ac_a
            :language: cpp
            :compileargs: [ '-Wall', '-Werror' ]

            Below is one way to write the alphaCombine function.
            ~~~~
            #include <iostream>
            #include <string>
            using namespace std;

            string alphaCombine (string first, string second) {
                if (first > second) {
                    return second + first;
                }
                else {
                    return first + second;
                }
            }

            ====
            #define DOCTEST_CONFIG_IMPLEMENT_WITH_MAIN
            #include "doctest.h"

            TEST_CASE("alphaCombine function") {
                CHECK_EQ(alphaCombine("zebra","mega"), "megazebra");
                CHECK_EQ(alphaCombine("alpha","combine"), "alphacombine");
                CHECK_EQ(alphaCombine("combine","alpha"), "alphacombine");
            }

.. tabbed:: mucp_7_11_ac

    .. tab:: Question

        .. activecode:: mucp_7_11_ac_q
            :language: cpp
            :compileargs: [ '-Wall', '-Werror' ]

            Let's write a function called ``ispalindrome`` which takes
            a string named input
            and returns a bool
            The function returns true if the string is a palindrome and false if not.
            palindromes are symmetrical strings.
            That is a string that reads the same backwards is palindrome.
            palindromes:  "hih", "i", "bob", "tenet", "soos", "madam" .
            not palindromes: "join", "hat", "frat", "supper", "rhythm".
            ~~~~
            #include <iostream>
            #include <string>
            using namespace std;
            // YOUR CODE HERE


            ====
            #define DOCTEST_CONFIG_IMPLEMENT_WITH_MAIN
            #include "doctest.h"

            TEST_CASE("ispalindrome function") {
                CHECK(ispalindrome("madam"));
                CHECK_FALSE(ispalindrome("join"));
            }

    .. tab:: Answer

        .. activecode:: mucp_7_11_ac_a
            :language: cpp
            :compileargs: [ '-Wall', '-Werror' ]

            Below is one way to write the ispalindrome function.
            ~~~~
            #include <iostream>
            #include <string>
            using namespace std;

            bool ispalindrome(string input) {
                if (input.length() == 0)
                    return true;
                size_t front = 0;
                size_t back = input.length() - 1;
                while (front < back) {
                    if(input[front] != input[back]) {
                        return false;
                    }
                    front = front + 1;
                    back = back - 1;
                }
                return true;
            }

            ====
            #define DOCTEST_CONFIG_IMPLEMENT_WITH_MAIN
            #include "doctest.h"

            TEST_CASE("ispalindrome function") {
                CHECK(ispalindrome("madam"));
                CHECK_FALSE(ispalindrome("join"));
            }
