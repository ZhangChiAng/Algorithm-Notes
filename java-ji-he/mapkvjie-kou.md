# Map\<K, V>接口

## 常用API

```java
V get(Object key)
// 获取与键关联的值；
// 返回与键关联的对象，或者如果映射中没有这个对象，则返回null。实现类可以禁止键为null。
default V getOrDefault(Object key, V defaultValue)
// 获取与键关联的值；
// 返回与键关联的对象，或者如果未在映射中找到这个键，则返回defaultValue。

V put(K key, V value)
// 将关联的一对键和值放到映射中。
// 如果这个键已经存在，新的对象将取代与这个键关联的旧对象。这个方法将返回键关联的旧值。
// 如果之前没有这个键，则返回null。实现类可以禁止键或值为null。
void putAll(Map<? extends K, ? extends V> entries)
// 将给定映射中的所有映射条目添加到这个映射中。

boolean containsKey(Object key)
// 如果在映射中已经有这个键，返回true。
boolean containsValue(Object value)
// 如果映射中已经有这个值，返回true。

default void forEach(BiConsumer<? super K, ? super V> action)
// 对这个映射中的所有键值对应用这个动作。

default V merge(K key, V value, 
                BiFunction<? super V, ? super V, ? extends V> remappingFuntion)
// 如果key与一个非null值v关联，将函数应用到v和value，将key与结果关联，
// 或者如果结果为null，则删除这个键。
// 否则，将key与value关联，返回get(key)。

default V compute(K key,
                BiFunction<? super K, ? super V, ? extends V> remappingFunction)
// 将函数应用到key和get(key)。将key与结果关联，
// 或者如果结果为null，则删除这个键。返回get(key)。
default V computeIfPresent(K key,
                BiFunction<? super K, ? super V, ? extends V> remappingFunction) 
// 如果key与一个非null值v关联，将函数应用到key和v，将key与结果关联，
// 或者如果结果为null，则删除这个键。返回get(key)。
default V computeIfAbsent(K key,
                Function<? super K, ? extends V> mappingFunction) 
// 将这个函数应用到key，除非key与一个非null值关联。将key与结果关联，
// 或者如果结果为null，则删除这个键。返回get(key)。

default void replaceAll(BiFunction<? super K, ? super V, ? extends V> function)
// 在所有映射条目上应用这个函数。将键与非null结果关联，对于null结果，则将相应的键删除。

default V putIfAbsent(K key, V value)
// 如果key不存在或者与null关联，则将它与value关联，并返回null。否则返回关联的值。

Set<Map.Entry<K, V>> entrySet()
// 返回Map.Entry对象（映射中的键值对）的一个集视图。
// 可以从这个集中删除元素，它们将从映射中删除，但是不能添加任何元素。

Set<K> keySet()
// 返回映射中所有键的一个集视图。
// 可以从这个集中删除元素，键和相关联的值将从映射中删除，但是不能添加任何元素。

Collection<V> values()
// 返回映射中所有值的一个集合视图。
// 可以从这个集合中删除元素，所删除的值及相对应的键将从映射中删除，不过不能添加任何元素。
```

## 常用实现类

```java
HashMap, TreeMap
```
