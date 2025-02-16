# List接口

## 常用API

```java
ListIterator<E> listIterator()
//返回一个列表迭代器，用来访问列表中的元素
ListIterator<E> listIterator(int index)
//返回一个列表迭代器，用来访问列表中的元素，第一次调用这个迭代器的next会返回给定索引的元素

void add(int i, E element)
//在给定位置添加一个元素
void addAll(int i, Collection<? extends E> elements)
//将一个集合中的所有元素添加到指定位置

E remove(int i)
//删除并返回给定未知的元素

E get(int i)
//获取给定未知的元素

E set(int i)
//用一个新元素替换给定位置的元素，并返回原来那个元素

int indexOf(Object element)
//返回与指定元素相等的元素在列表中第一次出现的位置，如果没有这样的元素将返回-1
int lastIndexOf(Object element)
//返回与指定元素相等的元素在列表中最后一次出现的位置，如果没有这样的元素将返回-1
```

## 常用实现类

```java
ArrayList, LinkedList
```
