### Stack
---
a stack is an abstract data type that serves as a collection of elements, with two
principal operations: push, which adds an element to the collection, and pop, which removes the
most recently added element that was not yet removed. The order in which elements come off a
stack gives rise to its alternative name, LIFO (for last in, first out). 
![image](https://user-images.githubusercontent.com/88880169/222900089-f000e445-5294-4ebc-9937-89fd9938f6a7.png)
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
