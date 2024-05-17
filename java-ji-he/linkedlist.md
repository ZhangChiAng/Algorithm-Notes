---
description: 链表
---

# LinkedList

以下情况使用 ArrayList :

* 频繁访问列表中的某一个元素。
* 只需要在列表末尾进行添加和删除元素操作。

以下情况使用 LinkedList :

* 你需要通过循环迭代来访问列表中的某些元素。
* 需要频繁的在列表开头、中间、末尾等位置进行添加和删除元素操作。

```java
import java.util.LinkedList; 
LinkedList<E> list = new LinkedList<E>();
```

#### 构造器方法

```java
LinkedList()    //构造一个空列表。
```

#### 常用方法

```java
void addFirst(E e)    //在此列表的开头插入指定的元素。
void addLast(E e)    //将指定的元素追加到此列表的末尾。
void add(int index, E e)    //将指定元素插入此列表中的指定位置。
E removeFirst()    //从此列表中删除并返回第一个元素。
E removeLast()    //从此列表中删除并返回最后一个元素。
E remove(int index)    //删除此列表中指定位置的元素。
E getFirst()    //返回此列表中的第一个元素。
E getLast()    //返回此列表中的最后一个元素。
E get(int index)    //返回此列表中指定位置的元素。
E set(int index, E e)    //用指定的元素替换此列表中指定位置的元素。
int size()    //返回此列表中的元素数。
Object[] toArray()    //以适当的顺序（从第一个元素到最后一个元素）返回包含此列表中所有元素的数组。
```
