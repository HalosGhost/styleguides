Variable Declaration
--------------------
When declaring a variable, the name should be separate from the data type.
Furthermore, variable names should be representative of what they are (avoid cryptic names); they should also remain all lowercase, with words separated by an ``_``.
Next, pointer dereferencing should be separated from both the data type and the name.
If declared with an initializer, the initializer should be separated from the equals sign, just as the name is.
Below is an example of a good variable declaration::
   char * variable_name = "data";

Variable (Re)Definition and Usage
---------------------------------
If a variable was declared with no initializer and it is now being defined, or it is being redefined, its assigned value should still be separated from the equals sign.
However, pointer dereferencing and referencing both are attached to the name.
Having the pointer (de)reference attached to the name is the same for usage.
Below is an example of a good variable definition and a good variable usage::
   *variable_name = "new data";

   if ( *variable_name )

Casting
-------
A variable is cast in a very similar style to how it is declared.
The data type, (pointer reference if applicable) and space are simply surrounded by parentheses.
Below is an example of good casting::
   (char * )casted_variable;

*Note that there is a space between the last piece of the cast and the close parenthesis, but no space between the close parenthesis and the variable name.*

Function Declaration
--------------------
Similar to variable declarations, function names should be representative and lower_case.
Also similar, data types should be separated from the function name.
The declarative argument list should be separated from the function name, and each item in the list should be separated by a comma, and a space.
When creating functions with generic names, prefix their names with an '_' (or with a module name, e.g., ``module_``).
Below is an example of a good function declaration with an argument list::
   char * _generic_function (int first_argument, char * second_argument);

*Note that each argument is formatted as if it were a regular variable declaration*

Indentation and Bracing
-----------------------
When defining a function, all the same guidelines for function declaration apply.
However, rather than ending the line with a ';', the argument list's close parenthesis ends the line.
On the following line, the function's opening brace is placed at the same indent level as the function name, and then (without a line-break) follows the first line of the function indented.
A standard indentation shall be four digits (this means that a function's first line will be spaced three times from the opening brace).
The function's closing brace will be left to a newline at the same indentation level as the opening brace and function name.
Below is an example of a good function definition showing good indentation and bracing style::
   char * _generic_function (int first_argument, char * second_argument) {
       first_argument = 1;
       second_argument = "some data";
       return second_argument;
   }

Also note that *all* indentations should be spaces (not tabs).
This indentation style can be easily achieved in vim using the following modesetting line which should be the last line of the source file::
   // vim:set ts=4 sw=4 et:

Calling Functions
-----------------
When calling a function, the function's argument list should be attached to the name.
All other guidelines from the function declaration and definition sections apply.
Below is an example of a good function call::
   _generic_function(7, "data");

Conditions
----------
Conditional blocks should always be spaced from the function and the opening parentheses.
In a for loop, each piece of the conditional block should be spaced from one another.
Below are a few examples of good conditional block formatting::
   while ( n < 7 ) {

   for ( i = 0; i < 34; i ++ ) {

   if ( a == b ) {

*Note that the opening brace of each of these (should they have multiple lines of conditional execution) will follow the Indentation and Bracing guidelines.*
An if...else if...else block will look like the following::
   if ( a > 0 ) {
       _run_function();
       exit(1);
   } else if ( a == 0 ) {
       _some_other_function();
       exit(2);
   } else {
       printf("panic!\n");
       exit(3);
   }

Where applicable, if there are more than three cases (if it would require more than a single ``else if``), use of the ``switch`` function is preferred.

Operators
---------
In general, operators should be separated from operands.
The only exception to this rule are the unary negation operators (both logical, ``!``, and numeric, ``-``), and the unary positive operator (``+``)::
   a = b;
   a == b;
   b = !a;
   c = -1;
   c = +1;
   c ++;

Section Labeling
----------------
It is often desirable to label various sections of the source document with comments.
When doing so, one should pick a consistent style of headings and sub-headings.
I prefer to use the following style::
   // Section //

   /* Subsection */

   /+ Subsubsection +/

Some basic section headings to contemplate using are "Libraries", "Forward Declarations", "Main Function", "Function Definitions", etc.

Comments
--------
All comment texts should be spaced from the comment opening.
Multi-line comments should be delineated with a preceding '*' for each new line.
After the final line of text in a multi-line comment, add another new-line with a comment closing.
Below is an example of good commenting::
   foo * bar = "something"; // a comment
   
   /** 
    * Here is an example
    * of a multi-line
    * comment
    */

Disclaimer
----------
Personally, I find the above guidelines to create source documents that are incredibly well formatted and easy to read.
They reflect experience and conclusions made from working with other styles.
