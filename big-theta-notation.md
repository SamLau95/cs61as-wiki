Big Theta notation relates the running-time of a function to the size of its arguments by providing both a lower and an upper bound on how the running time will increase given large inputs. We say a function $f(n) = \Theta(g(n))$ if and only if $f(n)$ is always less than than or equal to $g(n)$ multiplied by some constant and greater than $g(n)$ multiplied by some other constant for large values of $n$ (the asymptotic behavior of $f(n)$).

Mathematically this is represented by writing: $c_1 \cdot g(n) \le f(n) \le c_2 \cdot g(n)$ for some constants $c_1$ and $c_2$ and for large values of $n$; $f(n)$ is sandwiched by $g(n)$. 

Notes about Big Theta notation:

- Because Big Theta notation provides both a lower and upper bound it is considered more exact than other types of [notation](http://en.wikipedia.org/wiki/Big_O_notation#Family_of_Bachmann.E2.80.93Landau_notations), such as [Big O notation](wiki:big-o-notation).
- However, in practice Big O notation is seen more often because it is more lenient (it's sometimes hard to find an exact function for our algorithms) and because Big O notation is more platform independent ([reference](http://stackoverflow.com/a/12338937/2559290)).

To see more, read [Orders of Growth](wiki:orders-growth).