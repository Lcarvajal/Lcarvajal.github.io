---
layout: post
title: Why can IO operator overloads not be written as member functions? (C++)
---
The reason IO operator overloads can’t be written as member functions lies in their binary property. 
This means they need to take two operands in order to perform. 
Let’s look at an example of a simple output statement to better explain this property:

cout  << “Hello ” << “world!”  << “Yay!”;

In this example, the first step a compiler takes in computing this is by first executing

cout << “Hello ”;

Here cout serves as the l-value and “Hello “ serves as the r-value. Hence the binary operation. 
The compiler then stores “Hello “ into the cout and does the operation again with the next operand:

cout << “world! ”;    // where cout contains “Hello ”

then the next

cout << “Yay!”;    // where cout contains “Hello World!”

Finally, we reach a point where cout contains the entire line of code and the program displays:

Hello World! Yay!

Note that cout is of type ostream, so whenever using the << operator, C++ takes an l-value of type ostream and an r-value of whatever type is being displayed (string in the above example). 
If we were to write the << operator as a member function, we would have an object from the created class as the calling object and ostream as the parameter we are passing. 
Using cout  as an r-value. 
This creates a problem, because we have taken away this recursive property of the << operator and so we would not be able to use the object like in the example above. For example:

cout << “Hello ” << <object> << “lalala”;

would not work. Because of this, we write the IO operator overloads as friend functions so that we can have an l-value of type ostream and an r-value of the class type. We also pass the two by reference to hold that recursive property.

