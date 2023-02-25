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
- Binary search can be applied to a sorted array where the array is sorted based on the search key:
  - Searches a sorted array repeatedly dividing the search interval in half;
  - If the value of the target key is less than the middle value, it narrows the search to the lower half;	
  - If the value of the target key is greater than the middle value, it narrows the search to the upper half;
  - Repeat this process until all the values are found or the interval is empty.
```
public static int binarySearch(int[] array, int target) {
        int left = 0;
        int right = array.length - 1;
        
        while (left <= right) {
            int mid = (left + right) / 2;
            
            if (array[mid] == target) {
                return mid;
            } else if (array[mid] < target) {
                left = mid + 1;
            } else {
                right = mid - 1;
            }
        }
```
- Divides the search space in two on every iteration:
  - Similar to the logarithmic function
  - The average & worst case time complexity of binary search is O(log n).
  - So, binary search is often far faster than linear search (which is O(n)) if the array is sorted.
  - The best case scenario for an array containing n items is when the target is found at the middle of the first iteration. This requires a single comparison – O(1)




