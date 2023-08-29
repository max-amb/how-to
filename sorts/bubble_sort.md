# Bubble sort
## Basics
- Description: Works by comparing each element to the one next to it in the list and swapping them if necessary, it is a comparison sort.
- Worst-case performance: $O(n^2)$
- [Wikepedia](https://en.wikipedia.org/wiki/Bubble_sort)

## Implementations
```python
# Unoptimised
def bubble_sort(arr: list) -> list:
    for i in range(0,n-2):
        for j in range(0, n-i-2):
            if arr[j] > arr[j+1]:
                arr[j], arr[j+1] = arr[j+1], arr[j]
    return arr

# Optimised
def bubble_sort(arr: list) -> list:
    while True:
        swapped = False # Tracking if a swap was made
        for i in range(1,len(arr)):
            if arr[i-1] > arr[i]:
                arr[i-1], arr[i] = arr[i], arr[i-1] # Swap
                swapped = True
        if not swapped: # If no swaps were made
            break
    return arr
```
