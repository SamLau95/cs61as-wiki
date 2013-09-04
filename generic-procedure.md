A generic procedure is a [procedure](wiki:procedure) that can operate on data that may be represented in more than one way. 

For example, suppose I want to define an operation `add` which adds two numbers together and `sub` which subtracts one number from another. However, I have three types of numbers: regular Scheme integers, rational numbers, and imaginary numbers. I could write a separate procedure for each of them and name each one differently, but if I had many operations and many types of numbers defining all the procedures is tedious and not scalable.

    (define (add-int num1 num2) ...)
    (define (add-rat num1 num2) ...)
    (define (add-imag num1 num2) ...)

    (define (sub-int num1 num2) ...)
    (define (sub-rat num1 num2) ...)
    (define (sub-imag num1 num2) ...)
    ;; Imagine if we had 10 operations and 10 number types - that's 100 procedures!

There are a number of ways we can deal with this proliferation of procedures:

- [Data-Directed Programming](wiki:data-directed-programming) - we attach a label to each object saying what type of object it is, then look up the correct procedure to call through a table.
- [Message Passing](http://mitpress.mit.edu/sicp/full-text/book/book-Z-H-17.html#_sec_Temp_275) - each object is itself a function that dispatches to an internal routine
- [Object Oriented Programming](wiki:object-oriented-progrmaming) - a little more complicated; basically objects themselves are "smart" enough to know to use the correct procedure (see the wiki for more information).

In all of these strategies, the end-goal is to be able to simply call the generic procedures `add` or `sub` on any number and have it work correctly for each representation of a number.