<h3>What are Data Structures?</h3>
<p>Manner in which data is stored for efficient search and retrieval. The simplest data structure is the one-dimensional (linear) array, in which stored elements are numbered with consecutive integers and contents are accessed by these numbers. Data items stored non-consecutively in memory may be linked by pointers (memory addresses stored with items to indicate where the “next” item or items in the structure are located). Many algorithms have been developed for sorting data efficiently; these apply to structures residing in main memory and also to structures that constitute information systems and databases.</p>  

<h3>ArrayLists.</h3>     
<li> cannot directly store Java Primitives, so we must wrap them.</li>    
<li> is a class in the standard Java libraries that can hold any type of object, through a feature calledGenerics. </li>    
<li> an object that can grow and shrink while your program is running (unlike arrays, which have afixed length once they have been created). </li>     
<li> serves the same purpose as an array, except that an ArrayList can change length while the program is running, it is also easier to use.  </li>   
<hr>
<p>Resizable-array implementation of the List interface. Implements all optional list operations, and permits all elements, including null. In addition to implementing the List interface, this class provides methods to manipulate the size of the array that is used internally to store the list</p>

<p>ArrayList is implemented using an array as a private instance variable. When this hidden array is full, a new larger hidden array is created and the data is transferred to this new array. In this way an ArrayList abstracts the user from the low-level workings of an Array.</p>

<h3>Arrays versus ArrayList</h3>
<h4>Why use an Array?</h4>
<ol>
  <li>An ArrayList is less efficient than an array</li>
  <ul>
      <li>An ArrayList is less efficient than an array in some cases because an ArrayList is implemented as a dynamic array, which means it can grow and shrink as needed. When you add an element to an ArrayList, it may have to resize the underlying array and copy all the existing elements to a new, larger array. This can be expensive in terms of time and memory usage.
      <li>Another factor that can make an ArrayList less efficient than an array is that an ArrayList is an object, which means it has additional overhead compared to a simple array. Accessing an element in an ArrayList requires an additional level of indirection through a method call, while accessing an element in an array is a direct memory access.
  </ul>        
  <li>ArrayList does not have the convenient square bracket notation</li>
<li>The base type of an ArrayList must be a class type (or other reference type). It cannot be a primitive type. (Although wrappers, auto boxing, and auto unboxing make this a non-issue with Java 5)</li>
  </ol>
<h4>Why use an ArrayList?</h4>
<ul>
<li>Arrays can’t grow. Their size is fixed at compile time. ArrayList grows and shrinks as needed while your program is running</li>
<li>You need to keep track of the actual number of elements in your array (recall partially filled arrays). ArrayList will do that for you.</li>
<li>Arrays have no methods (just length instance variable). ArrayList has powerful methods for manipulating the objects within it</li>
</ul> 
<h3>Linked List</h3>
<h4>List</h4>
<p>An ArrayList is an implementation of the List interface. List is an ADT. In programming an interface is a means to specify behaviour without providing an implementation for that behaviour. An ArrayList is one implementation of the behaviour of the List interface in Java.</p>
<h4>Singly Linked List</h4>
<b>Memory Allocation</b><br>
1. Contiguous Allocation<br>
<ul>
<li>Implementation of lists can be array-based, this is known as contiguous memory allocation.
<li>In contiguous allocation, list elements occupy consecutive memory locations.
</ul>
![image](https://user-images.githubusercontent.com/88880169/221598240-88a8a23d-dbeb-4edb-a991-f67bd6fba81b.png)
<h4> Contiguous Allocation advantages</h4>
<ol>
<li>Access to a contiguously allocated list element is very fast: given any index k, we can compute the memory address of the list element at that position by adding the size (in bytes) of k items to the address of the first element in the list.
<li>Contiguous allocation is said to allow random access because we can directly jump to any given element without going through its predecessors.
<li>Contiguous allocation is used by array-based list implementations such as ArrayList
</ol>  
<h4> Contiguous Allocation disadvantages</h4> 
<ol>
<li> Insertion or deletion of elements in the middle of the list involves the laborious relocation of all elements that come after.
<li> For example, if a list has a thousand elements, then to insert a new element at position 5 means all elements from position 5 on up must be moved up.
<li> This overhead is bad for applications that do a lot of insertions and deletions
</ol>  
2. Linked Allocation<br>
<ul>
<li>Linked allocation is an alternative to contiguous allocation.
<li>In linked allocation, the list keeps a reference to its first element: this is the head reference
<li>Every element in the list keeps a reference to its successor, the element that follows it on the list.
<li>Memory for list elements does not have to be consecutive
</ul>  
![image](https://user-images.githubusercontent.com/88880169/221600521-3253c288-b398-4cb4-adf4-d0810f11a465.png)

Nodes & Links<br>
 The objects that hold the list element and the reference (link) to its successor are called nodes.
 The references to successors are called successor links.
<b>Disadvantages of Linked Allocation</b>
<ul>
<li>Given a node in the list, we can only access it by starting at the first node and following the successor links until we come to the desired node.
This is called sequential access.
<li>Sequential access takes a lot longer than random access to get to nodes near the end of a long list.
</ul>
