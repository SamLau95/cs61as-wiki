In [Scheme](https://edge.edx.org/courses/uc-berkeley/cs61as-1x/SICP/wiki/cs61as-1x/scheme/), `or` is a [special form](https://edge.edx.org/courses/uc-berkeley/cs61as-1x/SICP/wiki/cs61as-1x/special-form/). It checks to see if any of its [arguments](../argument/) are true. 

    > (or (> 5 3) (< 2 1))
  #t
    > (or (> 5 6) (< 2 1))
    #f


Subtle point about `or`: It [evaluates](https://edge.edx.org/courses/uc-berkeley/cs61as-1x/SICP/wiki/cs61as-1x/expression/) its [arguments](https://edge.edx.org/courses/uc-berkeley/cs61as-1x/SICP/wiki/cs61as-1x/argument/) in order from left to right and stops as soon as it can. It returns `true` as soon as any argument is true. This turns out to be useful because not all of the arguments have to be evaluated. So we save time.