A special form is an [expression](https://edge.edx.org/courses/uc-berkeley/cs61as-1x/SICP/wiki/cs61as-1x/expression/) that follows special [evaluation](https://edge.edx.org/courses/uc-berkeley/cs61as-1x/SICP/wiki/cs61as-1x/expression/) rules. Usually, an expression represents a procedure invocation, so the general rule is that Scheme first evaluates all the subexpressions, and then applies the resulting procedure to the resulting argument values. The specialness of special forms is that Scheme doesn't evaluate all the subexpressions. Instead, each special form has its own particular evaluation rule.

ex: defining a procedure `square`

  (define (square x)
      (* x x))

For example, when we defined `square`, no part of the definition was evaluated: not `square`, not `x`, and not `(* x x)`. It wouldn't make sense to evaluate `(square x)` because you can't invoke the square procedure before you [define](https://edge.edx.org/courses/uc-berkeley/cs61as-1x/SICP/wiki/cs61as-1x/define/) it. The entire special form that starts with `define` is just a completely different kind of thing from a procedure call. In Scheme there is no procedure named `define`. 
