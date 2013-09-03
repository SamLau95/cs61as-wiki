In [Scheme](../scheme/), `and` is a [special form](../special-form/). It checks to see if all its [arguments](../argument/) are true. 

    > (and (> 5 3) (< 2 4))
  #t
    > (and (> 5 3) (< 2 1))
    #f

Subtle point about `and`: It [evaluates](../expression/) its [arguments](../argument/) in order from left to right and stops as soon as it can. It returns `false` as soon as any argument is false. This turns out to be useful in cases like the following:

  (define (divisible? big small)
    (= (remainder big small) 0))

  (define (num-divisible-by-4? x)
    (and (number? x) (divisible? x 4)))

  > (num-divisible-by-4? 16)
  #T

  > (num-divisible-by-4? 6) 
  #F

  > (num-divisible-by-4? 'aardvark)
  #F

  > (divisible? 'aardvark 4)
  ERROR: AARDVARK IS NOT A NUMBER

We want to see if `x` is a number, and, if so, if it's divisible by 4. It would be an error to apply `divisible?` to a nonnumber. If `and` were an ordinary [procedure](../procedure/), the two tests (`number?` and `divisible?`) would both be evaluated before we would have a chance to pay attention to the result of the first one. Instead, if `x` turns out not to be a number, our procedure will return `#f` without trying to divide it by 4.