# TreeSet trong java
## Lớp TreeSet trong java
- Sử dụng cấu trúc cây để lưu trữ các phần tử
- Kế thừa (```extends```) **AbstractSet**
- Triển khai (```implements```) của **NavigableSet** của **Set** trong Collections Framework 

## Những điểm cần ghi nhớ về lớp TreeSet:
- Chỉ chứa các phần tử duy nhất giống như HashSet.
- Thời gian truy xuất nhanh.
- Duy trì thứ tự tăng dần.

Hierarchy của lớp TreeSet
Lớp TreeSet trong java implements giao diện NavigableSet. Giao diện NavigableSet extends giao diện SortedSet, Set, Collection và Iterable theo thứ bậc.
![image-1](./image/treeset-trong-java.png)

> Ví dụ về TreeSet trong java
```java
package vn.viettuts.collection;
 
import java.util.TreeSet;
 
public class TreeSetExample1 {
    public static void main(String[] args) {
        // init treeSet object
        TreeSet<String> treeSet = new TreeSet<String>();
        treeSet.add("Java");
        treeSet.add("C++");
        treeSet.add("Java");
        treeSet.add("PHP");
        // show treeSet
        for (String str : treeSet) {
            System.out.println(str);
        }
    }
}
```
```
C++
Java
PHP
```

> TreeSet trong java với đối tượng Student:
> Chú ý: Phần tử của lớp TreeSet trong java phải được implements giao diện Comparable. Trong ví dụ này lớp Student phải được implements giao diện Comparable và phải override phương thức compareTo() để cài đặt các tiêu trí so sánh.

```java
package vn.viettuts.collection;
 
import java.util.TreeSet;
 
/**
 * Student class
 * 
 * @author viettuts.vn
 */
class Student implements Comparable<Student> {
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
 
    @Override
    public int compareTo(Student student) {
        // sort student's name by ASC
        return this.getName().compareTo(student.getName());
    }
}
 
/**
 * TreeSetExample2 class
 * 
 * @author viettuts.vn
 */
public class TreeSetExample2 {
    public static void main(String[] args) {
        // init treeSet
        TreeSet<Student> treeSet = new TreeSet<Student>();
        // create students object
        Student student1 = new Student("Cong", 17, "Hanoi");
        Student student2 = new Student("Dung", 16, "Haiphong");
        Student student3 = new Student("Ngon", 18, "Hanoi");
        Student student4 = new Student("Hanh", 19, "Danang");
        // add students object to treeSet
        treeSet.add(student1);
        treeSet.add(student2);
        treeSet.add(student3);
        treeSet.add(student4);
        treeSet.add(student1);
        // show treeSet
        for (Student student : treeSet) {
            System.out.println(student.toString());
        }
    }
}
```
```
Student@name=Cong,age=17,address=Hanoi
Student@name=Dung,age=16,address=Haiphong
Student@name=Hanh,age=19,address=Danang
Student@name=Ngon,age=18,address=Hanoi
```