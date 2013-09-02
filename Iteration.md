In computer science, iteration is the process of repeating a set of instructions a specified number of times or until a specific result is achieved. It is implemented using the special case of recursion, [tail-recursion](https://edge.edx.org/courses/uc-berkeley/cs61as-1x/SICP/wiki/cs61as-1x/recursion/).

ex: definition of factorial function using iteration

  (define (factorial n)
    (fact-iter 1 1 n))

  (define (fact-iter product counter max-count)
    (if (> counter max-count)
        product
        (fact-iter (* counter product)
                   (+ counter 1)
                   max-count)))
