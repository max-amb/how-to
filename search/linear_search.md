# Linear search
## Basics
- Description: An algorithm that sequentially checks each element of the list until a match is found or the whole list has been searched.
- Worst-case performance: $O(n)$
- [Wikepedia](https://en.wikipedia.org/wiki/Linear_search)

## Implementations
```python
def linear_search(arr: list, key: int) -> bool:
    for i in arr: # Loop through array
        if i == key: # If the element is found
            return True
    return False
```
