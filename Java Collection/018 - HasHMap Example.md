# Các ví dụ về sử dụng HashMap trong java

### Khởi tạo một HashMap
Để khai báo một HashMap, chúng ta cần phải import gói thư viện java.util.HashMap của Java. Cú pháp import như sau:

```java
// import gói thư viện java.util.HashMap
import java.util.HashMap;
 
public class KhoiTaoHashMap {
    public static void main(String[] args) {
        // khai báo 1 HashMap có tên là hashMap1
        // có key là String và value là String
        HashMap<String, String> hashMap1 = new HashMap<String, String>();
    }
}
```

### Duyệt và hiển thị các phần tử có trong HashMap
Để hiển thị các phần tử có trong ArrayList, chúng ta có các cách như sau:

#### Hiển thị theo tên của HashMap
Bạn có thể sử dụng lệnh System.out.println(hashMap) để hiển thị ra thông tin của đối tượng hashMap. Ví dụ:

```java
package vn.viettuts.collection.hashmap;
 
import java.util.HashMap;
 
public class HashMapExample1 {
    /**
     * main
     * 
     * @author viettuts.vn
     * @param args
     */
    public static void main(String args[]) {
        // khoi tao hashMap
        HashMap<Integer, String> hashMap = new HashMap<Integer, String>();
        // them cac phan tu vao hashMap
        hashMap.put(1, "Java");
        hashMap.put(3, "C++");
        hashMap.put(2, "PHP");
        hashMap.put(4, "Python");
        // hien thi HashMap
        System.out.println(hashMap);
    }
}
```
```
{1=Java, 2=PHP, 3=C++, 4=Python}
```

#### Sử dụng vòng lặp for - duyệt các phần tử của HashMap
Ví dụ này chúng ta sẽ sử dụng hàm keySet() để lấy ra một đối tượng Set chứa các key của HashMap. Sau đó sử dụng vòng lặp for để lặp các key của đối tượng Set. Sử dụng các key này để lấy ra giá trị tương ứng được lưu trữ trong đối tượng HashMap:

```java
package vn.viettuts.collection.hashmap;
 
import java.util.HashMap;
import java.util.Set;
 
/**
 * Vi du su dung vong lap for duyet cac phan tu cua HashMap
 * 
 * @author viettuts.vn
 */
public class HashMapExample2 {
 
    public static void main(String args[]) {
        // init hashMap
        HashMap<Integer, String> hashMap = new HashMap<Integer, String>();
        // add elements to hashMap
        hashMap.put(1, "Java");
        hashMap.put(3, "C++");
        hashMap.put(2, "PHP");
        hashMap.put(4, "Python");
        // hien thi HashMap
        show(hashMap);
    }
     
    public static void show(HashMap<Integer, String> hashMap) {
        Set<Integer> keySet = hashMap.keySet();
        for (Integer key : keySet) {
            System.out.println(key + " - " + hashMap.get(key));
        }
    }
}
```
```
1 - Java
2 - PHP
3 - C++
4 - Python
```

#### Sử dụng Map.Entry interface - duyệt các phần tử của HashMap
Bạn có thể sử dụng phương thức `entrySet()` để duyệt các phần tử của `HashMap`, phương thức này trả về một đối tượng `Map.Entry`. Vi dụ:

```java
package vn.viettuts.collection.hashmap;
 
import java.util.HashMap;
import java.util.Map;
  
public class HashMapExample7 {
    public static void main(String args[]) {
        // init map
        HashMap<Integer, String> map = new HashMap<Integer, String>();
        // add elements to map
        map.put(1, "Java");
        map.put(3, "C++");
        map.put(2, "PHP");
        map.put(4, "Python");
        // show map
        for (Map.Entry<Integer, String> entry : map.entrySet()) {
            System.out.println(entry.getKey() + " - " + entry.getValue());
        }
    }
}
```

```
1 - Java
2 - PHP
3 - C++
4 - Python
```

#### Sử dụng Iterator - duyệt các phần tử của HashMap
Bạn có thể sử dụng phương thức `keySet().iterator()` để duyệt các phần tử của HashMap. Vi dụ:
```java
package vn.viettuts.collection.hashmap;
 
import java.util.Iterator;
import java.util.TreeMap;
 
public class HashMapExample8 {
    public static void main(String args[]) {
        // khoi tao map
        TreeMap<String, String> map = new TreeMap<String, String>();
        // them cac phan tu vao map
        map.put("J", "Java");
        map.put("C", "C++");
        map.put("P", "PHP");
        map.put("Py", "Python");
        // show hashMap
        Iterator<String> itr = map.keySet().iterator();
        while (itr.hasNext()) {
            System.out.println(map.get(itr.next()));
        }
    }
}
```
```
C ++
Java
PHP
Python
```

### Truy cập phần tử của HashMap

Phương thức `get(key)` trả về giá trị của phần tử có key đã chỉ định, ví dụ:

```java
package vn.viettuts.collection.hashmap;
 
import java.util.HashMap;
 
/**
 * truy cap phan tu cua HashMap
 * 
 * @author viettuts.vn
 */
public class HashMapExample3 {
 
    public static void main(String args[]) {
        // init hashMap
        HashMap<Integer, String> hashMap = new HashMap<Integer, String>();
        // add elements to hashMap
        hashMap.put(1, "Java");
        hashMap.put(3, "C++");
        hashMap.put(2, "PHP");
        hashMap.put(4, "Python");
        // hien thi HashMap
        System.out.println("Phan tu co key = 1 la: " + hashMap.get(1));
        System.out.println("Phan tu co key = 2 la: " + hashMap.get(2));
    }
}
```
```
Phan tu co key = 1 la: Java
Phan tu co key = 2 la: PHP
```

### Cập nhật giá trị của phần tử HashMap
Phương thức `put()` được sử dụng để thêm phần tử, đồng thời bạn cũng có thể sử dụng phương thức này để cập nhật giá trị của phần tử hashMap, ví dụ:

```java
package vn.viettuts.collection.hashmap;
 
import java.util.HashMap;
 
/**
 * cap nhat phan tu cua HashMap
 * 
 * @author viettuts.vn
 */
public class HashMapExample4 {
 
    public static void main(String args[]) {
        // khoi tao hashMap
        HashMap<Integer, String> hashMap = new HashMap<Integer, String>();
        // them cac phan tu vao hashMap
        hashMap.put(1, "Java");
        hashMap.put(3, "C++");
        hashMap.put(2, "PHP");
        hashMap.put(4, "Python");
        // hien thi hashMap
        System.out.println(hashMap);
        // cap nhat gia tri cua phan tu co key = 4
        hashMap.put(4, "Angular8");
        // hien thi hashMap
        System.out.println(hashMap);
    }
}
```
```
{1=Java, 2=PHP, 3=C++, 4=Python}
{1=Java, 2=PHP, 3=C++, 4=Angular8}
```

### Xóa phần tử HashMap
Bạn có thể sử dụng phương thức remove() để xóa một phần tử, hoặc phương thức clear() để xóa hoàn toàn các phần tử của một HashMap. Ví dụ:

```java
package vn.viettuts.collection.hashmap;
 
import java.util.HashMap;
 
/**
 * Xoa phan tu cua HashMap
 * 
 * @author viettuts.vn
 */
public class HashMapExample5 {
 
    public static void main(String args[]) {
        // khoi tao hashMap
        HashMap<Integer, String> hashMap = new HashMap<Integer, String>();
        // them cac phan tu vao hashMap
        hashMap.put(1, "Java");
        hashMap.put(3, "C++");
        hashMap.put(2, "PHP");
        hashMap.put(4, "Python");
        // hien thi hashMap
        System.out.println(hashMap);
        // xoa phan tu co key = 4
        hashMap.remove(4);
        // hien thi hashMap
        System.out.println(hashMap);
        // xoa toan bo hashMap
        hashMap.clear();
        // hien thi hashMap
        System.out.println(hashMap);
    }
}
```
```
{1=Java, 2=PHP, 3=C++, 4=Python}
{1=Java, 2=PHP, 3=C++}
{}
```

### Tạo HashMap có kiểu generic là đối tượng do người dùng định nghĩa
Ví dụ tạo một lớp Student, sau đó tạo một đối tượng HashMap với key có kiểu String, value có kiểu Student:
Lớp Student.java

```java
package vn.viettuts.collection.hashmap;
 
/**
 * Student class
 * 
 * @author viettuts.vn
 */
public class Student{
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

Lớp HashMapExample6.java

```java
package vn.viettuts.collection.hashmap;
 
import java.util.HashMap;
import java.util.Map;
import java.util.Set;
 
public class HashMapExample6 {
    /**
     * main
     * 
     * @author viettuts.vn
     * @param args
     */
    public static void main(String args[]) {
        // init hashMap
        Map<String, Student> hashMap = new HashMap<String, Student>();
        // add elements to hashMap
        hashMap.put("1", new Student("A", 12, "Hanoi"));
        hashMap.put(null, new Student("C", 13, "Hanoi"));
        hashMap.put("2", null);
        hashMap.put("4", new Student("D", 14, "Hanoi"));
        // show hashMap
        show(hashMap);
    }
 
    /**
     * show HashMap
     * 
     * @param viettuts.vn
     */
    public static void show(Map<String, Student> map) {
        Set<String> keySet = map.keySet();
        for (String key : keySet) {
            System.out.println(key + " " + map.get(key));
        }
    }
}
```
```
null Student@name=C,age=13,address=Hanoi
1 Student@name=A,age=12,address=Hanoi
2 null
4 Student@name=D,age=14,address=Hanoi
```

### Sự khác nhau giữa HashSet và HashMap
Đây cũng là một câu hỏi phỏng vấn được hỏi với tần suất cao.

Câu trả lời là: HashSet chỉ chứa giá trị (value) trong khi HashMap chứa cặp key và value.

