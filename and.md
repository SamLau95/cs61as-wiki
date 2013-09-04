In [Scheme](../scheme/), `and` is a [special form](wiki:special-form/). It checks whether all its [arguments](wiki:argument) are true. 

    > (and (> 5 3) (< 2 4))
    #t
    > (and (> 5 3) (< 2 1))
    #f

Why `and` is a special form: it [evaluates](wiki:expression) its arguments in order from left to right and stops as soon as it can, returning `#f` as soon as any argument evaluates to false. This turns out to be useful:

    > (define (divisible? big small)
        (= (remainder big small) 0))
    > (define (num-divisible-by-4? x)
        (and (number? x) (divisible? x 4)))
    > (num-divisible-by-4? 16)
    #t
    > (num-divisible-by-4? 6) 
    #f
    > (num-divisible-by-4? 'aardvark)
    #f  ;; and exits before trying to find the remainder of 'aardvark
    > (divisible? 'aardvark 4)
    ERROR: AARDVARK IS NOT A NUMBER

A subtle point about `and`: similar to [or](wiki:or) if all its arguments evaluate to true, instead of simply returning `#t` it will return the value of its last argument.

    > (and #t (+ 3 5))
    8
    > (and (- 2 1) 100)
    100

Since all values besides `#f` in Scheme are "truthy", this aspect of `and` still works as if it just returned `#t` while allowing us to make use of the value of its last argument. 