Big O notation relates the running-time of a function to the size of its arguments by providing a relative upper bound on how the running time will increase given large inputs. We say a function $f(n) = O(g(n))$ if and only if $f(n)$ is always less than than or equal to $g(n)$ multiplied by some constant for large values of $n$.

Suppose that we have written a function that given an input of size $n$ takes $2n^2 + n - 3$ steps to complete. When $n$ becomes very large, the $2n^2$ term dominates the $n - 3$ term so when looking at run-time we can just look at the quadratic term. Since big O notation accounts for constant factors, we can drop the coefficient on $2n^2$ and say the function is $O(n^2)$

More information about big O notation:

- A function that takes $\frac{1}{2}n^2$ steps and a function that takes $1000n^2$ steps are both $O(n^2)$. Because of this, big O notation is considered a crude measure of resources consumed by the program.
- The example function in the previous paragraph is also technically $O(n^3)$ and $O(2^n)$, since both are greater than $n^2$ for large $n$. So that our measure of running time is as accurate as possible, the slowest growing function that still satisfies the specification of the notation is typically given, so we say that our function is $O(n^2)$ rather than $O(n^3)$ or another faster growing function.

These are some of the most commonly seen time complexities of functions ordered from smallest to greatest:

- $O(1)$ - constant time, eg. arithmetic operations such as $+$ or $-$
- $O(logn)$ - logarithmic time, eg. [binary search](http://en.wikipedia.org/wiki/Binary_search_algorithm)
- $O(n)$ - linear time, eg. printing every element in a list
- $O(nlogn)$ - linearithmic time, eg. [merge sort](http://en.wikipedia.org/wiki/Merge_sort)
- $O(n^2)$ - quadratic time, eg. [insertion sort](http://en.wikipedia.org/wiki/Insertion_sort)
- $O(k^n)$ - exponential time (where k is some other number), eg. [recursive fibonacci](http://mitpress.mit.edu/sicp/full-text/book/book-Z-H-11.html#%_sec_1.2.2)

Big O notation is the most frequently used notation to characterize the running time of programs. For example, from the list above we notice that merge sort and selection accomplish the same task (sorting a list), but merge sort is $O(nlogn)$ whereas selection sort is $O(n^2)$, so we expect merge sort to be significantly faster than selection sort for large lists. 

To read more, go to [Orders of Growth](../orders-growth/).