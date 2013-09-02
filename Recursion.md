A technique where a function calls itself with the smaller part of the task. It is the central idea of computer science, but usually considered inefficient compared to [iteration](https://edge.edx.org/courses/uc-berkeley/cs61as-1x/SICP/wiki/cs61as-1x/iteration/). 

ex: 

  (define (recursive-funct x)
      (if (= x 0)
          1
            (+ 1 (recursive-funct (- x 1)))))

Tail-recursion is the optimized version of recursion so that the program is essentially iterative. In tail-recursion, all recursive calls are tail calls and hence do not build up any deferred operations.

ex:

  (define (tail-recursive-funct x)
      (if (= x 0)
          1
            (tail-recursive-funct (- x 1))))
            
See also: [recursion](../recursion)