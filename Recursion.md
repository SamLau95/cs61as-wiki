See also: [Recursion](../recursion)

A technique where a function calls itself with a smaller part of the task. It is a central idea of computer science, allowing many programs to be written much more succinctly as well as being especially important in functional languages such as Scheme because of the lack of looping constructs such as `for` or `while`. Recursive procedures are characterized by two properties:

- A simple base case
- A set of rules that reduce other cases toward the base case

Using recursion often allows for procedures that closely mirror mathematical recurrence relations. For example, computing the factorial of a number $n$ can be defined as: $n! = n(n - 1)!$. Using this definition and $1! = 1$ we can write:

    (define (factorial n)
      (if (= n 1)
          1
          (* n (factorial (- n 1)))))

Note how this procedure is a direct translation of the mathematical definition.

Tail-recursion is an optimized form of recursion so that the program uses less memory. In the example above, it is clear that in the final statement `(* n (factorial (- n 1)))` the computer must "hold on" to the value of `n` while computing `(factorial (- n 1))`. Because of this, the computer must use memory to keep track of the different values of `n` as the program proceeds. A tail-recursive version of `factorial` (where the computer does not have to use memory keeping track of the value of n) can be written as follows:

    (define (factorial n)
      (fact-iter 1 1 n))

    (define (fact-iter product counter max-count)
      (if (> counter max-count)
          product
          (fact-iter (* counter product)
                     (+ counter 1)
                     max-count)))

Note that in the helper procedure `fact-iter` the current state of the algorithm is completely contained within its arguments, eliminating the need to spend memory keeping track of the previous values of `n`. See [Iteration](wiki:iteration) for more information.