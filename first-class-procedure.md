[Procedures](wiki:procedure) are said to be first-class if they can be passed around as data.  Specifically, first-class procedures can take other first-class procedures as [arguments](wiki:argument), can be returned by other first-class procedures, and can be assigned to [variables](wiki:variable). All procedures in [Scheme](wiki:scheme) are first class.

Example:

    (define (make-double f)       ; Takes a first-class procedure f as an argument
      (lambda (x) (f (f x))))     ; Returns a first-class procedure
    
    (define 2+ (make-double 1+))  ; Assign a first-class procedure to the 2+ variable
    
    (2+ 5)                        ; Call the new procedure, returns 7