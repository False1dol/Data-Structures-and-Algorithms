SER 501
Assignment 1




Ans 1.


>   Base case : (n = 2)
>
>   => T(2) = 2 and 2 log 2 = 2
>
>   Thus, T(2) = 2 log 2
>
>
>
>   Assume T(n) = n log n is true if n = 2<sup>k</sup> for some integer k > 0
>
>
>
>   Induction Step:
>
>
>   If n = 2<sup>k+1</sup>, then
>
>   T(2<sup>k+1</sup>)
>
>   = 2T(2<sup>k+1</sup> / 2) + 2<sup>k+1</sup> 
>
>   = 2T(2<sup>k</sup> ) + 2<sup>k+1 </sup>
>
>   = 2(2<sup>k</sup> log 2<sup>k</sup>) + 2<sup>k+1</sup>
>
>   = 2<sup>k+1</sup>(log 2<sup>k + 1</sup>)
>
>   = 2<sup>k+1</sup> log 2<sup>k+1</sup>
>
>   Hence proved by induction.


Ans 2 Part A.
>
>
>

Ans 2 Part B.


>   f(n) = 1 + 2 + 4 + … + 2<sup>n</sup>
>
>   This is an infinite geometric progression, and the summation is:
>
>   f(n) = ∑ <sub>i = 0</sub> <sup>i = n</sup>  2<sup>i</sup>
>
>   Therefore, f(n) = 1(2<sup>n+1</sup> -1) / (2 - 1) = 2<sup>n+1</sup> - 1
>
>   If we consider       g(n) = 2<sup>n</sup>
>                   Then f(n) <= c.g(n), c > 0 (ignoring the -1, f(n) = 2<sup>n+1</sup>, i.e., f(n) = 2.2<sup>n</sup> and c = 3)
>   So by definition,    f(n)  = O(g(n))
>                        f(n)   = O(2<sup>n</sup>)


Ans 3 Part (1).

>   Considering 999 = 10<sup>3</sup>-1, we find that for k digits in base b we can express numbers up to b<sup>k</sup> −1.
>
>   N = b<sup>k</sup> - 1
>   log <sub>b</sub> (N + 1) = k
>
>   Or, k = log <sub>b</sub> (N)
>   Now, log <sub>b</sub> N = (log <sub>a</sub> N)/(log <sub>a</sub> b)
> 
>   So the size of integer N in base a is the same as its size in base b, times a constant factor log <sub>a</sub> b. 
>
>   In big-O notation, the base is irrelevant, therefore, it is O(log N).

Ans 3 Part (2).

>   While n > 1:
>      Print “hello”   ----------------- O (1)  
>      N := n/2        ----------------- O (lg (n))  
>   F(n) = n (O(1) + O(lg (n))  
>        = O(n lg(n))  


Ans 4.

>   The height of the tree is (lg n), each level adds up to (2in + 21-i) and there are 4lg n = n2 
>   leaves. We get
>
>	
>   Using substitution method, we guess: T(n) <= cn<sup>2</sup> + 2n:
>      T(n) <= 4c(n/2)<sup>2</sup> + 2n/2 + n
>           <= cn<sup>2</sup> + 2n
>            = Θ(n<sup>2</sup>)




Ans 5.

>   There are two steps in this recursive sorting algorithm:
>
>   Sort the sub-array A[1..n−1]
>   Insert A[n] into the sorted subarray from step 1 in proper position
>
>   For n=1, step 1 doesn’t take any time as the sub-array is an empty array and step 2 takes constant time, i.e. the algorithm runs in >   Θ(1) time.
>
>   For n>1, step 1 again calls for the recursion for n−1 and step 2 runs in Θ(n) time.
>
>   So, we can write the recurrence as:
>
>   T(n) = {  Θ(1)         , if n = 1  
>             T(n−1) + Θ(n), if n > 1  
>
>   Let us assume that for n=1, T(n) = c<sub>1</sub>, where c<sub>1</sub> is some constant. 
>   And on average for n > 1, inserting an element in its proper position in a sorted array requires shifting half of the elements, i.e. >   c<sub>2</sub>n/2 + c<sub>3</sub> time (c<sub>2</sub>n/2 for shifting the elements and c<sub>3</sub> for inserting the element).
>
>   So, we can rewrite the recurrence as:
>
>   T(n) = {c<sub>1</sub>                                , if n = 1  
>           T(n−1) + c<sub>2</sub>(n−1)/2 + c<sub>3</sub>, if n > 1  
>
>   So for any general n > 1,
>
>   T(n) = T(n−1) + c<sub>2</sub>(n−1)/2 + c<sub>3</sub>
>        = T(n−2) + c<sub>2</sub>(n−2)/2 + c<sub>3</sub> + {c<sub>2</sub>(n−1)/2 + c<sub>3</sub>}
>        = T(1) + ⋅⋅⋅ + {c<sub>2</sub>(n−2)/2 + c<sub>3</sub>} + {c<sub>2</sub>(n−1)/2 + c<sub>3</sub>}
>        = c<sub>1</sub> + c<sub>2</sub>/2⋅{1+2+⋅⋅⋅+(n−1)} + c<sub>3</sub>(n−1)
>        = c<sub>1</sub> + c<sub>2</sub>/2⋅n(n−1)/2 + c<sub>3</sub>(n−1)
>        = Θ(n<sup>2</sup>)



Ans 6.


