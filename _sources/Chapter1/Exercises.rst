Multiple Choice Exercises
-------------------------

Answer the following **Multiple Choice** questions to
assess what you have learned in this chapter.


.. mchoice:: programming_1

    What is a **program** in computer science?

    -   a planned series of events, a schedule

        -   This is a definition of a program, just not in the computer science sense.

    -   a translated language that is easy for the computer to understand

        -   This is actually called a low-level language!

    -   a sequence of instructions that specifies how to perform a computation

        +   You can write these instructions to accomplish pretty much anything 
            you want!

    -   a general process for solving a category of problems

        -   This is actually called an algorithm!


.. mchoice:: programming_2

    What is the function of the compiler?

    -   It loads the program from its saved location and makes the computer execute it.

        -   This is the function of an executor.  If you use a compiler, you must also
            use an executer to run your code.

    -   It reads a high-level program and translates everything at once, before executing
        any of the commands.

        +   If there are any errors in your code, the program will not compile.  It is an
            all-or-nothing process.

    -   It translates the program from the low-level language you coded in to a high-level
        language that the computer can understand.

        -   You, the programmer, write your program in a HIGH-level language.  It is then
            translated to a LOW-level language that the computer can understand.

    -   It translates the program line-by-line, alternately reading lines and carrying 
        out commands.

        -   This is the function of an interpreter.


.. mchoice:: programming_3

    What is the difference between **source code** and **object code**?

    -   Source code can contain simple things like variables and values.  Object code 
        can contain more complex objects like data structures.

        -   Contrary to it's name, object code has nothing to do with creating objects!

    -   Object code can contain simple things like variables and values.  Source code 
        can contain more complex objects like data structures.

        -   Source code and object code both contain variables, values, and data structures.
            They're just written in a different way.

    -   Object code is the code that your program is written in.  Source code is the
        translated version of this code that the computer can understand.

        -   You seem to have things a bit mixed up!

    -   Source code is the code that your program is written in.  Object code is the
        translated version of this code that the computer can understand.

        +   The computer can either use an interpreter or a compiler to make the 
            translation.


.. mchoice:: programming_4

    **Multiple Response**  What are the basic functions that appear in
    every programming language?

    -   math operations

        +   This is how your program can carry out complex calculations!

    -   debugging

        -   Debugging is the process of finding and fixing errors AFTER you 
            have written your program. It's not one of the basic functions
            of a programming language.

    -   input/output from the terminal and saved files

        +   This allows your program to communicate with data either from the user, 
            or from the user's saved files.

    -   testing for conditions

        +   This is why you would consider using conditional statements
            in your program.

    -   repetition

        +   This is why you would consider using a loop in your program.


.. mchoice:: programming_5

    What type of error would the following code cause?  Assume you are
    trying to calculate the volume of a cylinder:

    ::

        int radius = 7;
        int height = 8;
        double volume = 3.14 * radius * height;

    -   syntax error

        -   There is nothing wrong with the structure of this program.

    -   run-time error

        -   There are no errors that will surface at runtime.

    -   semantic error

        +   This is not the correct formula for calculating the volume of a
            cylinder.  This program will go on to calculate the wrong volume
            because it doesn't know any better.

    -   no error

        -   Take a look at the area formula.


.. mchoice:: programming_6

    What type of error would the following generate?  Assume you are
    trying to calculate the volume of a cylinder:

    ::

        int radius = 7;
        int height = 8
        double volume = 3.14 * r * r * height;

    -   syntax error

        +   You are missing a semicolon on the second line, and you are using
            the variable ``r`` without defining it on the third line.  your
            program will not compile.

    -   run-time error

        -   There are no errors that will surface at runtime.

    -   semantic error

        -   Everything looks good with your volume calculations.

    -   no error

        -   Take a closer look at the structure of the code.


.. mchoice:: programming_7

    **Multiple Response**  C++ is a(n) ________.

    -   formal language

        +   all programming languages are formal languages!

    -   natural language

        -   C++ certainly did not evolve naturally!

    -   foreign language

        -   C++ might seem foreign to you, but it's used globally!

    -   high-level language.

        +   C++ must be translated before the computer can understand!

    -   low-level language.

        -   The computer doesn't understand C++ until it gets translated!


.. mchoice:: programming_8

    **Multiple Response** Which of the following is true about writing a program.

    -   The compiler ignores anything after ``//``.

        +   This is called a comment, which you can use to describe your code to
            outsiders who might not understand.

    -   There is no limit the number of statements you can put in ``main``.

        +   You can include as many statements as you want to, but it is good 
            practice to keep the ``main`` as short as possible.

    -   Program execution begins at the first line of code.

        -   Program execution actually begins with ``main`` and then
            happens in order, from top to bottom.

    -   ``main`` is enclosed by squiggly brackets ``{ }``.

        +   The ``main`` program and *all* functions in C++ are enclosed by squiggly brackets.

    -   The end of each statement is marked with a colon ``:``.

        -   Actually, each statement is terminated with a *semi* colon ``;``.


.. mchoice:: programming_9

    **Multiple Response** Which is true about programming languages?

    -   Low-level languages are only used for a few special applications.

        +   Low-level languages take more time to write, and they are much harder to
            understand, so they aren't used often.

    -   Programs written in low-level languages must be translated before they can be run.

        -   Low level languages are already written in a language that your computer
            can understand, so they don't need to be translated!

    -   It's easier to program in a high-level language than a low-level language.

        +   High-level languages take less time to write, they are much easier to
            understand, and they are more likely to be correct!

    -   Computers can only execute programs written in low-level languages.

        +   This is why most programs need to be translated before they can be run!

    -   High-level languages can run on many different kinds of computers without an issue.

        +   This is called portability.


.. mchoice:: programming_10

    You were asked to parse through your program, what should this entail?

    -   You should walk through your program line by line to make sure it's 
        that your code doing what it is supposed to.

        -   This is how you would detect a semantic error. Parsing doesn't involve
            semantic errors.

    -   You should search through your program for syntax errors.

        +   Parsing involves looking at the syntactic structure of your program.

    -   You should translate your program to object code.

        -   This would be quite a chore! Luckily you have an interpreter or a compiler
            to do that for you!

    -   You should run your program and check for run-time errors.

        -   Parsing doesn't involve run-time errors.

.. fillintheblank:: programming_11

    #include <|blank|>
    using namespace |blank|
    int |blank| {
         cout << "Hello, World."<< endl |blank|
         return |blank|;
   }
    
   - :(iostream): Correct!
     :.*: Try again!
   - :(std;): Correct!
     :.*: Try again!
   - :(main): Correct!
     :.*: Try again!
   - :(;): Correct!
     :.*: Try again!
   - :(0): Correct!
     :.*: Try again!
