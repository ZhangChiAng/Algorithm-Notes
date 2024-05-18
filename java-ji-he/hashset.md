---
description: 无序
---

# HashSet

```java
import java.util.HashSet;
var set = new HashSet<E>();
```

#### 构造方法

```java
HashSet()    //构造一个新的空集; 支持HashMap实例具有默认初始容量（16）和加载因子（0.75）。
```

#### 实例方法

```java
boolean	add​(E e)    //如果指定的元素尚不存在，则将其添加到此集合中。

boolean	contains​(Object o)    //如果此set包含指定的元素，则返回 true。

boolean	remove​(Object o)    //如果存在，则从该集合中移除指定的元素。

void clear()    //从该集中删除所有元素.
boolean	isEmpty()    //如果此集合不包含任何元素，则返回 true。
int size()    //返回此集合中的元素数。
```
