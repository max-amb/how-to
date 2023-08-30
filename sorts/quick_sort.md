# Quick sort
## Basics
- Description: A divide-and-conquer algorithm, based on a partitioning routine.
- Worst-case performance: $O(n^2)$
- [Wikepedia](https://en.wikipedia.org/wiki/Quicksort)

## Implementations
```python
def partition(array: list, start: int, end: int) -> int:
    pivot = array[end] # Set pivot as the last element (Lomuto partition scheme)
    i = start - 1 # Temporary pivot index
    for j in range(start, end):
        if array[j] <= pivot: # If the element is less then or equal to the pivot
            i = i + 1 # Move the temporary pivot index up
            array[i], array[j] = array[j], array[i] # Swap the current element with the element at the temporary pivot index
    i += 1 # Move the temporary pivot index forward
    array[i], array[end] = array[end], array[i] # Swap the pivot and the element at the pivot index to put it between the smaller and larger elements
    return i # Return the pivots index
 
def quick_sort(array: list, start: int, end: int):
    if start < end: # Ensure indices are in the correct order
        pivot_index = partition(array, start, end) # Gets the pivot index after partitioning the array
        quick_sort(array, start, pivot_index-1) # Left side of the pivot
        quick_sort(array, pivot_index+1, end) # Right side of the pivot
    return array
```
