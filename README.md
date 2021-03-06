## rvrv3
## Raj Vansia 
## CSE6242 Hw1
# Get Familiar with R [10 points]
One thing that I observed is that R has a lot of tools built in to handle matrices. This is needed for both data analysis and machine learning. For example, a matrix can easily be created by using the following code. Additionally, matrix transformations and manipulations can easily be done such as matrix multiplication . This makes it easier to work with matrices suitable for data analysis. 

How to create a matrix
```
> z = seq(1,16)
> z
 [1]  1  2  3  4  5  6  7  8  9 10 11 12 13 14 15 16

> x = array(data = z, dim = c(4,4))
> x
     [,1] [,2] [,3] [,4]
[1,]    1    5    9   13
[2,]    2    6   10   14
[3,]    3    7   11   15
[4,]    4    8   12   16
```

Additionally, R has built in functions for matrix multiplication below we will multiple the matrix x that we created earlier. 

```
>x%*%x
     [,1] [,2] [,3] [,4]
[1,]   90  202  314  426
[2,]  100  228  356  484
[3,]  110  254  398  542
[4,]  120  280  440  600

```
Lastly, I can easily select a row in the matrix x. In this example I will select the 4th row in the x matrix. 
```
> x[4,]
[1]  4  8 12 16
```

# Compare Results to Built-In R Function [30 points]

 Exectuion times were plotted for loop, built-in, and recursive implementations for the sum of log gamma. According to the tests ran the built in function of log gamma in R ,sum_lgamma(), grew the slowest.  This can be attributed to the fact that the built in log gamma function is executed using C code. Per the source code the implementation is C code from a fortran subroutine. R is an interpreted language which results in overhead when executing code. While C is a compiled language which is much faster. 

![Imgur](https://i.imgur.com/ZqFFFQl.png)

The sum_log_gamma_loop implementation grew the faster than the sum_log_gamma_recursive function. The sum_log_gamma_recursive function was the slowest. From the graphs both are exponential. The slowest method was the recursive function according to the data. The execution times were plotted on a log-log plot to determine the exponential constant. The constant I calculated the slope from the log-log plot for recursion which was 1.83. This means that the complexity is polynomial and N^2.  While the loop slope from the log-log plot was 1.92. This means the time complexity is polynomial and N^2. From the log-log plot the recursive function has a bigger constant. 

![Imgur](https://i.imgur.com/QUmwe4h.png)

From the first graph it is hard to determine the time growth of the built in log gamma function. At first it looks like its constant time. However, in the below graph the built in log gamma function execution time was plotted with n =10,000.  From the graph it shows that the sum_lgamma function is linear or O(N)   

![Imgur](https://i.imgur.com/IlbeJWE.png)

## Sources 
Soruce code for built in lgamma function in R 

https://github.com/wch/r-source/blob/af7f52f70101960861e5d995d3a4bec010bc89e6/src/nmath/lgamma.c

