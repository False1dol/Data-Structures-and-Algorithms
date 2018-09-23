SER 501
Assignment 1




Ans. <sup TEST </sup>

	Base case : (n = 2)

		=> T(2) = 2 and 2 log 2 = 2

		Thus, T(2) = 2 log 2


	Assume T(n) = n log n is true if n = 2k for some integer k > 0

	
	Induction Step:

		If n = 2k+1, then

		T(2k+1)

		= 2T(2k+1 / 2) + 2k+1 

		= 2T(2k ) + 2k+1 

		= 2(2k log 2k) + 2k+1

		= 2k+1(log 2k + 1)

		= 2k+1 log 2k+1
		
	Hence proved by induction.




Ans.



Ans.
	f(n) = 1 + 2 + 4 + … + 2n

	This is an infinite geometric progression, and the summation is:

	f(n) = ∑i = 0i = n  2i

	Therefore, f(n) = 1(2n+1 -1) / (2 - 1) = 2n+1 - 1
	
	If we consider g(n) = 2n
	Then f(n) <= c.g(n), c > 0 (ignoring the -1, f(n) = 2n+1, i.e., f(n) = 2.2n and c = 3)
	So by definition,    f(n)  = O(g(n))
	         f(n)   = O(2n)





Ans.
(1) 
Considering 999 = 103-1, we find that for k digits in base b we can express numbers up to bk −1.

N = bk - 1
log b (N + 1) = k

Or, k = log b (N)
Now, log b N = (log a N)/(log a b)
 
So the size of integer N in base a is the same as its size in base b, times a constant factor log a b. 

In big-O notation, the base is irrelevant, therefore, it is O(log N).

(2)
	While n > 1:
		Print “hello”   ----------------- O (1)
		N := n/2        ----------------- O (lg (n))
	F(n) = n (O(1) + O(lg (n))
	        = O(n lg(n))


Ans.

The height of the tree is (lg n), each level adds up to (2in + 21-i) and there are 4lg n = n2 
leaves. We get

	
Using substitution method, we guess: T(n) <= cn2 + 2n:

	T(n) <= 4c(n/2)2 + 2n/2 + n
	        <= cn2 + 2n
	          = Θ(n2)




Ans.
	There are two steps in this recursive sorting algorithm:

Sort the sub-array A[1..n−1]
Insert A[n] into the sorted subarray from step 1 in proper position

For n=1, step 1 doesn’t take any time as the sub-array is an empty array and step 2 takes constant time, i.e. the algorithm runs in Θ(1) time.

For n>1, step 1 again calls for the recursion for n−1 and step 2 runs in Θ(n) time.

So, we can write the recurrence as:

T(n) = {  Θ(1)               , if n = 1
              	  T(n−1) + Θ(n), if n > 1

Let us assume that for n=1, T(n) = c1, where c1 is some constant. 
And on average for n > 1, inserting an element in its proper position in a sorted array requires shifting half of the elements, i.e. c2n/2+c3 time (c2n/2 for shifting the elements and c3 for inserting the element).

So, we can rewrite the recurrence as:

T(n) = {          c1                        , if n = 1
 T(n−1) + c2(n−1)/2 + c3, if n > 1

So for any general n > 1,

T(n) = T(n−1) + c2(n−1)/2 + c3
= T(n−2) + c2(n−2)/2 + c3 + {c2(n−1)/2 + c3}
= T(1) + ⋅⋅⋅ + {c2(n−2)/2 + c3} + {c2(n−1)/2 + c3}
= c1 + c2/2⋅{1+2+⋅⋅⋅+(n−1)} + c3(n−1)
= c1 + c2/2⋅n(n−1)/2 + c3(n−1)
= Θ(n2)



Ans.


