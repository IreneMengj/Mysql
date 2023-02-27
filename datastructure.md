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


