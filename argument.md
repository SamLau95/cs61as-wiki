An argument is a [value](wiki:value) that you pass to a [procedure](wiki:procedure).

    > (define (foo a b c d) ;; a b c d are foo's parameters
        (+ a b c d))
    > (foo 1 2 3 4) ;; 1 2 3 4 are arguments
    10

In [applicative order](wiki:applicative-order), the arguments are fully evaluated before they are passed into the procedure body.

    > (define (bar a b)
        (* a b))
    > (bar (+ 1 1) (+ 2 2)) ;; the arguments are evaluated to 2 and 4 first
    8                       ;; before they are passed into `bar`

