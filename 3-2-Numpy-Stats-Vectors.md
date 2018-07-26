# 3-2. NumPy, stats and vectors

Python is good at handling basic stats. We'll use the `NumPy` and `Scipy` packages to handle this.

1. `import`/`as`.
2. NumPy arrays vs `list`s
3. Statistical methods (mean, median, mode, standard deviation, variance)
4. Linear regression (using the `scipy` package)

**Project**: Interpolating real data

## 1. import/as

The major package for using stats is `NumPy`. Since it gets annoying to write `numpy.something` over and over, it is **standard practice** to import it `as` `np`. That way we can write `np.array` instead of `numpy.array`.

```python
import numpy as np

x = np.array([1,4,9])
print( x )
```

## 2. Numpy arrays vs lists

Numpy handles data sets as `array`s not `list`s. It also assumes that the data is all of one type: strings, ints or floats. If you mix floats and ints it will automatically convert things to floats.

```python
import numpy as np

x = np.array([1,4,9.2])
print( x )
```

There's a *lot* we could say about arrays - [like all this stuff](http://cs231n.github.io/python-numpy-tutorial/#numpy), but for now we'll leave it at "treat them basically like lists, but no that there's a lot of other stuff you can do with them."

```python
import numpy as np

x = np.array([[1,2,3],[1,4,9]])
print( np.sum(x) ) # Sum all elements; prints "12"
print(np.sum(x, axis=0))  # Compute sum of each column; prints "[2 6 12]"
print(np.sum(x, axis=1))  # Compute sum of each row; prints "[6 14]"
```

Adding elements to arrays is more annoying, because Python is treating an array like an n by m box. Adding an element to an array is like adding an extra column!

```python
import numpy as np

x = np.array([1,2,3])
y = np.array([4,5,6,7])
print(np.concatenate([x, y]))
```

### Exercise

Use the `matplotlib` package to plot and display the data we gathered. Change the data however you want to make a new graph.

```python
import numpy as np

import numpy as np
import matplotlib.pyplot as plt

x = np.array([i for i in range(2,10)])
y = np.array([i**4 for i in range(2,10)])

plt.plot(x, y) # Plot the points. Try replacing this by plt.scatter(x, y)
plt.savefig('file_name.png')
```

## 3. Statistical methods (mean, median, standard deviation, variance)

NumPy is very good at handling statistics. It can perform all the basic operations you want (except mode?). Let's compute them now for a data set.

```python
import numpy as np
import matplotlib.pyplot as plt  # For plotting
from sympy import sieve          # For totient function

N=100
x = np.array([i for i in range(1,N)])
y = np.array([i for i in sieve.totientrange(1, N)])

plt.scatter(x, y)
plt.savefig('file_name.png')

print( np.mean(y), np.median(y))
print( np.std(y) ) # Standard Deviation
print( np.var(y) ) # Variance
```

### Exercise

The above code has been modified to look at statistics from `phi(n)/n` instead of just `phi(n)`. Run this code and interpret your findings.

```python
import numpy as np
import matplotlib.pyplot as plt
from sympy import sieve

N=100
x = np.array([i for i in range(1,N)])
y = np.array([n/(i+1) for i,n in enumerate(sieve.totientrange(1, N))]) # phi(n)/n

plt.scatter(x, y)
plt.savefig('phi_over_n.png')

print( np.mean(y), np.median(y))
print( np.std(y) ) # Standard Deviation
print( np.var(y) ) # Variance
```

## 4. Linear regression (using the `scipy` package)

While NumPy doesn't give us the power to do linear regression (or line of best fit), the `SciPy` package does! So lets use it to perform linear regression.

```python
from scipy import stats
import numpy as np
import matplotlib.pyplot as plt  # For plotting
from sympy import sieve   # For totient function

N=100
x = np.array([i for i in range(1,N)])
y = np.array([i for i in sieve.totientrange(1, N)])
slope, intercept, r_value, p_value, std_err = stats.linregress(x,y)

plt.scatter(x, y)
plt.plot(x, slope*x+intercept, 'r.-') # Line of best fit. 'r.-' makes it red.
plt.savefig('phi_stats.png')

print( slope, intercept, r_value, p_value, std_err )
```

### Exercise

1. Find how to call the standard deviation of y, using [Numpy's documentation](https://docs.scipy.org/doc/numpy-1.14.0/reference/routines.statistics.html). Call this variable `std_dev`. 
2. Take the above plot and add the bounds from the standard deviation. To do this, plot the line of best fit twice more: once by shifting the line up `std_dev`, and once by shifting the line down by `std_dev`.

```python
from scipy import stats
import numpy as np
import matplotlib.pyplot as plt  # For plotting
from sympy import sieve   # For totient function

N=100
x = np.array([i for i in range(1,N)])
y = np.array([i for i in sieve.totientrange(1, N)])
slope, intercept, r_value, p_value, std_err = stats.linregress(x,y)

std_dev = # HERE!

plt.scatter(x, y)
plt.plot(x, slope*x+intercept, 'r.-') # Line of best fit. 'r.-' makes it red.
# Upper bound for std_dev here. Make it green with 'g.-'
# Lower bound for std_dev here. Make it green with 'g.-'
plt.savefig('phi_stats.png')

print( slope, intercept, r_value, p_value, std_err )
```

**Project**: Interpolating real data

In this project I'd like you to use a real data set. There are an amazing amount of [free data sets](https://www.springboard.com/blog/free-public-data-sets-data-science-project/) available of very high quality. With your new knowledge of Python you can interpret and visualize this data. Have fun and do some science!

Choose one of the following projects:

1. Plot the [population of Georgia over time](https://www.statista.com/statistics/206111/resident-population-in-georgia/), or whatever your favourite location is.
2. Plot the [violent crime rates](https://ucr.fbi.gov/crime-in-the-u.s/2013/crime-in-the-u.s.-2013/tables/1tabledatadecoverviewpdf/table_1_crime_in_the_united_states_by_volume_and_rate_per_100000_inhabitants_1994-2013.xls) in the US for the past 20 years. Plot the absolute numbers, and the numbers per 100,000 people.
