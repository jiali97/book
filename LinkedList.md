---
tags:
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