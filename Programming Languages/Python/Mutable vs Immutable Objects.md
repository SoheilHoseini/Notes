In Python, an object is considered **immutable** if its value cannot be changed after it has been created. This means that any operation that modifies an immutable object returns a new object with the modified value. Examples of immutable objects in Python include **strings**, **tuples**, and **numbers**.

```python
tuple1 = (0, 1, 2, 3)
tuple1[0] = 4
print(tuple1)
```
Result:
```error
Traceback (most recent call last):
  File "e0eaddff843a8695575daec34506f126.py", line 3, in 
    tuple1[0]=4
TypeError: 'tuple' object does not support item assignment
```

Any operation that modifies a **mutable** object will modify the original object itself. To put it simply, mutable objects are those that can be modified either in terms of state or contents after they have been created. The mutable objects that are present in python are **lists**, **dictionaries** and **sets**.


