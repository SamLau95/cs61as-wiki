While it difficult to predict exactly how much time a function will take to run because of differences in processor speeds and other factors, it is still possible to characterize functions by their orders of growth, a measurement of how a function's resource usage grows given differently sized inputs. In nearly all cases of orders of growth, we use a function's asymptotic behavior, or how a function behaves given large inputs. Orders of growth are typically used to characterize an algorithm's running time and memory usage.

One way to specify an algorithm's order of growth is if beyond a certain input size $n$, the function $f(n)$ times a positive constant provides an upper bound or limit for the resource consumed for that algorithm. In other words, for a large value of $n$ and a constant $c$, the resources consumed of that algorithm will never be larger than $c × f(n)$. This concept is expressed using [Big O notation](wiki:big-o-notation). 

For example, for

    (define (factorial n)
      (if (= n 1)
          1
          (* n (factorial (- n 1)))))

since the run-time of the above function grows linearly as its input size increases, the run-time of `factorial` can be said to be of order $O(n)$. Also note that `factorial` uses memory $O(n)$ because it is [linear recursive](http://mitpress.mit.edu/sicp/full-text/book/book-Z-H-11.html#%_sec_1.2.1).

The [most common notations](http://en.wikipedia.org/wiki/Big_O_notation#Family_of_Bachmann.E2.80.93Landau_notations) of specifying orders of growth include: 

- Big Omega notation, which specifies a lower bound
- Theta notation, which specifies both a lower and an upper bound
- Big O notation, which specifies an upper bound and is most widely used.