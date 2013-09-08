A boolean is an [expression](wiki:expression) that results in a [value](wiki:value) of either `true` or `false`. Everything that is not `false` evaluates to `true` when put in a boolean context. In [Scheme](wiki:scheme), true is represented by the [constant](wiki:constant) `#t`, and false by `#f`.

  > (< 2 3)
  #t
  > (if 1234
      (+ 1 1)
      (/ 1 0))
  2 ;; Doesn't raise an error because 1234 is considered true