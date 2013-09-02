In computer science, iteration is the process of repeating a set of instructions a specified number of times or until a specific result is achieved. Many other languages use loop constructs such as `for` and `while` to create iterative processes. However, because of the lack of looping constructs in Scheme, iteration in Scheme is implemented using [tail-recursion](https://edge.edx.org/courses/uc-berkeley/cs61as-1x/SICP/wiki/cs61as-1x/recursion/).

*Definition of factorial function using iteration*

    (define (factorial n)
      (fact-iter 1 1 n))

    (define (fact-iter product counter max-count)
      (if (> counter max-count)
          product
          (fact-iter (* counter product)
                     (+ counter 1)
                     max-count)))

Note that in this iterative process recursion is still used. SICP thus uses the terms "iterative process" and "recursive process" to describe the two different processes; both are recursive procedures. Iterative processes in Scheme are characterized by having their state completely self-contained within the procedure arguments - in this example, `product`, `counter`, and `max-count` describe the state in each iteration. 

Whereas iterative processes are often more memory-efficient than recursive processes, they are sometimes more challenging to write because mathematical recurrence relations are more easily translated into recursive processes. 