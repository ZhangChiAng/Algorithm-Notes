---
description: >-
  StringBuilder 和 StringBuffer 之间的最大不同在于 StringBuilder 的方法不是线程安全的（不能同步访问)。由于
  StringBuilder 相较于 StringBuffer 有速度优势，所以多数情况下建议使用 StringBuilder 类。
---

# StringBuilder

```java
var sb = new StringBuilder();
```

#### 构造方法

```java
StringBuilder()    //构造一个字符串构建器，其中不包含任何字符，初始容量为16个字符。
StringBuilder​(String str)    //构造一个初始化为指定字符串内容的字符串构建器。
```

#### 实例方法

```java
StringBuilder append(typename x)    //将参数x的字符串表示形式追加到序列中。
StringBuilder insert(int offset, typename x)    //将参数x的字符串表示形式插入此序列中。

char charAt(int index)    //返回指定索引处的此序列中的 char值。

StringBuilder replace(int start, int end, String str)    //使用指定的 String的字符替换此序列的子字符串中的字符。

StringBuilder delete(int start, int end)    //删除此序列的子字符串中的字符。
StringBuilder deleteCharAt(int index)    //按此顺序删除指定位置的char。

int compareTo(StringBuilder another)    //以字典序比较两个StringBuilder实例。
```
