search algorithm
1. Sequential Search (or Linear Search) searches all the elements of the array  sequentially until a target element is found or all the elements are checked.
  - Start from the beginning of the array
  - Move from one item to its neighbour
  - If the item is found at the 𝑖^𝑡ℎ index, it returns the index (or the value or just TRUE)
  - Otherwise, keep searching until it reaches the end of the array
```
public static int sequentialSearch(int[] arr, int target) {
        for (int i = 0; i < arr.length; i++) {
            if (arr[i] == target) {
                return i;
            }
        }
        return -1;
    }
```
- time complexity
  - Best case for an array containing n items is when  the target is found at the beginning of the array.
  - This requires a single comparison: O(1)
  - Worst case scenario is when the target is not in the array.
  - Requires n comparisons to check this. O(n)
  - The average case scenario is when the target is in the middle
  - This requires n/2 comparisons: n/2 -> O(n)

2. Binary Search

