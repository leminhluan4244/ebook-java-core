# Các ví dụ về sử dụng HashSet trong java

### HashSet hoạt động như thế nào:

```java
package vn.viettuts.collection.hashset;
 
import java.util.HashSet;
 
public class HashSetExam1 {
    public static void main(String[] args) {
        HashSet<String> setA = new HashSet<String>();
        setA.add("Java");
        setA.add("Python");
        setA.add("Java");
        setA.add("PHP");
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

### Thêm các phần tử vào HashSet trong Java

Để thêm các phần tử cho một HashSet bạn gọi phương thức add(). Phương thức này được kế thừa từ Collection interface.

```java
HashSet<String> setA = new HashSet<String>();
setA.add("Java");
setA.add("Python");
setA.add("Java");
setA.add("PHP");
```

### Thêm các phần tử một Collection khác vào HashSet trong Java

Phương thức addAll(Collection c) được sử dụng để chèn tất cả các phần tử của c vào HashSet, Ví dụ:

```java
package vn.viettuts.collection.hashset;
 
import java.util.HashSet;
 
public class HashSetExam2 {
    public static void main(String[] args) {
        HashSet<String> setA = new HashSet<String>();
        HashSet<String> setB = new HashSet<String>();
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

# Duyệt các phần của một HashSet trong Java

Có hai cách để duyệt các phần tử của Java HashSet.
- Sử dụng bộ lặp Iterator
- Sử dụng vòng lặp for-each

#### Sử dụng bộ lặp Iterator
```java
package vn.viettuts.collection.hashset;
 
import java.util.HashSet;
import java.util.Iterator;
 
public class HashSetExam3 {
    public static void main(String[] args) {
        HashSet<String> setA = new HashSet<String>();
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
```java
package vn.viettuts.collection.hashset;
 
import java.util.HashSet;
 
public class HashSetExam4 {
    public static void main(String[] args) {
        HashSet<String> setA = new HashSet<String>();
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

### Xóa phần tử khỏi HashSet trong Java
Bạn xóa các phần tử khỏi HashSet bằng cách gọi phương thức remove(Object o). Ví dụ:

```java
package vn.viettuts.collection.hashset;
 
import java.util.HashSet;
 
public class HashSetExam5 {
    public static void main(String[] args) {
        HashSet<String> setA = new HashSet<String>();
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

### Xóa tất cả các phần tử khỏi HashSet trong Java
Bạn có thể xóa tất cả các phần tử khỏi HashSet bằng phương thức clear().

```java
set.clear();
```

### Độ dài của HashSet trong Java
Bạn có thể kiểm tra độ dài/kích thước của một HashSet trong Java bằng cách sử dụng phương thức size().

```java
package vn.viettuts.collection.hashset;
 
import java.util.HashSet;
 
public class HashSetExam6 {
    public static void main(String[] args) {
        HashSet<String> setA = new HashSet<String>();
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

### Kiểm tra HashSet trống trong Java
Bạn có thể kiểm tra độ dài/kích thước của một HashSet trong Java bằng cách sử dụng phương thức isEmpty().

```java
package vn.viettuts.collection.hashset;
 
import java.util.HashSet;
 
public class HashSetExam7 {
    public static void main(String[] args) {
        HashSet<String> setA = new HashSet<String>();
        setA.add("Java");
        setA.add("Python");
        setA.add("Java");
        setA.add("PHP");
        HashSet<String> setB = new HashSet<String>();
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

### Ví dụ sử dụng HashSet với kiểu do người dùng tự định nghĩa (Object)
```java
package vn.viettuts.collection.hashset;
 
import java.util.HashSet;
 
public class HashSetExam8 {
    public static void main(String[] args) {
        // khoi tao hashSet
        HashSet<Student> hashSet = new HashSet<Student>();
        // Tao cac doi tuong Student
        Student student1 = new Student("Cong", 17, "Hanoi");
        Student student2 = new Student("Dung", 16, "Haiphong");
        Student student3 = new Student("Ngon", 18, "Hanoi");
        Student student4 = new Student("Hanh", 19, "Danang");
        // them cac doi tuong Student vao hashSet
        hashSet.add(student1);
        hashSet.add(student2);
        hashSet.add(student3);
        hashSet.add(student4);
        hashSet.add(student1);
        // Hien thi hashSet
        for (Student student : hashSet) {
            System.out.println(student.toString());
        }
    }
}
 
/**
 * Student class
 * 
 * @author viettuts.vn
 */
class Student implements {
    private String name;
    private int age;
    private String address;
  
    public Student() {
    }
  
    public Student(String name, int age, String address) {
        super();
        this.name = name;
        this.age = age;
        this.address = address;
    }
  
    public String getName() {
        return name;
    }
  
    public void setName(String name) {
        this.name = name;
    }
  
    public int getAge() {
        return age;
    }
  
    public void setAge(int age) {
        this.age = age;
    }
  
    public String getAddress() {
        return address;
    }
  
    public void setAddress(String address) {
        this.address = address;
    }
  
    @Override
    public String toString() {
        return "Student@name=" + name + ",age=" + age + ",address=" + address;
    }
}
```
```
Student@name=Dung,age=16,address=Haiphong
Student@name=Hanh,age=19,address=Danang
Student@name=Cong,age=17,address=Hanoi
Student@name=Ngon,age=18,address=Hanoi
```