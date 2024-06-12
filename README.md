# Algebraic and graphical notes in Jupyter using Sympy, Numpy, Matplotlib etc.

## Sample from Exponential functions.

```python
import numpy as np
import matplotlib.pyplot as plt
import sympy as sym
from IPython.display import display,Math
```


```python
display(Math('\\text{Exponential function } f(x) = -4^{2-x} + 3'))
```


$\displaystyle \text{Exponential function } f(x) = -4^{2-x} + 3$



```python
a,b,x = sym.symbols('a,b,x')
# intial_value
a = -1
# growth_factor
b = 4
expr = a*(b**(2-x))
```


```python
x_points = np.linspace(-5, 5)
y_points = []

for x_ in x_points:
    y_ = sym.Float((expr.subs({ 'x': x_ })))
    y_points.append(y_)
```


```python
fig, (ax0) = plt.subplots(nrows=1, layout='constrained', figsize=(12,10))

ax0.plot(x_points, y_points, alpha=0.5, marker='o')
# plot horizontal asymptote
ax0.plot(x_points, (np.zeros(len(x_points)) + 3), '--', color='orange', alpha=0.8)

plt.show()
```


    
![png](output.png)
