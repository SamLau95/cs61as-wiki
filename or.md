In [Scheme](wiki:scheme), `or` is a [special form](wiki:special-form). It checks whether any of its [arguments](wiki:argument) are true. 

    > (or (> 5 3) (< 2 1))
    #t
    > (or (> 5 6) (< 2 1))
    #f


Why `or` is a special form: it [evaluates](wiki:expression) its arguments in order from left to right and stops as soon as one of its arguments evaluates to true.

    > (or #f #f #t (/ 1 0))
    #t

A subtle point about `or`: similar to [and](wiki:and), if any one of its arguments evaluate to true (it evaluates to anything besides `#f`), `or` returns the value of the evaluated expression rather than just simply `#t`.

    > (or #f (+ 1 2 3))
    6
    > (or (* 3 4) (- 2 1))
    12

Since all values besides `#f` in Scheme are "truthy", this aspect of `or` still works as if it just returned `#t` while allowing us to make use of the value of its first argument that evaluates to true.