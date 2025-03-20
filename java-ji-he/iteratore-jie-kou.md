# Iterator接口

```java
boolean hasNext()
// 如果存在另一个可访问的元素，返回true。

E next()
// 返回将要访问的下一个对象。如果已经达到了集合的末尾，将抛出一个NoSuchElementException。

void remove()
// 删除上次访问的对象。这个方法必须紧跟在访问一个元素之后执行。
// 如果上次访问之后集合已经发生了变化，这个方法将抛出一个IllegalStateException。

default void forEachRemaining(Consumer<? super E> action)
// 访问元素，并传递到指定的动作，直到再没有更多元素，或者这个动作抛出一个异常。
```
