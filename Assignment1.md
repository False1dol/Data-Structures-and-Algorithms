SER 501
Assignment 1

  
  
![alt text](https://github.com/MrReese0/SER501-AdvDSA/blob/master/images/A1Q1.png)  
  
  
Ans.
  
  
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
  
![alt text](https://github.com/MrReese0/SER501-AdvDSA/blob/master/images/A1Q2P1.png)  
![alt text](https://github.com/MrReese0/SER501-AdvDSA/blob/master/images/A1Q2P2.png)  
  
  
Ans. 
>
>
>
  
![alt text](https://github.com/MrReese0/SER501-AdvDSA/blob/master/images/A1Q2P3.png)  
  
  
Ans. 
  
  
>   f(n) = 1 + 2 + 4 + … + 2<sup>n</sup>  
>
>   This is an infinite geometric progression, and the summation is:  
>
>   f(n) = <sup>i = n</sup>∑<sub>i = 0</sub>   2<sup>i</sup>  
>
>   Therefore, f(n) = 1(2<sup>n+1</sup> -1) / (2 - 1) = 2<sup>n+1</sup> - 1  
>
>   If we consider       g(n) = 2<sup>n</sup>  
>                   Then f(n) <= c.g(n), c > 0 (ignoring the -1, f(n) = 2<sup>n+1</sup>, i.e., f(n) = 2.2<sup>n</sup> and c = 3)  
>   So by definition,    f(n)  = O(g(n))  
>                        f(n)   = O(2<sup>n</sup>)  
  
    
![alt text](https://github.com/MrReese0/SER501-AdvDSA/blob/master/images/A1Q3.png)  
  
    
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
  
  
![alt text](https://github.com/MrReese0/SER501-AdvDSA/blob/master/images/A1Q4.png)  


Ans
  
>   ![alt text](https://github.com/MrReese0/SER501-AdvDSA/blob/master/images/Tree.png)  
>   The height of the tree is (lg n), each level adds up to (2<sup>i</sup>n + 2<sup>1-i</sup>) and there are 4<sup>lg n</sup> = n<sup>2</sup>  
>   leaves. We get  
>   T(n) = <sup>lg(n-1)</sup>∑<sup>i=0</sup> (2<sup>i</sup>n + 2<sup>1-i</sup>) + Θ(n<sup>2</sup>)  
>        = <sup>lg(n-1)</sup>∑<sup>i=0</sup> 2<sup>i</sup>n + <sup>lg(n-1)</sup>∑<sup>i=0</sup> 2<sup>1-i</sup> + Θ(n<sup>2</sup>)  
>        = (2<sup>lgn</sup>-1)/(2-1) + 2. <sup>lg(n-1)</sup>∑<sup>i=0</sup>(½)<sup>i</sup> + Θ(n<sup>2</sup>)  
>       <= n -1 + 2. <sup>∞</sup>∑<sup>i=0</sup>(½)<sup>i</sup> + Θ(n<sup>2</sup>)  
>        = n - 1 + 2. ( 1/ (1 - (½)) ) + Θ(n<sup>2</sup>)  
>        = Θ(n<sup>2</sup>) + n + 3  
>        = Θ(n<sup>2</sup>)  
>
>	
>   Using substitution method, we guess: T(n) <= cn<sup>2</sup> + 2n:  
>      T(n) <= 4c(n/2)<sup>2</sup> + 2n/2 + n  
>           <= cn<sup>2</sup> + 2n  
>            = Θ(n<sup>2</sup>)  
  
  
![alt text](https://github.com/MrReese0/SER501-AdvDSA/blob/master/images/A1Q5.png)  
  
    
Ans. 
  
  
>   There are two steps in this recursive sorting algorithm:  
>
>   1. Sort the sub-array A[1..n−1]  
>   2. Insert A[n] into the sorted subarray from step 1 in proper position  
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
  
  
![alt text](https://github.com/MrReese0/SER501-AdvDSA/blob/master/images/A1Q6P1.png)  
  
  
Ans 6 (a)  
  
>   a = 2, b = 2, f(n) = n<sup>4</sup>  
>   n<sup>log<sub>b</sub> a</sup> = n<sup>1</sup>  
>   Case 3: f(n) = ꭥ (n<sup>1 + 3</sup>) for 𝞮 = 3  
>   And 2(cn/2)<sup>4</sup> <= cn<sup>4</sup> for c < 1/2  
>   Therefore, T(n) = Θ(n<sup>4</sup>)  
  
Ans 6 (b)	 
  
>   a = 1, b = 10/7, f(n) = n  
>   n<sup>log<sub>b</sub> a</sup> = n<sup>0</sup>  
>   Therefore, T(n) = Θ(n)  
  
Ans 6 (c) 	
  
>   a = 16, b = 4, f(n) = n<sup>2</sup>  
>   n<sup>log<sub>b</sub> a</sup> = n<sup>2</sup>  
>   Case 2: f(n) = Θ(n<sup>2</sup>)  
>   Therefore, T(n) = Θ(n<sup>2</sup>lgn)  
  
Ans 6 (d)	
  
>   a = 2, b = 4, f(n) = n<sup>1/2</sup>  
>   n<sup>log<sub>b</sub> a</sup> = n<sup>1/2</sup>  
>   Case 2: f(n) = Θ(n<sup>1/2</sup>)  
>   Therefore, T(n) = Θ(n<sup>1/2</sup>lgn)  
  
Ans 6 (e)	
  
>   a = 2<sup>1/2</sup>, b = 2, f(n) = lgn  
>   n<sup>log<sub>b</sub> a</sup> = n<sup>1/2</sup>  
>   Now, n<sup>1/2</sup> grows faster than f(n) = lgn  
>   Therefore, by case (1), T(n) = Θ(n<sup>1/2</sup>)  
  
Ans 6 (f)	
  
>   a = 64, b = 8, f(n) = -n<sup>2</sup>lgn  
>   Under Master theorem's conditions, f(n) has to be a positive value. Hence, it’s not applicable here.  
  
Ans 6 (g)	
  
>   a = 2, b = 4, f(n) = n<sup>0.51</sup>  
>   n<sup>log<sub>b</sub> a</sup> = n<sup>1/2</sup> = n<sup>0.5</sup>  
>   Case 3: f(n) ꭥ (n<sup>0.5 + 0.01</sup>), for 𝞮 = 0.01  
>   And 2(cn/4)<sup>0.51</sup> <= cn<sup>0.51</sup> for c < (2 * (¼)<sup>0.51</sup>)<sup>1/0.49</sup>  
>   Therefore, T(n) = Θ(n<sup>0.51</sup>)  
  
  
![alt text](https://github.com/MrReese0/SER501-AdvDSA/blob/master/images/A1Q6P2.png)  
  
  
Ans 6 (h)	
  
>   a = 16, b = 4, f(n) = n!  
>   n<sup>log<sub>b</sub> a</sup> = n<sup>2</sup>  
>   Now, n! grows faster than n<sup>2</sup>,  
>   Therefore, by case (3), T(n) = Θ(n!)  
  
Ans 6 (i)	
  
>   a = ½, b = 2, f(n) = ½  
>   Under Master theorem's conditions, a always has to be > 1. Hence, it’s not applicable here.  
  
Ans 6 (j)	

>   a = 2<sup>n</sup>, b = 2, f(n) = n<sup>n</sup>  
>   Under Master theorem's conditions, a has to be a constant. Hence, it’s not applicable here.  

