
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

#use a Poisson distribution

exp_val_1 = 47
var_1 = 47

k = 60

#we want to find the probability of P(X=60)
prob_1 = (
    exp_val_1**k
    *np.exp(-exp_val_1)
    /np.math.factorial(k)
)

# used for tests
pkl_dump([
    (exp_val_1, 'exp_val_1'),
    (var_1, 'var_1'),
    (prob_1, 'prob_1')
])

# prob_1
```

    can"t dump, exp_val_1 already exists


### Problem 2

Lebron and MJ are playing pickup 1:1 (all made baskets are 2pts)

Every time Lebron drives on MJ, he has an 80% chance of making a basket

During the course of the game, Lebron drives 45 times

What is the probability he scores **at least** 80 pts?


```python

#We have 45 trials of an outcome that is 80% success and 20% failure for each trial

#Binomial is the distribution to use

n = 45
p = .8

exp_val_2 = n*p

var_2 = n*p*(1-p)

'''
We'll sum the probabilities that Lebron makes 80, 82, . . . , 90 pts

(why do we sum?)

if we have 80 points at 2pts a shot we have 40 made shots out of 45 trials

similarly, 82pts = 41 shots, . . ., 90pts = 45 shots

so, we'll calculate the probabilities for Lebron making [40, 45] shots and sum em
'''

def n_choose_k(n, k):
    '''
    computes n choose k
    
    inputs: 
        n: integer
        k: integer
        
    outputs:
        n choose k
    '''
    
    value = (
        np.math.factorial(n)
        / 
        (
            np.math.factorial(k)
            * np.math.factorial(n-k)
        )
    )
    
    return value

def binomial_prob(p, k, n):
    '''
    calculates the probability for a given p, k, and n
    in a binomial distribution 
    
    inputs:
        p: integer
        k: integer
        n: integer
        
    outputs:
        the probability in a binomial distribution
        of having k successes of n trials
        with success probability p of any one trial
        
    requires:
        function n_choose_k(n, k) which calculates n choose k 
        for a given n and k
    '''
    
    prob = n_choose_k(n,k) * p**(k)*(1-p)**(n-k)
    
    return prob
    

prob_2 = (
    np.sum(
        [
            binomial_prob(p, k, n)
            for k
            in range(40, 46)
        ]
    
    )

)

#used for tests
# pkl_dump([
#     (exp_val_2, 'exp_val_2'),
#     (var_2, 'var_2'),
#     (prob_2, 'prob_2')
# ])

prob_2
```




    0.09020387884112469


