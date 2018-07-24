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

Numpy handles data sets as `array`s not `list`s. This 
