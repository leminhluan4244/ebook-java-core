# Các ví dụ về sử dụng Set trong java

### Thêm các phần tử vào Set trong Java
Để thêm các phần tử cho một Set bạn gọi phương thức add(). Phương thức này được kế thừa từ Collection interface.

```java
Set<String> setA = new HashSet<String>();
setA.add("Java");
setA.add("Python");
setA.add("Java");
setA.add("PHP");
```

### Thêm các phần tử một Collection khác vào Set trong Java
Phương thức addAll(Collection c) được sử dụng để chèn tất cả các phần tử của c vào set, Ví dụ:
```
package vn.viettuts.set;

import java.util.HashSet;
import java.util.Set;

public class SetExam {
    public static void main(String[] args) {
        Set<String> setA = new HashSet<String>();
        Set<String> setB = new HashSet<String>();
        setB.add("Java");
        setB.add("Python");
        setB.add("Java");
        setB.add("PHP");
        // Thêm các phần tử setB khác vào setA trong Java
        setA.addAll(setB);
         
        System.out.println("Số phần tử của setA: " + setA.size());
        System.out.println("Các phần tử của setA: " + setA);
        System.out.println("setA có chứa Java không? " + setA.contains("Java"));
        System.out.println("setA có chứa C++ không? " + setA.contains("C++"));
    }
}
```
```
Số phần tử của setA: 3
Các phần tử của setA: [Java, PHP, Python]
setA có chứa Java không? true
setA có chứa C++ không? false
```

### Duyệt các phần của một Set trong Java
Có hai cách để duyệt các phần tử của Java Set.
- Sử dụng bộ lặp Iterator
- Sử dụng vòng lặp for-each
#### Sử dụng bộ lặp Iterator
Ví dụ duyệt Set với bộ lặp Iterator:

```java
package vn.viettuts.set;
 
import java.util.HashSet;
import java.util.Iterator;
import java.util.Set;
 
public class DuyetSet1 {
    public static void main(String[] args) {
        Set<String> setA = new HashSet<String>();
        setA.add("Java");
        setA.add("Python");
        setA.add("Java");
        setA.add("PHP");
        System.out.println("Số phần tử của setA: " + setA.size());
        System.out.println("Các phần tử của setA: ");
        Iterator<String> iterator = setA.iterator();
        while (iterator.hasNext()) {
            System.out.println((String) iterator.next());
        }
    }
}
```

```
Số phần tử của setA: 3
Các phần tử của setA: 
Java
PHP
Python
```
#### Sử dụng vòng lặp for-each
Ví dụ duyệt Set với vòng lặp for-each:

```java
package vn.viettuts.set;
 
import java.util.HashSet;
import java.util.Set;
 
public class DuyetSet2 {
    public static void main(String[] args) {
        Set<String> setA = new HashSet<String>();
        setA.add("Java");
        setA.add("Python");
        setA.add("Java");
        setA.add("PHP");
        System.out.println("Số phần tử của setA: " + setA.size());
        System.out.println("Các phần tử của setA: ");
        for (String element : setA) {
            System.out.println(element);
        }
    }
}
```
```
Số phần tử của setA: 3
Các phần tử của setA: 
Java
PHP
Python
```
### Xóa phần tử khỏi Set trong Java
Bạn xóa các phần tử khỏi Set bằng cách gọi phương thức remove(Object o). Ví dụ:

```java
package vn.viettuts.set;
 
import java.util.HashSet;
import java.util.Set;
 
public class XoaSetExam1 {
    public static void main(String[] args) {
        Set<String> setA = new HashSet<String>();
        setA.add("Java");
        setA.add("Python");
        setA.add("Java");
        setA.add("PHP");
        System.out.println("Các phần tử của setA trước khi xóa: ");
        for (String element : setA) {
            System.out.println(element);
        }
        // xóa phần tử PHP khỏi setA
        setA.remove("PHP");
        System.out.println("Các phần tử của setA sau khi xóa: ");
        for (String element : setA) {
            System.out.println(element);
        }
    }
}
```
```
Các phần tử của setA trước khi xóa: 
Java
PHP
Python
Các phần tử của setA sau khi xóa: 
Java
Python
```

### Xóa tất cả các phần tử khỏi Set trong Java
Bạn có thể xóa tất cả các phần tử khỏi Set bằng phương thức clear().
```java
set.clear();
```
### Độ dài của Set trong Java
Bạn có thể kiểm tra độ dài/kích thước của một set trong Java bằng cách sử dụng phương thức size().

```java
package vn.viettuts.set;
 
import java.util.HashSet;
import java.util.Set;
 
public class SetExam {
    public static void main(String[] args) {
        Set<String> setA = new HashSet<String>();
        setA.add("Java");
        setA.add("Python");
        setA.add("Java");
        setA.add("PHP");
        System.out.println("Số phần tử của setA: " + setA.size());
    }
}
```
```
Số phần tử của setA: 3
```

### Kiểm tra Set trống trong Java
Bạn có thể kiểm tra độ dài/kích thước của một set trong Java bằng cách sử dụng phương thức isEmpty().

```java
package vn.viettuts.set;
 
import java.util.HashSet;
import java.util.Set;
 
public class SetExam {
    public static void main(String[] args) {
        Set<String> setA = new HashSet<String>();
        setA.add("Java");
        setA.add("Python");
        setA.add("Java");
        setA.add("PHP");
        Set<String> setB = new HashSet<String>();
        System.out.println("setA có trống không? " + setA.isEmpty());
        System.out.println("setB có trống không? " + setB.isEmpty());
    }
}
```
```
setA có trống không? false
setB có trống không? true
```

### Chuyển đổi Set thành List trong Java
Bạn có thể chuyển đổi Set thành List trong Java bằng cách tạo List và gọi addAll() phương thức của nó, truyền tham số dưới dạng set cho phương thức addAll(). Ví dụ:

```java
package vn.viettuts.set;
 
import java.util.ArrayList;
import java.util.HashSet;
import java.util.List;
import java.util.Set;
 
public class SetExam {
    public static void main(String[] args) {
        Set<String> setA = new HashSet<String>();
        setA.add("Java");
        setA.add("Python");
        setA.add("Java");
        setA.add("PHP");
        List<String> listA = new ArrayList<String>();
        // chuyển đổi setA thành listA
        listA.addAll(setA);
        System.out.println(listA);
    }
}
```
```
[Java, PHP, Python]
```