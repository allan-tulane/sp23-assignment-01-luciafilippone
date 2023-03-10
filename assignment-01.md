

# CMPS 2200 Assignment 1

**Name:**_________________________


In this assignment, you will learn more about asymptotic notation, parallelism, functional languages, and algorithmic cost models. As in the recitation, some of your answer will go here and some will go in `main.py`. You are welcome to edit this `assignment-01.md` file directly, or print and fill in by hand. If you do the latter, please scan to a file `assignment-01.pdf` and push to your github repository. 
  
  

1. (2 pts ea) **Asymptotic notation** (12 pts)

  - 1a. Is $2^{n+1} \in O(2^n)$? Why or why not? 
.  To prove this there needs to exist constants c and n0 such that 2^(n+1) <= c*2n
.  for all n > n0. Simplify to 2*2^n <= c*2n. Divide both sides by 2^n to get 2 <= 
.  c * 2^(n-1) for all n >= n0. So yes 2^(n+1) is in 0(2^n) where c >= 2.
.  
. 
  - 1b. Is $2^{2^n} \in O(2^n)$? Why or why not?     
.  See if there exists constant c and n0 such that 2^2^n <= c*2^n for all n >= n0.
.  Simplify the equation to 4^n <= c * ^n. Divid both sides by 2^n and get 2^n^n
.  <= c for all n > n0. However the left side grows much faster than the right so 
.  theres no constant c to satisfy the inequality for all n. therefor 2^n^n is not
.  in O(2^n)
  - 1c. Is $n^{1.01} \in O(\mathrm{log}^2 n)$?    
.  Show there exists constnats c and n0 such that n^1.01 < c * log2n for all n >= n0
.  Taking the logarithm of both sides its log2(n^1.01) <= log2(c*log2n) which 
.  simplofoes to 1.01 * log2n <= log2c + log2log2n. The left side grows much faster 
.  than the right. Therefore there is no constant c that can satisfy the inequality for all n so n^1.01 is not in O(log2n).

  - 1d. Is $n^{1.01} \in \Omega(\mathrm{log}^2 n)$?  
.  To prove this there needs to exist constants c and n0 such that n^1.01 >= c *
.  log2n for all n > n0. For the same reasons above the equations simplify to 
.  1.01 * log2n >= log2c + log2log2n. Since the right hand grows much faster than the 
.  right side the inequality is satisfied for all n so n^1.01 is in Omega(log2n)
  - 1e. Is $\sqrt{n} \in O((\mathrm{log} n)^3)$?  
.  Is ???n ??? O((logn)3)?
.  No sqrt(n) is not in 0((
.  
.  
  - 1f. Is $\sqrt{n} \in \Omega((\mathrm{log} n)^3)$?  
.  


2. **SPARC to Python** (12 pts)

Consider the following SPARC code of the Fibonacci sequence, which is the series of numbers where each number is the sum of the two preceding numbers. For example, 0, 1, 1, 2, 3, 5, 8, 13, 21, 34, 55, 89, 144, 233, 377, 610 ... 
$$
\begin{array}{l}
\mathit{foo}~x =   \\
~~~~\texttt{if}{}~~x \le 1~~\texttt{then}{}\\
~~~~~~~~x\\   
~~~~\texttt{else}\\
~~~~~~~~\texttt{let}{}~~(ra, rb) = (\mathit{foo}~(x-1))~~,~~(\mathit{foo}~(x-2))~~\texttt{in}{}\\  
~~~~~~~~~~~~ra + rb\\  
~~~~~~~~\texttt{end}{}.\\
\end{array}
$$ 

  - 2a. (6 pts) Translate this to Python code -- fill in the `def foo` method in `main.py`  

  - 2b. (6 pts) What does this function do, in your own words?  

.  
.  
.  
.  
.  
.  
.  
.  
  

3. **Parallelism and recursion** (26 pts)

Consider the following function:  

```python
def longest_run(myarray, key)
   """
    Input:
      `myarray`: a list of ints
      `key`: an int
    Return:
      the longest continuous sequence of `key` in `myarray`
   """
```
E.g., `longest_run([2,12,12,8,12,12,12,0,12,1], 12) == 3`  
 
  - 3a. (7 pts) First, implement an iterative, sequential version of `longest_run` in `main.py`.  

  - 3b. (4 pts) What is the Work and Span of this implementation?  

.  
.  
.  
.  
.  
.  
.  
.  
.  


  - 3c. (7 pts) Next, implement a `longest_run_recursive`, a recursive, divide and conquer implementation. This is analogous to our implementation of `sum_list_recursive`. To do so, you will need to think about how to combine partial solutions from each recursive call. Make use of the provided class `Result`.   

  - 3d. (4 pts) What is the Work and Span of this sequential algorithm?  
.  
.  
.  
.  
.  
.  
.  
.  
.  
.  
.  


  - 3e. (4 pts) Assume that we parallelize in a similar way we did with `sum_list_recursive`. That is, each recursive call spawns a new thread. What is the Work and Span of this algorithm?  

.  
.  
.  
.  
.  
.  
.  
.  

