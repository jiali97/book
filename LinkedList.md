---
tags:
- 技巧总结
- Linked List
---

#### Linked List 常见技巧总结

- 只要涉及到处理头结点的时候，都可以通过增添哑结点，使得操作head节点和其他节点无异
- 找到链表中的一个特定位置的时候，可以使用快慢指针的方法
- 交换两个节点的注意事项
  - 先交换两个前驱节点的next指针的值
  - 再交换这两个节点的next指针的值
- 修改单链表的时候注意事项
  - 哪个节点的`next`指针受到影响，需要修改该指针
  - 操作链表的时候注意边界条件
- 同时操作两个链表的注意事项
  - 循环条件可以是`while list1 && list2`
  - 当循环跳出的时候，再处理剩下非空的链表
- 倒序访问链表
  - 可以使用递归或者是栈来进行等效处理
- Java 中链表的实现类 LinkedList\<E\>
  - add(E e)
  - add(int index, E e)
  - remove(int index)
  - addAll(Collection< ? Extends E> c)
  - get(int index)
- Reference: 《程序员面试白皮书》

#### Java 链表类定义

```java
public class ListNode {
		int val;
  	ListNode next;
  	ListNode(int x) { val = x; }
}
```

#### Python 链表类定义

```python
class ListNode:
    def __init__(self, x):
        self.val = x
        self.next = None
```

#### Java 中链表的实现类 LinkedList 使用方法

```Java
//构造函数
// LinkedList类是双向链表，列表中的每个节点都包含了对前一个和后一个元素的引用
LinkedList<String> list = new LinkedList<String>(); //生成空的链表
LinkedList<String> list = new LinkedList<String>(Col); //复制构造函数

//方法
//1. 增添
boolean add(E e); //Appends the specified element to the end of this list.
void add(int index, E e); //Inserts the specified element at the specified position in this list.
boolean addAll(Collection<? extends E> c); //Appends all of the elements in the specified collection to the end of this list, in the order that they are returned by the specified collection's iterator.
boolean addAll(int index, Collection<? Extends E> C);//Inserts all of the elements in the specified collection into this list, starting at the specified position.
void addFirst(E e); //Inserts the specified element at the beginning of this list.
void addLast(E e); //Appends the specified element to the end of this list.
boolean	offer(E e); //Adds the specified element as the tail (last element) of this list.
boolean	offerFirst(E e); //Inserts the specified element at the front of this list.
boolean	offerLast(E e);// Inserts the specified element at the end of this list.

//2. 获取
E element(); // Retrieves, but not remove the head of the list.
E get(int index); //Returns the element at the specified position in this list.
E	getFirst(); // Returns the first element in this list.
E	getLast(); //Returns the last element in this list.
E	peek();  //Retrieves, but does not remove, the head (first element) of this list.
E	peekFirst(); //Retrieves, but does not remove, the first element of this list, or returns null if this list is empty.
E	peekLast(); //Retrieves, but does not remove, the last element of this list, or returns null if this list is empty.
int	indexOf(Object o); //Returns the index of the first occurrence of the specified element in this list, or -1 if this list does not contain the element.
int	lastIndexOf(Object o); //Returns the index of the last occurrence of the specified element in this list, or -1 if this list does not contain the element.

//3. 删除
void clear();//Removes all of the elements from this list.
E	poll(); //Retrieves and removes the head (first element) of this list.
E	pollFirst(); //Retrieves and removes the first element of this list, or returns null if this list is empty.
E	pollLast(); //Retrieves and removes the last element of this list, or returns null if this list is empty.
E	pop(); //Pops an element from the stack represented by this list.
void	push(E e); //Pushes an element onto the stack represented by this list.
E	remove();//Retrieves and removes the head (first element) of this list.
E	remove(int index);//Removes the element at the specified position in this list.
boolean	remove(Object o);//Removes the first occurrence of the specified element from this list, if it is present.
E	removeFirst();//Removes and returns the first element from this list.
boolean	removeFirstOccurrence(Object o);//Removes the first occurrence of the specified element in this list (when traversing the list from head to tail).
E	removeLast();//Removes and returns the last element from this list.
boolean	removeLastOccurrence(Object o); //Removes the last occurrence of the specified element in this list (when traversing the list from head to tail).

// 4. 设置
E	set(int index, E element);//Replaces the element at the specified position in this list with the specified element.

// 5. 其他方法
Object clone();//Returns a shallow copy of the LinkedList.
boolean contains(Object o); // Return true if this list contains the specified element.
int	size();//Returns the number of elements in this list.
Object[]	toArray();//Returns an array containing all of the elements in this list in proper sequence (from first to last element).
<T> T[]	toArray(T[] a); //Returns an array containing all of the elements in this list in proper sequence (from first to last element); the runtime type of the returned array is that of the specified array.
ListIterator<E>	listIterator(int index); //Returns a list-iterator of the elements in this list (in proper sequence), starting at the specified position in the list.
Spliterator<E>	spliterator();//Creates a late-binding and fail-fast Spliterator over the elements in this list.
```

#### Java 中 ArrayList 和 LinkedList 区别

- `ArrayList`实现了基于动态数组的结构，`LinkedList`基于实现链表的结构。
- 对于随机访问`get`和`set`, `ArrayList`明显要优于`LinkedList`, 因为`LinkedList`需要移动指针
- 对于数组元素的添加删除，在不同的数据规模上测试的时候，两种结构表现出来的不一样，所以不进行比较。

####Reference

- [ArrayList和LinkedList的区别](https://blog.csdn.net/eson_15/article/details/51145788)
- [LinkedList 类用法文档](https://docs.oracle.com/javase/7/docs/api/java/util/LinkedList.html)