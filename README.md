
# Distributions warmup!

## To start, a writing exercise.

![](viz/writing.gif)

Write out the differences between:

- A discrete and continous variable, as well as an example of each

- A PMF, PDF and CDF, as well as an example of what you would calculate with each

- An example of a situation in which you would use a Binomial distribution, a Bernoulli distribution, a Poisson distribution, and a Normal distribution

Practice some Markdown!

Ping Ben to have him look your answers over!

Write your answers here






## A spot of coding, eh
![](viz/eh.gif)

#### Imports


```python
#Run this cell as-is

#data manip
import numpy as np

#used for tests
from test_background import pkl_dump, test_obj_dict, run_test_dict, run_test 
```

#### For each problem:

- Determine which distribution is appropriate to use for calculating
- Calculate the expected value of the random variable described and its variance
- Calculate the given probability

### Problem 1

Kevin Durant loves posting on his social media feeds.  He has the true soul of a poster, in that:

- any given post is independent of any other post
- on average he posts 47 times an hour

What is the probability in a given hour that he achieves posting nirvana and posts 60 times?


```python
'''
you may have to create extra variables than these, 
but use these as your expected value, variance,
and probability variables
'''

exp_val_1 = #your code here

var_1 = #your code here

prob_1 = #your code here
```


    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    <ipython-input-31-624091ed50d0> in <module>
         12     exp_val_1**k
         13     *np.exp(-exp_val_1)
    ---> 14     /np.math.factorial(k)
         15 )


    TypeError: unsupported operand type(s) for ** or pow(): 'NoneType' and 'int'



```python
#run this cell to test your expected value

run_test(exp_val_1, 'exp_val_1')
```




    'Hey, you did it.  Good job.'




```python
#run this cell to test your variance

run_test(var_1, 'var_1')
```




    'Hey, you did it.  Good job.'




```python
#run this cell to test your probability

run_test(prob_1, 'prob_1')
```




    'Try again'



### Problem 2

Lebron and MJ are playing pickup 1:1 (all made baskets are 2pts)

Every time Lebron drives on MJ, he has an 80% chance of making a basket

During the course of the game, Lebron drives 45 times

What is the probability he scores **at least** 80 pts?


```python
'''
you may have to create extra variables than these, 
but use these as your expected value, variance,
and probability variables
'''

exp_val_2 = #your code here

var_2 = #your code here

prob_2 = #your code here
```


```python
#run this cell to test your expected value

run_test(exp_val_2, 'exp_val_2')
```


```python
#run this cell to test your variance

run_test(var_2, 'var_2')
```


```python
#run this cell to test your probability

run_test(prob_2, 'prob_2')
```
