<b>Sorting Algorithms</b>

- <h3>Bubble Sort</h3>.
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
   
- <h3>Selection Sort</h3>. 
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

-<h3>Merge Sort</h3>

> - Divide: If S has zero or one element, return S immediately; it is already sorted. Otherwise (S has at least two elements), remove all the elements from S and put them into two sequences, S1 and S2, each containing about half of the elements of S; that is, S1 contains the first ⌊n/2⌋ elements of S, and S2 contains the remaining ⌈n/2⌉ elements.
> - Conquer: Recursively sort sequences S1 and S2.
> - Combine: Put the elements back into S by merging the sorted sequences S1 and S2 into a sorted sequence



<img width="475" alt="image" src="https://user-images.githubusercontent.com/88880169/221359670-19e2c7b3-272f-4956-88bf-f0fa11e5aa5b.png">
<img width="475" alt="image" src="https://user-images.githubusercontent.com/88880169/221359703-185fa66e-0ef0-4e8a-a9a3-11fad164e8f5.png">
<img width="475" alt="image" src="https://user-images.githubusercontent.com/88880169/221359707-c66a9b37-fd61-45f7-b707-ed45614afb5b.png">
<img width="475" alt="image" src="https://user-images.githubusercontent.com/88880169/221359910-9f8f117f-4f23-4d43-87b7-4ef80a14043a.png">
<img width="475" alt="image" src="https://user-images.githubusercontent.com/88880169/221359918-51b5daa0-b3b7-468f-a269-1de87ad3fdcf.png">
<hr>

- time complexity:  
  - Always O(N*logN) because merge is O(N), and division is O(logN).
  - Overhead of creating temp array and copying data.
  - For large dataset Quicksort outperforms it.


<h3>Generic Programming</h3>
<hr>
<img width="350" alt="image" src="https://user-images.githubusercontent.com/88880169/221354907-2ccceb9a-597c-49e7-9c37-1cd5f1f64207.png">
<img width="534" alt="image" src="https://user-images.githubusercontent.com/88880169/221354911-daa7b7a6-ead7-4348-a64f-fab239c1723e.png">
<hr>
Generic Programming – Searching or Sorting. 
<hr>
<img width="534" alt="image" src="https://user-images.githubusercontent.com/88880169/221355026-3b3a0fc0-d53b-474a-bf44-5380aa36728b.png">
<img width="534" alt="image" src="https://user-images.githubusercontent.com/88880169/221355033-b63bf678-2f2f-4782-92ec-70e681fbe821.png">
<img width="534" alt="image" src="https://user-images.githubusercontent.com/88880169/221355036-999f070d-285b-4bb9-9b88-7da4036a6588.png">

```
public class GenericArray2<T extends Comparable<T>> {
    private T[] data;
    int size=0;

    public GenericArray2() {
        data=(T[])new Comparable[50];
    }
    public GenericArray2(int n) {
        data=(T[])new Comparable[n];
    }
    public void add(T element){
        data[size]=element;
        size++;
    }
    public int length(){
        return size;
    }
    public String printGe(){
        return Arrays.toString(data);
    }
    public boolean search(T element){
        boolean found = false;
        int j=0;
        while(j<size&& !found){
            if(data[j].compareTo(element)==0){
                found=true;
            }
            j++;
        }
        return found;
    }
    public void bubbleSort(){
        for(int i=0;i<size;i++){
            for(int j=1;j<size-i;j++){
                if(data[j-1].compareTo(data[j])>0){
                    T temp=data[j-1];
                    data[j-1]=data[j];
                    data[j]=temp;
                }
            }
        }
        System.out.println(Arrays.toString(data));
    }
    public void selectionSort(){
        for(int i=0;i<size;i++){
            int smallestIndex=i;
            for(int j=i+1;j<size;j++){
                if(data[j].compareTo(data[smallestIndex])<0){
                    smallestIndex=j;
                }
            }
            T temp=data[i];
            data[i]=data[smallestIndex];
            data[smallestIndex]=temp;
        }
        System.out.println(Arrays.toString(data));
    }
    public void insertionSort(){

    }

    public static void main(String[] args) {
        GenericArray2<Integer> ge=new GenericArray2();
        ge.add(3);
        ge.add(561);
        ge.add(4);
        ge.add(34);
        ge.add(39);
        ge.add(56);
        ge.add(6);
        boolean search = ge.search(3);
        String s = ge.printGe();
        //System.out.println(s);
        //System.out.println(search);
        //ge.bubbleSort();
        ge.selectionSort();
    }
}
```
<h3>Generic Programming – Iteration.</h3>  
An iterator is an object that allows traversal over a given data structure.   
<img width="534" alt="image" src="https://user-images.githubusercontent.com/88880169/221357158-bd1b0651-a89e-43e5-af8f-88c98dffe779.png">
<img width="534" alt="image" src="https://user-images.githubusercontent.com/88880169/221357163-37d62a93-4ae5-484e-b936-ba9f6596d8eb.png">
<img width="758" alt="image" src="https://user-images.githubusercontent.com/88880169/221357171-885ad0eb-d3ed-47c6-89af-1e4f974410ee.png">
<img width="534" alt="image" src="https://user-images.githubusercontent.com/88880169/221357174-87df9122-bb0a-4bb3-87ea-7c0642e6a008.png">

<h3>algorithmic design pattern</h3>.  
divide-and-conquer: 
1. Break problem up into smaller parts.
2. Solve each part recursively.
3. Combine solutions to sub-problems into overall solution.  

<h3>Recursion</h3>
This is the process in which a method calls itself continuously.
- Recursion is defined by two properties:
  - A base case
  - A set of rules that reduces the chain of invocation to the base case.  
  <hr>
  <img width="248" alt="image" src="https://user-images.githubusercontent.com/88880169/221359008-e702fcee-51e0-4270-9b2d-8501f312848f.png">
  <img width="828" alt="image" src="https://user-images.githubusercontent.com/88880169/221359024-50b78f51-ea9c-44f6-92d2-b28cbfc0773a.png">
  <img width="475" alt="image" src="https://user-images.githubusercontent.com/88880169/221359522-6d740026-c60e-4144-b21b-0a5596f01d66.png">
  <img width="837" alt="image" src="https://user-images.githubusercontent.com/88880169/221359540-d7112e04-3f77-400c-8a58-d11f2529465f.png">
















