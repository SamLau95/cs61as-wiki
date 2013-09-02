Big O notation relates the running-time of a function to the size of its arguments by providing a relative upper bound on how the running time will increase given large inputs. We say a function $f(n) = O(g(n))$ if and only if $f(n)$ is always less than than or equal to $g(n)$ multiplied by some constant for large values of $n$.

Suppose that we have written a function that given an input of size $n$ takes $2n^2 + n - 3$ steps to complete. For example, if we give our function a list of length $100$, the function will take $20097$ steps to complete. When $n$ becomes large, the function $2n^2 + n - 3$ is always less than or equal to $n^2$ multipled by 3. Therefore, our function is $O(n^2)$ (quadratic time). Notice that as $n$ becomes large, $2n^2$ becomes so much larger than $n - 3$ that we can disregard these smaller terms. Also, since Big O notation accounts for constant factors, we can drop the constant on $2n^2$ and say our function is $O(n^2)$. Since our function is quadratic time, we expect that if our input size doubles our function will take approximately four times as long to complete.

Note that given this definition, both a function that takes $n^2$ steps and a function that takes $100000n^2$ would be considered $O(n^2)$. Because of this, Big O notation is considered a crude measurement of how fast a function will actually run, and it is mostly used to compare running times for a function given different size inputs. Additionally, our function given above is technically also $O(n^3)$ and $O(2^n)$, since both are greater than $n^2$ for large $n$. So that our measure of running time is as accurate as possible, the smallest possible function that still satisfies the specification of the notation is typically given, so we say that our function is $O(n^2)$ rather than $O(n^3)$ or another larger function. 

These are some of the most commonly seen time complexities of functions ordered from smallest to greatest:

- $O(1)$ - constant time, eg. arithmetic operations
- $O(logn)$ - logarithmic time, eg. [binary search](http://en.wikipedia.org/wiki/Binary_search_algorithm)
- $O(n)$ - linear time, eg. printing every element in a list
- $O(nlogn)$ - linearithmic time, eg. [merge sort](http://en.wikipedia.org/wiki/Merge_sort)
- $O(n^2)$ - quadratic time, eg. [insertion sort](http://en.wikipedia.org/wiki/Insertion_sort)
- $O(k^n)$ - exponential time (where k is some other number), eg. [recursive fibonacci](http://mitpress.mit.edu/sicp/full-text/book/book-Z-H-11.html#%_sec_1.2.2)

Big O notation is the most frequently used notation to characterize the running time of programs. For example, from the list above we notice that merge sort and selection accomplish the same task (sorting a list), but merge sort is $O(nlogn)$ whereas selection sort is $O(n^2)$, so we expect merge sort to be significantly faster than selection sort for large lists. 

To read more, go to [Orders of Growth](../orders-growth/).