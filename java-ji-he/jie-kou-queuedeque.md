# 接口：Queue，Deque

队列

```java
Queue<E> q;
```

```java
boolean add(E element)
boolean offer(E element)
//如果队列没有满，将给定的元素添加到这个队列的队尾并返回true。
//如果队列已满，第一个方法将抛出一个IllegalStateException，而第二个方法返回false。

E remove()
E poll()
//如果队列不为空，删除并返回这个队列队头的元素。
//如果队列是空的，第一个方法抛出NoSuchElementException，而第二个方法返回null。

E element()
E peek()
//如果队列不为空，返回这个队列队头的元素，但不删除。
//如果队列空，第一个方法将抛出一个NoSuchElementException，而第一个方法返回null。
```

常用实现类

```java
LinkedList
```

双端队列

```java
Deque<E> dq;
```

```java
void addFirst(E element)
void addLast(E element)
boolean offerFirst(E element)
boolean offerLast(E element)
//将给定的对象添加到双端队列的队头或队尾。
//如果这个双端队列已满，前面两个方法将抛出一个IllegalStateException，而后面两个方法将返回false。

E removeFirst()
E removeLast()
E pollFirst()
E pollLast()
//如果这个双端队列不为空，删除并返回双端队列队头的元素。
//如果双端队列为空，前面两个方法将抛出一个NoSuchElementException，而后面两个方法返回null。

E getFirst()
E getLast()
E peekFirst()
E peekLast()
//如果这个双端队列不为空，返回双端队列队头的元素，但不删除。
//如果双端队列为空，前面两个方法将抛出一个NoSuchElementException，而后面两个方法返回null。
```

常用实现类

```java
ArrayDeque
```
