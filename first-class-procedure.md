[Procedures](wiki:procedure) are said to be first-class if they can be passed around as objects or data.  Because of this property, first-class procedures can take other procedures as [arguments](wiki:argument), can be returned by other procedures, and can be assigned to [variables](wiki:variable). All procedures in [Scheme](wiki:scheme) are first class, a key distinction from some other languages that allows for [higher-order procedures](wiki:higher-order-procedure).

Example:

    (define (apply-twice f)          ; Takes a first-class procedure f as an argument
      (lambda (x) (f (f x))))        ; Returns a first-class procedure

    (define 1+ (lambda (x) (+ x 1)))  
    (define 2+ (apply-twice 1+))     ; Assign a first-class procedure to the 2+ variable
    
    (2+ 5)                           ; Call the new procedure, returns 7

To see more examples, go to [Higher-Order Procedures](wiki:higher-order-procedure).