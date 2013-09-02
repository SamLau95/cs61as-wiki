In computer science, a higher-order procedure is a [procedure](wiki:procedure) that does at least one of the following:

- take one or more procedures as an input
- output a procedure

In Scheme, higher-order procedures are supported because all procedures are first-class (see [first-class procedures](wiki:first-class-procedure)). For example, the built-in procedure `map` takes two arguments: a function and a list, and applies the function to each element in the list.

    > (define (square x) (* x x))
    > (map square '(1 2 3))
    '(1 4 9)

In languages without higher-order procedures, this procedure would be implemented using loops or recursion. However, Scheme's higher-order procedures allow for more elegant and succinct code through code reuse. For example:

    (define li '(1 2 3 4))
    (define (cube x) (* x x x))

    ;; Without higher-order procedures
    (define (cube-list li)
      (if (null? li)
          '()
          (cons (cube (car li)) (cube-list (cdr li)))))
    (cube-list li)  ; Outputs '(1 8 27 64)

    ;; With higher-order procedures
    (define (cube-list2 li) (map cube li))
    (cube-list2 li) ; Outputs '(1 8 27 64)

Also note that if we wanted to do something different to the list elements (eg. raise to the fourth power), without higher-order procedures we would have to define another function and repeat much of the body of `cube-list`, whereas with `map` we just need to map the new function to the list.