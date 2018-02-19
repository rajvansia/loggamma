### rvrv3
### Raj Vansia 

The time complexity of ***log_factorial(N) is O(N)*** that is because the execution time will grow linearly with respect to the size of N. For each iteration, N will decrement by 1 until it reaches 1. So at worst case the code will execute N times.

The time complexity of ***sum_log_factorial(N) is  O(N^2)*** because there is a outside loop that iterates  for each N. Then for each i in the loop it will then enter the log factorial function which has a time complexity of O(N) as noted above. So we multiply the two complexities and get O(N^2) 

The time complexity of the ***Fibonacci(N) is O(2^N)*** . This is because the function is using recursion. The number of calls the recursion function executes is N. the branching factor is 2 because each time it is returning  fib(n-1) and fib(n-2) for each recursive call. 


![Imgur](https://i.imgur.com/P7Szd39.png)

Code snippet showing how to calculate execution time for the Fibonacci function. Also shows how to create a data frame and create a line graph for diffrent execution times for each function.
```
## calculate the execution time of the fibonacci function 
for (i in 1:length(q)) {  
    time_fib=system.time(fibonacci(q[i]))
    time_fib=unname(time_fib[1])
    vec_fib <- c(vec_fib, time_fib) 
  }
## create the data frame of execution time for each function 
  tests <- data.frame("value"=x, "log"=vec_log)
  tes <- data.frame("value"=y, "sumlog"=vec_sumlog )
  test <- data.frame("value"=q, "fib"=vec_fib)
## create a line plot for each function execution time vs N  
  ggplot() + geom_line(data = tests, aes(x = value, y = log, color = "log")) +
    geom_line(data = tes, aes(x = value, y = sumlog, color = "sumlog"))+
    geom_line(data = test, aes(x = value, y = fib, color = "fib"))+

```
