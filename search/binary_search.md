# Binary search
## Basics
- Description: An algorithm that finds the position of a target value within a sorted array by repeatedly splitting the array in half.
- Worst-case performance: $O(\log(n))$
- [Wikepedia](https://en.wikipedia.org/wiki/Binary_search_algorithm)

## Implementations
```python
import math # Imports the math library for use of the floor function
def binary_search(arr: list, key: int) -> bool:
    left = 0 # Sets the left bound to the start of the array
    right = len(arr)-1 # Sets the right bound to the end of the array
    mid = 0 # To avoid mid is possibly unbound errors
    while left != right: # While the array has not homed in on the value
        mid = math.floor((left+right)/2) # Determines the middle of the array
        if arr[mid] > key: # If the middle of the array is greater than the key value
            right = mid # Moves the right bound to the middle of the array
        else: # If the middle of the array is less than or equal to the key value
            left = mid+1 # Moves the left bound to the middle of the array plus 1
    if arr[mid] == key: # If the homed in on value is the key
        return True
    else:
        return False
```
