# Problem
```
np.where(a==1, 1, 0)
```
It should return an array, but it return a single number.

# Solve
```
np.where(np.array(a)==1, 1, 0)
```
**a** should be an array, but not a list.
