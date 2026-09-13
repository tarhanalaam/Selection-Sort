# Selection Sort

A simple implementation of the selection sort algorithm in Python.

## Overview

Selection sort works by repeatedly finding the smallest remaining element in the unsorted portion of the list and swapping it into its correct sorted position. It divides the list into a sorted region (at the front) and an unsorted region (the rest), growing the sorted region by one element on each pass.

## Usage

```python
from selection_sort import selection_sort

nums = [64, 25, 12, 22, 11]
sorted_nums = selection_sort(nums)
print(sorted_nums)  # [11, 12, 22, 25, 64]
```

### Signature

```python
def selection_sort(nums: list[int]) -> list[int]:
```

- **nums**: A list of integers to sort.
- **Returns**: The same list, sorted in ascending order (sorted in place; the return value is a convenience).

## How It Works

1. Iterate over each index `i` from `0` to `len(nums) - 1`.
2. Assume the element at `i` is the smallest in the remaining unsorted portion.
3. Scan the rest of the list (`j` from `i + 1` to the end) to find the actual smallest element, tracking its index in `smallest_idx`.
4. Swap the element at `i` with the element at `smallest_idx`.
5. Repeat until the entire list is sorted.

## Complexity

| Case      | Time Complexity | Notes                                   |
|-----------|-----------------|------------------------------------------|
| Best      | O(n²)           | Still scans the full remainder each pass |
| Average   | O(n²)           |                                          |
| Worst     | O(n²)           |                                          |
| Space     | O(1)            | Sorts in place, no extra memory needed   |

- **Stable?** No — equal elements may be reordered relative to each other.
- **In-place?** Yes — sorting is done by swapping within the original list.

## When to Use It

Selection sort is rarely the best choice for production use since algorithms like Timsort (Python's built-in `sort()`) or quicksort/mergesort perform far better on large datasets. It's mainly useful for:

- Educational purposes (easy to understand and trace by hand)
- Small datasets where simplicity matters more than performance
- Situations where minimizing the number of swaps matters (it performs at most `n - 1` swaps)