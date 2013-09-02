An algorithm can be said to exhibit a growth rate on the order of a mathematical function if beyond a certain input size n, the function f(n) times a positive constant provides an upper bound or limit for the run-time of that algorithm. In other words, for a given input size n greater than some n and a constant c, the running time of that algorithm will never be larger than c × f(n). This concept is frequently expressed using [Big O notation](https://edge.edx.org/courses/uc-berkeley/cs61as-1x/SICP/wiki/cs61as-1x/big-o-notation/). 

For example, 

  (define (recursive-funct x)
      (if (= x 0)
          1
            (+ 1 (recursive-funct (- x 1)))))

since the run-time of the above function grows linearly as its input size increases, `recursive-funct` can be said to be of order O(n).
