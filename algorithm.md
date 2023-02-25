<b>Sorting Algorithms</b>

- Bubble Sort.
  - steps:   
    - Start from the beginning of the array;
    - Compare every adjacent pair, swap their position if they are in the wrong order (item on right smaller than the left).
    - After each iteration, one less element (the last element) is needed to be compared until there are no more elements left to be compared.
  - Time Complexity:    
    1. Because the array contains n elements, it has an O(n) number of elements   
    2. Bubble sort perform O(n) operations on an O(n) number of elements.  
    3. Hence bubble sort has a worst-case & average complexity of O(𝑛^2)，Where n is the number of items to be sorted.
    4. O(n) is the best-case running time for bubble sort on a list already sorted. 
    <hr>
  > <img width="828" alt="image" src="https://user-images.githubusercontent.com/88880169/221352365-3a61306d-6787-4874-b7f3-91d0cad601fe.png">
  > 
  > <img width="393" alt="image" src="https://user-images.githubusercontent.com/88880169/221352462-7d5cc4be-5106-4521-9906-cfb17b60e959.png">
 <hr>
   
- Selection Sort. 
  - This is called selection sort because it works by repeatedly selecting the smallest item in the array.
  - steps:  
    - 1.First find the smallest item in the array and exchange it with the first entry.
    - 2.Find the next smallest item and exchange it with the second entry.
    - 3.Continue with this logic until the entire array is sorted
  <img width="807" alt="image" src="https://user-images.githubusercontent.com/88880169/221352829-575aba4c-2b21-4772-bab6-6b51152bb0e9.png">
  <img width="624" alt="image" src="https://user-images.githubusercontent.com/88880169/221352860-ef201440-17f4-467a-b644-aac33373110b.png">
  <hr>
  - time complexity:  
    - O(𝑛^2) because it involves a loop within a loop over a space of size n.  
    - Selection sort is not impacted in any way by the state of the data.  
    - Therefore, the worst case and the best-case performs both at O(𝑛^2).     
- Insertion Sort. 
  - The algorithm that is often used to sort a deck of cards. It considers then one at a time, inserting each into its proper place among those already considered (keeping them sorted).  
  - steps:  
    - Iterate from the first element to the last.  
    - Compare the current element to its predecessor.  
    - If the element is smaller than its predecessor, compare it to the elements before. Move the greater elements one position up to make space for        smaller elements.  
   <img width="616" alt="image" src="https://user-images.githubusercontent.com/88880169/221353922-f669502b-c28b-4d81-a861-4668369e1204.png">
   <img width="613" alt="image" src="https://user-images.githubusercontent.com/88880169/221353928-cf198bce-3716-4ec8-b62e-7c4c2275f4ec.png">
    <hr>
   - time complexity:  
     - Unlike selection sort, the running time of insertion sort depends on the initial order of the items.
     - Worst-case performance if data is sorted inversely, giving O(𝑛^2).
     - Inner loop never executes if data is sorted, giving O(n).






