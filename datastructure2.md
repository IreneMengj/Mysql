### Stack
---
a stack is an abstract data type that serves as a collection of elements, with two
principal operations: push, which adds an element to the collection, and pop, which removes the
most recently added element that was not yet removed. The order in which elements come off a
stack gives rise to its alternative name, LIFO (for last in, first out). 
![image](https://user-images.githubusercontent.com/88880169/222900089-f000e445-5294-4ebc-9937-89fd9938f6a7.png).  
We could implement a stack using a Linked List, or anArray or an ArrayList.  
```
public class LinkedStack<T> implements Stack<T> {
    Node head;
    private class Node{
        public T item;
        public Node next;
        public Node(T item, Node next){
            this.item=item;
            this.next=next;
        }
    }
    public LinkedStack() {
        //this.head=new Node(null,null);
    }
    private boolean isEmpty(){
        return head==null;
    }

    @Override
    public void push(T ele) {
        if(isEmpty()){
            head=new Node(ele,null);
        }else{
            Node oldHead=head;
            head=new Node(ele,oldHead);
        }
    }

    @Override
    public T pop() {
        if(isEmpty()) return null;
        else{
            T value = head.item;
           head=head.next;
           return value;
        }
    }

    @Override
    public T peek() {
        if(isEmpty()) throw new IndexOutOfBoundsException();
        else{
            T value = head.item;
            return value;
        }
    }

    @Override
    public String toString() {
        String str = "TOP";

        Node top = head;
        while (top != null) {
            str += "\n" + top.item;
            top = top.next;
        }
        return str + "\nBOTTOM";
    }

    public static void main(String[] args) {
        Stack<Integer> stack = new LinkedStack<>();
        stack.push(2);
        stack.push(4);
        System.out.println(stack);
    }
}
```
---
```
public class ArrayStack <T> implements Stack<T>{
    int maxSize;
    int top;
    private T[] items;

    public ArrayStack(int size){
        this.maxSize=size;
        this.top=-1;
        this.items=(T[])new Object[maxSize];
    }

    private boolean isEmpty(){
        return top==-1;
    }


    @Override
    public void push(T ele) {
        if(top==maxSize-1){
            relocate();
        }
        top++;
        items[top]=ele;
    }
    public void relocate(){
        maxSize*=2;
        items=Arrays.copyOf(items,maxSize);
    }

    @Override
    public T pop() {
        if(isEmpty()) throw new IndexOutOfBoundsException();
        T item = items[top];
        top--;
        return item;
    }

    @Override
    public T peek() {
        if(isEmpty()) throw new IndexOutOfBoundsException();
        T item = items[top];
        return item;
    }

    @Override
    public String toString(){
        String str="Top: ";
        for(int i=top;i>=0;i--){
            str+=items[i]+", ";
        }
        str+="Bottom";
        return str;
    }

    public static void main(String[] args) {
        Stack<Integer> stack=new ArrayStack<>(3);
        stack.push(3);
        stack.push(4);
        stack.push(5);
        System.out.println(stack);
        stack.peek();
        System.out.println(stack);
        System.out.println(stack.pop());
        System.out.println(stack);
    }
}
```
### Queue. 
Definition: An abstract data type (ADT) in which the entities in the collection are kept in order
and the principal operations are the addition of entities to the rear terminal position, known as
enqueue, and removal of entities from the front terminal position, known as dequeue.   

This makes the queue a First-In-First-Out (FIFO) data structure. In a FIFO data structure, the first
element added to the queue will be the first one to be removed.    
Often a peek operation is also supported, returning the value of the front element without
dequeuing it.     
