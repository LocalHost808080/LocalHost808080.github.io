# Comparable VS. Comparator

2022.03.06

## Comparable

1. 如果希望我们自己创建的一个类是可以用 Arrays.sort(), Collections.sort(), PriorityQueue 等排序的，则应该让这个类 `实现 Comparable 接口（<>中的类型是类本身），重写 compareTo(T o) 方法`
2. 如果想达到以上目的却用了 `实现 Comparator 接口 + 重写 compare(T o1, T o2)` 的组合，会出现 `cannot be cast to java.lang.Comparable` 报错

```java
public class Person implements Comparable<Person> {
    @Override
    public int compareTo(Person o) {}   
}
```

## Comparator

1. 如果我们希望让一个已有的类可以用 Arrays.sort(), Collections.sort(), PriorityQueue 等排序，可以新建一个该类的比较器，实现 Comparator 接口 + 重写 compare(T o1, T o2)

```java
class User {}
class UserComparator implements Comparator<User> {
    @Override
    public int compare(User u1, User u2) {}
}
```





