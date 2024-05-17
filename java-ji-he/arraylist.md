---
description: ArrayList 类是一个可以动态修改的数组，与普通数组的区别就是它是没有固定大小的限制，我们可以添加或删除元素。
---

# ArrayList

```java
import java.util.ArrayList;
ArrayList<E> objectName =new ArrayList<>();
//E: 泛型数据类型，只能为引用数据类型。
```

#### 构造方法

```java
ArrayList()    //构造一个初始容量为10的空列表。
ArrayList​(int initialCapacity)    //构造具有指定初始容量的空列表。
```

#### 实例方法

{% code fullWidth="false" %}
```java
boolean add(E e)    //将指定的元素追加到此列表的末尾。
void add(int index, E element)    //将指定元素插入此列表中的指定位置
E get(int index)    //返回此列表中指定位置的元素。
E set(int index, E element)    //用指定的元素替换此列表中指定位置的元素。
E remove(int index)     //删除此列表中指定位置的元素。
void sort(Comparator c)    //根据指定的顺序对动态数组中的元素进行排序
                                //(Comparator.naturalOrder()/reverseOrder())。
int size()    //返回此列表中的元素数。
boolean isEmpty()    //如果此列表不包含任何元素，则返回 true 。
Object[] toArray()    //以适当的顺序（从第一个元素到最后一个元素）返回包含此列表中所有元素的数组。
```
{% endcode %}

#### 基本类型的包装类



|  基本类型 |    引用类型   |
| :---: | :-------: |
|  int  |  Integer  |
|  char | Character |
| 首字母小写 |   首字母大写   |
