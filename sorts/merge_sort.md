# Merge sort
## Basics
- Description: A divide-and-conquer algorithm, it is a comparison algorithm
- Worst-case performance: $O(n \log(n))$
- [Wikepedia](https://en.wikipedia.org/wiki/Merge_sort)

## Implementations
```python
import math # Imports the math library for the use of the floor function
def merge_sort(arr: list) -> list:
    if len(arr) <= 1: # A list of zero or one elements is sorted, by definition
        return arr

    mid = math.floor(len(arr)/2) # Determines the middle of the array
    left: list = arr[:mid] # Puts the first half of the array into the left list
    right: list = arr[mid:] # Puts the second half of the array into the right list

    left = merge_sort(left) # The function calls itself to split the left side of the array
    right = merge_sort(right) # The function calls itself to split the right side of the array
    return merge(left, right) # Returns the merged list

def merge(left: list, right: list) -> list:
    i,j = 0,0
    result: list = [] # Creates an empty result list
    while i<len(left) and j<len(right): # Checks if either of the lists have been completely covered by the merge
        if left[i] <= right[j]: # If the left list has the smaller number add that number to the result list
            result.append(left[i])
            i += 1
        else: # If the right list has the smaller number add that number to the result list
            result.append(right[j])
            j += 1
    result.extend(left[i:]) # Cleaning up if either of the lists wasnt empty
    result.extend(right[j:])
    return result # Returns the merged list
```
