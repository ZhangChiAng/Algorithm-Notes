# Queue\<E>接口

## 常用API

```java
boolean add(E element)
boolean offer(E element)
// 如果队列没有满，将给定的元素添加到这个队列的队尾并返回true。
// 如果队列已满，第一个方法将抛出一个IllegalStateException，而第二个方法返回false。

E remove()
E poll()
// 如果队列不为空，删除并返回这个队列队头的元素。
// 如果队列是空的，第一个方法抛出NoSuchElementException，而第二个方法返回null。

E element()
E peek()
// 如果队列不为空，返回这个队列队头的元素，但不删除。
// 如果队列空，第一个方法将抛出一个NoSuchElementException，而第一个方法返回null。
```

## 常用实现类

```java
LinkedList
```
