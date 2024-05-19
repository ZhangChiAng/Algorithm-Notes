---
description: String类是不可改变的，如果需要对字符串做很多修改，那么应该选择使用StringBuffer/StringBuilder类。
---

# String

String 创建的字符串存储在公共池中，而 new 创建的字符串对象在堆上

```java
String s1 = "s1";
String s2 = new String("s2");
```
