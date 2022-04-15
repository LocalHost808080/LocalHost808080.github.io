# Comparable VS. Comparator

2022.03.06

## Comparable 接口 + compareTo(T o)

1. 如果希望我们自己创建的一个类是可以用 Arrays.sort(), Collections.sort(), PriorityQueue 等直接排序的，则应该让这个类 `实现 Comparable 接口（<>中的类型是类本身），重写 compareTo(T o) 方法`
2. 如果想达到以上目的却用了 `实现 Comparator 接口 + 重写 compare(T o1, T o2)` 的组合，会出现 `cannot be cast to java.lang.Comparable` 报错

```java
// 用法
public class Person implements Comparable<Person> {
    @Override
    public int compareTo(Person o) {}   
}

public static void main() {
    Queue<Person> queue = new PriorityQueue<>();
    
    List<Person> list = new ArrayList<>();
    Collections.sort(list);
    
    Person[] personArr = new Person[10];
    Arrays.sort(personArr);
}
```

```java
// 定义
package java.lang;
import java.util.*;

public interface Comparable<T> {
    public int compareTo(T o);
}
```

```java
// 案例
public class Person implements Comparable<Person> {
    private String name;
    private int age;

    @Override
    public int compareTo(Person o) {
        int temp = this.name.compareTo(o.name);
        return temp == 0 ? this.age - o.age : temp ;
    }   
}
```

```java
class IDistPair implements Comparable<IDistPair> {
    public double iDist;
    public int objId;

    public IDistPair(double iDist, int objId) {
        this.iDist = iDist;
        this.objId = objId;
    }

    @Override
    public int compareTo(IDistPair o) {
        if (this.iDist <= o.iDist)
            return -1;
        else
            return 1;
    }
}
```

```java
// 这里如果我用 Comparator 和 compare 函数的组合
// 会出现 cannot be cast to java.lang.Comparable 的报错
class MappingNum implements Comparable<MappingNum> {
    public int origin;
    public int mapped;
    public int index;

    MappingNum(int origin, int mapped, int index) {...}

    @Override
    public int compareTo(MappingNum mn) {
        if (this.mapped < mn.mapped)
            return -1;
        else if (this.mapped > mn.mapped)
            return 1;
        else
            return this.index - mn.index;
    }
}
```

## Comparator 接口 + compare(T o1, T o2)

1. 如果我们希望让一个已有的类可以用 Arrays.sort(), Collections.sort(), PriorityQueue 等排序，可以新建一个该类的比较器，实现 Comparator 接口 + 重写 compare(T o1, T o2)

```java
// 用法
class User {}

class UserComparator implements Comparator<User> {
    @Override
    public int compare(User u1, User u2) {}
}

public static void main() {
    Queue<User> q = new PriorityQueue<>(new UserComparator());
}
```

```java
public static void main() {
    Queue<User> q = new PriorityQueue<>(new UserComparator());
}

class UserComparator implements Comparator<User> {
    @Override
    public int compare(User u1, User u2) {
        if (u1.number.charAt(0) == u2.number.charAt(0))
            return u1.number.compareTo(u2.number);
        if (u1.number.charAt(0) == 'V') {
            return -1;
        } else {
            return 1;
        }
    }
}

class User {
    public final String name;
    public final String number;
}
```

```java
// 定义
package java.util;

public interface Comparator<T> {
    int compare(T o1, T o2);
    boolean equals(Object obj);
}
```

```java
@Override
public int compare(CommentVo o1, CommentVo o2) {
           return o1.getTime().compareTo(o2.getTime());
}
// 返回-1（或负数），表示不需要交换01和02的位置，o1排在o2前面，asc
// 返回1（或正数），表示需要交换01和02的位置，o1排在o2后面，desc
```

```java
class ListComparator implements Comparator<List<Integer>> {
    @Override
    public int compare(List<Integer> list1, List<Integer> list2) {
        Integer sum1 = list1.get(0) + list1.get(1);
        Integer sum2 = list2.get(0) + list2.get(1);
        return sum1.compareTo(sum2);
    }
}
```

```java
TreeMap<Person, String> treeMap2 = new TreeMap<>((person1, person2) -> {
    int num = person1.getAge() - person2.getAge();
    return Integer.compare(num, 0);
});
```


```java
List<Edge> edges = new ArrayList<Edge>();

Collections.sort(edges, new Comparator<Edge>() {
    public int compare(Edge edge1, Edge edge2) {
        return edge1.len - edge2.len; 
        // 返回负数，edge1 和 edge2 不换位置
    }
});
```

```java
int[] intervals = new int[10];

Arrays.sort(intervals, new Comparator<int[]>() {
    public int compare(int[] interval1, int[] interval2) {
        return interval1[0] - interval2[0];
    }
});
```

```java
PriorityQueue<Integer> queue = new PriorityQueue<Integer>(new Comparator<Integer>() {
    public int compare(Integer num1, Integer num2) {
        return num2 - num1;	 // 大顶堆，大的先出
    }
}); 
```





