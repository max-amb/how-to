# Bubble sort
## Basics
- Description: Works by comparing each element to the one next to it in the list and swapping them if necessary thus it is a comparison sort.
- Worst-case performance: $O(n^2)$
- [Wikepedia](https://en.wikipedia.org/wiki/Bubble_sort)

## Implementations
```python
# Unoptimised
def bubble_sort(arr: list) -> list:
    for i in range(0,n-2): # First loop
        for j in range(0, n-i-2): # Second(inner) loop
            if arr[j] > arr[j+1]: # Determining if elements need to be swapped
                arr[j], arr[j+1] = arr[j+1], arr[j] # Swap
    return arr

# Optimised
def bubble_sort(arr: list) -> list:
    while True: # Infinite while loop
        swapped = False # Tracking if a swap was made
        for i in range(1,len(arr)): # Loop through the array
            if arr[i-1] > arr[i]: # Determining if elements need to be swapped
                arr[i-1], arr[i] = arr[i], arr[i-1] # Swap
                swapped = True # Changes the swapped variable to indicate a swap was made
        if not swapped: # If no swaps were made
            break # Exits the infinite while loop as the array is sorted
    return arr
```
