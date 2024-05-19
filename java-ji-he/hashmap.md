---
description: 无序
---

# HashMap

```java
import java.util.HashMap
var mp = new HashMap<K, V>();
```

#### 构造方法

```java
HashMap()    //使用默认初始容量（16）和默认加载因子（0.75）构造一个空 HashMap 。
```

#### 实例方法

```java
V put(K key, V value)    //将指定的值与此映射中的指定键相关联。

V get(Object key)    //返回指定键映射到的值，如果此映射不包含键的映射，则返回 null。

V remove(Object key)    //从此映射中删除指定键的映射（如果存在）。

Set<Map.Entry<K,​V>> entrySet()    //返回此映射中包含的映射的Set视图。
Set<K> keySet()    //返回此映射中包含的键的Set视图。
Collection<V> values()    //返回此映射中包含的值的Collection视图。

boolean containsKey(Object key)    //如果此映射包含指定键的映射，则返回 true 。
boolean containsValue(Object value)    //如果此映射将一个或多个键映射到指定值，则返回 true 。
```

#### Map.Entry

```java
K getKey()    //返回与此条目对应的键。
V getValue()    //返回与此条目对应的值。
V setValue(V value)    //用指定的值替换此条目对应的值（可选操作）。
```
